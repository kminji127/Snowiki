---
description: 웹 서버 설치와 운영
---

# Chapter 12

### APM

Apache 웹 서버(httpd) + PHP + MariaDB

1. 설치: `dnf -y install httpd php php-mysqld mariadb-server`
2. `systemctl start → enable httpd/mariadb`
   1. php는 별도 서비스가 아니라 httpd에 포함된 기능임
3. 홈 화면: var/www/html/index.html
4.  php 정보: var/www/html/phpinfo.php

    ```php
    <?php phpinfo(); ?>
    ```
5. 방화벽 설정(`firewall-config`) - 영구적 - 서비스 - http/https 선택
6. 클라이언트에서 접속: http://192.168.111.100/phpinfo.php (서버에서는 localhost)
7. `mysql` → DB, 사용자 생성, 권한 부여 (이하 634p\~638p)

### Apache

설정 파일:

* /etc/httpd/conf/ → httpd.conf가 메인 설정 파일
* /etc/httpd/conf.d/

모듈 파일: /etc/httpd/modules

* 확장자: .so
* 기본적으로 포함된 코어 모듈과 별도 제공 모듈로 구분

httpd.conf 태그 별 설정 적용 범위

* Files: 파일의 범위
* Directory: 디렉터리의 범위
* Location: URL의 범위

**httpd.conf 주요 설정**

* ServerTokens: http 헤더 내에 출력되는 버전 정보, 보통 Prod로 지정
* LoadModule: 모듈 활성화 여부
* User / Group: httpd 자식 프로세스의 실행 사용자/그룹 지정
  * 부모 프로세스(**80**번 포트로 요청 받음) / 자식 프로세스(클라이언트에 따라 처리 담당)
  * 부모: root 권한, 자식: 일반 사용자 권한 → 크래킹 피해 최소화
* DocumentRoot: 최상위 디렉터리
  * 기본값: /var/www/html
  * 이 디렉터리 이하의 파일들은 웹 브라우저에서 접근 가능
* UserDir: 일반 사용자의 공개 홈 디렉터리
  * /home/시용자명/public\_html
  * disabled: 비공개 (디폴트)
  * 최소 711(rwx—x—x)로 설정
* DirectoryIndex: 디렉터리의 인덱스 페이지로 반환할 파일
  * 순서대로 검색 → 처음 발견된 파일이 표시됨
* Alias: DocumentRoot 트리 외 장소 참조, 보안 취약점 주의
* Options: Directory 태그 안에서 옵션 기능 설정
* ServerSignature: 에러 화면에 footer 출력 여부

외부 설정 파일

* httpd.conf 파일 내의 AccessFileName 지시어에 지정 → 기본값: .htaccess
* AllowOverride: 덮어씌울 디렉티브들의 종류 지정

**아파치 로그**

* 로그 레벨: LogLevel (debug, info, notice, warn, error, crit, alert, emerg) - 뒤로 갈 수록 출력되는 정보 양 감소
* 에러 로그: 에러, 서버 작동 사항 기록
  * 파일명: ErrorLog 지시어에서 지정 (기본값: logs/error\_log)
  * 경로: ServerRoot 디렉터리의 상대 경로 (/var/log/httpd/error\_log)
* 접근 로그: 클라이언트로부터의 접근 기록
  * 기록 항목 및 서식명: LogFormat 지시어로 지정
    * LogFormat 포맷 서식명
    * custom 로그 서식: combined, common, referer, agent
  * 로그를 어떤 파일에 저장하는가: CustomLog 지시어로 지정
    * CustomLog 로그파일명 로그서식명
    * 경로: ServerRoot 디렉터리의 상대 경로 (기본값: /var/log/httpd/access\_log)

https: **433**번 포트
