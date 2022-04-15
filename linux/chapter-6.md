---
description: 하드디스크 관리와 사용자별 공간 할당
---

# Chapter 6

### 하드디스크, CD/DVD 장치 in 메인보드

* IDE: VMware의 경우 2개의 슬롯 당 각각 2개 장착 가능 (0:0, 0:1, 1:0, 1:1)
* SATA
* SCSI(서버용): VMware의 경우 4개의 슬롯 당 각각 16개 장착 가능 (0:0 \~ 3:15, 0:7 제외)
  * 장치 번호: `/dev/sda` → `/dev/sdb` → `/dev/sdc` → ...
  * 장치 내 파티션: `/dev/sda1` → `/dev/sda2` → ... , `/dev/sdb1` → `/dev/sdb2` → ...
* MVMe(SSD 형태의 플래시 메모리 사용 가능)

### 파티션(partition)

* Primary 파티션: 4개까지
* Extended 파티션

### 마운트 과정

* 리눅스에서는 파티션을 특정 디렉터리에 마운트시켜야 사용 가능

1. 물리적인 하드디스크 장착 (SCSI 0:1, `/dev/sdb`)
2. 하드디스크에 파티션 할당 (`/dev/sdb1`)
   1. `fdisk /dev/sdb`
   2. Command : n (새로운 파티션 분할)
   3. Select : p (Primary 파티션 선택)
   4. Partition number : 1 (파티션 번호 1번 선택)
   5. First/Last sector : `Enter` (시작/마지막 섹터 번호 입력)
      1. 섹터 하나는 512byte로 설정 → 512\*2097152 = 1024MB = 1GB
   6. Command : p (설정된 내용 확인)
   7. Command : w (설정 저장)
3. ext4 형식으로 파일 시스템 생성
   1. mkfs -t 파일시스템 파티션장치 (`mkfs -t ext4 /dev/sdb1`
   2. mkfs.파일시스템 파티션장치 (`mkfs.ext4 /dev/sdb1`
4. /dev/sdb1 파일 시스템을 사용하기 위해 디렉터리에 마운트
   1. mkdir /파일명
   2. `mount /dev/sdb1 /파일명`
5. 컴퓨터를 켤 때 /dev/sdb1 장치가 항상 /파일명 에 마운트되도록 설정
   1. `/etc/fstab` 파일에 내용 추가
   2. 장치이름, 마운트될 디렉터리, 파일 시스템, 속성, dump 작업 여부, 파일 시스템 체크 여부: /dev/sdb1 /파일명 ext4 defaults 0 0
6. 재부팅: `reboot`

### 여러 개의 하드디스크를 하나의 하드디스크처럼 사용

1. RAID
   1. 하드웨어 RAID: 여러 개의 하드디스크 연결한 장비 (고비용)
   2. 소프트웨어 RAID: 하드디스크만 여러 개 있으면 운영체제에서 지원하는 방식으로 RAID를 구성하는 방법 (비용 저렴)
2. LVM

### 쿼터(quota)

파일 시스템마다 사용자/그룹이 생성할 수 있는 파일의 용량과 개수 제한

[https://jhnyang.tistory.com/266](https://jhnyang.tistory.com/266)

1. 실습용 사용자 생성: `useradd -d /userHome/john john` → `passwd john`
2. /etc/fstab 수정: defaults → `defaults,usrjquota=aquota.user,jqfmt=vfsv0`
3. 재부팅 또는 리마운팅: `mount --options remount /userHome`
4. 쿼터 DB 생성
   1. cd /userHome
   2. `quotaoff -avug` (쿼터 끄기)
   3. quotacheck -augmn (쿼터 체크)
   4. `rm -rf aquota.*` (쿼터 관련 파일 삭제)
   5. quotacheck -augmn (다시 체크)
   6. `touch aquota.user [aquota.group](http://aquota.group)` (쿼터 관련 파일 생성)
   7. `chmod 600 aquota.*` (소유자 root 이외 접근 불가)
   8. quotacheck -augmn (다시 체크)
   9. `quotaon -avug` (쿼터 시작)
5. 개인별 쿼터 설정: 사용자별 공간 할당 `equota -u john`
   1. Filesystem: 파일 시스템 (/dev/sdb1)
   2. blocks: 현재 사용자가 사용하는 블록(KB 단위)
      1. soft: 소프트 사용 한도
      2. hard: 하드 사용 한도
         1. 0: 사용 한도를 정하지 않았음을 의미
   3. inodes: inode 개수(파일 개수)
      1. soft
      2. hard

grace period: 소프트 한도를 초과하여 사용할 수 있는 유예 기간

`edquota -t` :유예기간을 변경

`repquota /userHome`: 사용자별 현재 사용량 확인

`edquota -p 기준사용자 대상사용자`: 사용자 할당 설정 동일하게 복사
