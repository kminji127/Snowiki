---
description: 원격지 시스템 관리
---

# Chapter 8

서버-클라이언트

* 서버에 접속하려면 클라이언트 프로그램 필요
* 서버 OS와 클라이언트 OS가 같을 필요 X
* 텔넷 서버 ↔ 텔넷 클라이언트(telnet, 한글 PuTTY 등)

원격 접속 방법

* telnet(d), ssh(d): 텍스트 모드
* xrdp: GUI 모드 지원

479p에 비교 표 참조

**텔넷 서버:** 대부분 OS에 텔넷 클라이언트가 내장

1. 텔넷 서버 설치 `dnf -y install telnet-server`
2. 텔넷 서비스 시작 `systemctl start telnet.socket`
3. 텔넷 전용 사용자 생성 (adduser, passwd)
4. 방화벽 설정(포트 열기) `firewall-config`
   1. 포트: 가상의 논리적인 통신 연결 번호 (텔넷 서버는 **23**번)
   2. `firewall-cmd —add -service=telnet`
5. 텔넷 서비스 상시 가동 `systemctl enable telnet.socket`
6. 클라이언트에서 접속 `telnet 서버IP`

**OpenSSH 서버:** 데이터 전송 시 암호화 (포트 번호: **22**번)

1. openssh 서버 확인 `systemctl status sshd`
2. 방화벽 설정 `firewall-config`
3. 서버 접속 `ssh 사용자명@서버IP` 또는 `ssh 사용자이름@호스트이름`

**XRDP 서버:** X윈도 환경으로 원격 접속 지원

1. EPEL 저장소에서 추가 설치 허용 `dnf -y install epel-release`
2. 패키지 설치 `dnf -y install xrdp`
3. 서비스 시작 및 상시 가동 `systemctl start xrdp` → `systemctl enable xrdp`
4. 방화벽에서 포트 번호인 **3389**번 허용 `firewall-config`
5. 클라이언트 접속 (원격 데스크톱 연결)

### SSH

openSSH 설정 파일: /etc/ssh

서버 접속: `ssh 접속계정@접속할서버주소` 또는 `ssh -l 접속계정 접속할서버주소`

특징: OpenBSD 그룹에서 구현, 서버 유효성 확인 가능

**사용자 인증 절차(공개 키 인증 방식)**

1. 클라이언트: 공개+비밀 키 생성 (서버 용은 이미 생성되어 있음)
   1. `ssh-keygen 옵션`
   2. 옵션: 13p
2. 서버에 사용자 공개 키 등록
   * `ssh-copy-id 로그인이름@호스트이름`
   * 공개(호스트) 키 위치: \~/.ssh/known\_hosts
   * 서버 측 \~/.ssh/authorized\_keys 에 등록된 키 추가
3. 접속 시 사용자의 키가 사용 가능한지 확인
4. 클라이언트: 공개 키와 데이터를 전자서명
5. 데이터와 전자서명을 서버에 전송
6. 서버: 데이터와 서명 검증 → 로그인 허용

**SSH 서버**

서버 바이너리: /user/sbin/sshd

설정 파일: /etc/ssh/sshd\_config

기본 포트: **22**

프로토콜: 버전 2

**SSH 클라이언트**

`ssh 옵션 로그인이름@호스트 명령`

* `scp`: 호스트 간 파일 복사
* `sftp`: ssh 사용한 파일 전송 (sftp 사용자명@대상호스트)
* SSH Agent: 암호 문구(passphrase) 생략, 비밀 키를 메모리에 보존, bash를 ssh-agent의 자식 프로세스로 시작해야 함 (ssh-agent bash → ssh-add → ssh-add -l)

설정 파일: /etc/ssh/ssh\_config

* 사용자 개별 설정 시 \~/.ssh/ssh\_config

로그인 후 자동으로 실행하고 싶은 명령이 있을 경우

* 모든 사용자 적용: /etc/ssh/sshrc
* 사용자 개별 적용: \~/.ssh/rc
