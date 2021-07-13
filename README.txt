Hello,  안녕하세요! 
이 곳은 제가 MongoDB를 학습하면서 정리하기 위한 Repository입니다.
많은 도움 되셨으면 합니다.

Cent OS 7 에서 Mongo DB 설치 방법
* root 계정으로 진행

1. yum package repository 추가 

# vi /etc/yum.repos.d/mongodb-org-4.4.repo

아래를 작성
[mongodb-org-4.4]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/redhat/$releasever/mongodb-org/4.4/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-4.4.asc

2. MongoDB package install

# yum install -y mongodb-org

Loaded plugins: fastestmirror, priorities
Determining fastest mirrors
epel/x86_64/metalink                                     | 9.0 kB     00:00
 * base: ftp.kaist.ac.kr
 * epel: nrt.edge.kernel.org
 * extras: ftp.kaist.ac.kr
 * remi-php72: mirror.sjc02.svwh.net
 * remi-safe: mirror.sjc02.svwh.net
 * rpmforge: mirror.chpc.utah.edu
 * updates: ftp.kaist.ac.kr
base                                                     | 3.6 kB     00:00
epel                                                     | 4.7 kB     00:00
extras                                                   | 2.9 kB     00:00
mongodb-org-4.4                                          | 2.5 kB     00:00
nginx                                                    | 2.9 kB     00:00
nodesource                                               | 2.5 kB     00:00
remi-php72                                               | 3.0 kB     00:00
remi-safe                                                | 3.0 kB     00:00
rpmforge                                                 | 1.9 kB     00:00
updates                                                  | 2.9 kB     00:00
(1/8): epel/x86_64/updateinfo                              | 1.0 MB   00:08
(2/8): mongodb-org-4.4/7/primary_db                        |  53 kB   00:00
(3/8): nodesource/x86_64/primary_db                        |  43 kB   00:00
(4/8): epel/x86_64/primary_db                              | 6.9 MB   00:02
(5/8): nginx/x86_64/primary_db                             |  67 kB   00:06
(6/8): remi-php72/primary_db                               | 250 kB   00:09
updates/7/x86_64/primary_db    FAILED
http://mirror.kakao.com/centos/7.9.2009/updates/x86_64/repodata/8f0fe9aaa433106aeb9b55f9c2a5c4a387ad2dae365a2eb58769587be8435d0f-primary.sqlite.bz2: [Errno 14]                                      curl#18 - "transfer closed with 9092892 bytes remaining to read"
Trying other mirror.
(7/8): updates/7/x86_64/primary_db                         | 8.8 MB   00:04
(8/8): remi-safe/primary_db                                | 2.0 MB   00:43
296 packages excluded due to repository priority protections
Resolving Dependencies
--> Running transaction check
---> Package mongodb-org.x86_64 0:4.4.6-1.el7 will be installed
--> Processing Dependency: mongodb-org-shell = 4.4.6 for package: mongodb-org-4.4.6-1.el7.x86_64
--> Processing Dependency: mongodb-org-tools = 4.4.6 for package: mongodb-org-4.4.6-1.el7.x86_64
--> Processing Dependency: mongodb-org-server = 4.4.6 for package: mongodb-org-4.4.6-1.el7.x86_64
--> Processing Dependency: mongodb-org-mongos = 4.4.6 for package: mongodb-org-4.4.6-1.el7.x86_64
--> Running transaction check
---> Package mongodb-org-mongos.x86_64 0:4.4.6-1.el7 will be installed
---> Package mongodb-org-server.x86_64 0:4.4.6-1.el7 will be installed
---> Package mongodb-org-shell.x86_64 0:4.4.6-1.el7 will be installed
---> Package mongodb-org-tools.x86_64 0:4.4.6-1.el7 will be installed
--> Processing Dependency: mongodb-org-database-tools-extra = 4.4.6 for package: mongodb-org-tools-4.4.6-1.el7.x86_64
--> Processing Dependency: mongodb-database-tools for package: mongodb-org-tools-4.4.6-1.el7.x86_64
--> Running transaction check
---> Package mongodb-database-tools.x86_64 0:100.3.1-1 will be installed
--> Processing Dependency: cyrus-sasl-gssapi for package: mongodb-database-tools-100.3.1-1.x86_64
--> Processing Dependency: cyrus-sasl-plain for package: mongodb-database-tools-100.3.1-1.x86_64
---> Package mongodb-org-database-tools-extra.x86_64 0:4.4.6-1.el7 will be installed
--> Running transaction check
---> Package cyrus-sasl-gssapi.x86_64 0:2.1.26-23.el7 will be installed
---> Package cyrus-sasl-plain.x86_64 0:2.1.26-23.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

================================================================================
 Package                          Arch   Version          Repository       Size
================================================================================
Installing:
 mongodb-org                      x86_64 4.4.6-1.el7      mongodb-org-4.4 6.2 k
Installing for dependencies:
 cyrus-sasl-gssapi                x86_64 2.1.26-23.el7    base             41 k
 cyrus-sasl-plain                 x86_64 2.1.26-23.el7    base             39 k
 mongodb-database-tools           x86_64 100.3.1-1        mongodb-org-4.4  50 M
 mongodb-org-database-tools-extra x86_64 4.4.6-1.el7      mongodb-org-4.4  19 k
 mongodb-org-mongos               x86_64 4.4.6-1.el7      mongodb-org-4.4  17 M
 mongodb-org-server               x86_64 4.4.6-1.el7      mongodb-org-4.4  22 M
 mongodb-org-shell                x86_64 4.4.6-1.el7      mongodb-org-4.4  14 M
 mongodb-org-tools                x86_64 4.4.6-1.el7      mongodb-org-4.4 6.1 k

Transaction Summary
================================================================================
Install  1 Package (+8 Dependent packages)

Total download size: 102 M
Installed size: 413 M
Downloading packages:
(1/9): cyrus-sasl-plain-2.1.26-23.el7.x86_64.rpm           |  39 kB   00:00
(2/9): cyrus-sasl-gssapi-2.1.26-23.el7.x86_64.rpm          |  41 kB   00:00
warning: /var/cache/yum/x86_64/7/mongodb-org-4.4/packages/mongodb-org-4.4.6-1.el
7.x86_64.rpm: Header V3 RSA/SHA1 Signature, key ID 90cfb1f5: NOKEY
Public key for mongodb-org-4.4.6-1.el7.x86_64.rpm is not installed
(3/9): mongodb-org-4.4.6-1.el7.x86_64.rpm                  | 6.2 kB   00:00
(4/9): mongodb-org-database-tools-extra-4.4.6-1.el7.x86_64 |  19 kB   00:00
(5/9): mongodb-org-mongos-4.4.6-1.el7.x86_64.rpm           |  17 MB   00:18
(6/9): mongodb-database-tools-100.3.1.x86_64.rpm           |  50 MB   00:48
(7/9): mongodb-org-server-4.4.6-1.el7.x86_64.rpm           |  22 MB   00:28
(8/9): mongodb-org-tools-4.4.6-1.el7.x86_64.rpm            | 6.1 kB   00:00
(9/9): mongodb-org-shell-4.4.6-1.el7.x86_64.rpm            |  14 MB   00:11
--------------------------------------------------------------------------------
Total                                              1.7 MB/s | 102 MB  01:00
Retrieving key from https://www.mongodb.org/static/pgp/server-4.4.asc
Importing GPG key 0x90CFB1F5:
 Userid     : "MongoDB 4.4 Release Signing Key <packaging@mongodb.com>"
 Fingerprint: 2069 1eec 3521 6c63 caf6 6ce1 6564 08e3 90cf b1f5
 From       : https://www.mongodb.org/static/pgp/server-4.4.asc
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
Warning: RPMDB altered outside of yum.
  Installing : mongodb-org-database-tools-extra-4.4.6-1.el7.x86_64          1/9
  Installing : cyrus-sasl-gssapi-2.1.26-23.el7.x86_64                       2/9
  Installing : mongodb-org-shell-4.4.6-1.el7.x86_64                         3/9
  Installing : cyrus-sasl-plain-2.1.26-23.el7.x86_64                        4/9
  Installing : mongodb-database-tools-100.3.1-1.x86_64                      5/9
  Installing : mongodb-org-tools-4.4.6-1.el7.x86_64                         6/9
  Installing : mongodb-org-server-4.4.6-1.el7.x86_64                        7/9
Created symlink from /etc/systemd/system/multi-user.target.wants/mongod.service
to /usr/lib/systemd/system/mongod.service.
  Installing : mongodb-org-mongos-4.4.6-1.el7.x86_64                        8/9
  Installing : mongodb-org-4.4.6-1.el7.x86_64                               9/9
  Verifying  : mongodb-database-tools-100.3.1-1.x86_64                      1/9
  Verifying  : mongodb-org-4.4.6-1.el7.x86_64                               2/9
  Verifying  : mongodb-org-mongos-4.4.6-1.el7.x86_64                        3/9
  Verifying  : mongodb-org-server-4.4.6-1.el7.x86_64                        4/9
  Verifying  : cyrus-sasl-plain-2.1.26-23.el7.x86_64                        5/9
  Verifying  : mongodb-org-shell-4.4.6-1.el7.x86_64                         6/9
  Verifying  : mongodb-org-tools-4.4.6-1.el7.x86_64                         7/9
  Verifying  : cyrus-sasl-gssapi-2.1.26-23.el7.x86_64                       8/9
  Verifying  : mongodb-org-database-tools-extra-4.4.6-1.el7.x86_64          9/9

Installed:
  mongodb-org.x86_64 0:4.4.6-1.el7

Dependency Installed:
  cyrus-sasl-gssapi.x86_64 0:2.1.26-23.el7
  cyrus-sasl-plain.x86_64 0:2.1.26-23.el7
  mongodb-database-tools.x86_64 0:100.3.1-1
  mongodb-org-database-tools-extra.x86_64 0:4.4.6-1.el7
  mongodb-org-mongos.x86_64 0:4.4.6-1.el7
  mongodb-org-server.x86_64 0:4.4.6-1.el7
  mongodb-org-shell.x86_64 0:4.4.6-1.el7
  mongodb-org-tools.x86_64 0:4.4.6-1.el7

Complete!


3. MongoDB service 시작하기

# systemctl start mongod

3.1 부팅 시 서비스 자동 시작

# systemctl enable mongod

4. MongoDB Shell 접속하기

# mongo 