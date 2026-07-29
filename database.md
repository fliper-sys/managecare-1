===== OS =====
Distributor ID:	Ubuntu
Description:	Ubuntu 24.04.4 LTS
Release:	24.04
Codename:	noble

===== Postgres =====
/usr/bin/psql
psql client found
active
ii  libpq5:amd64                    16.14-0ubuntu0.24.04.1                           amd64        PostgreSQL C client library
ii  postgresql                      16+257build1.1                                   all          object-relational SQL database (supported version)
ii  postgresql-16                   16.14-0ubuntu0.24.04.1                           amd64        The World's Most Advanced Open Source Relational Database
ii  postgresql-client-16            16.14-0ubuntu0.24.04.1                           amd64        front-end programs for PostgreSQL 16
ii  postgresql-client-common        257build1.1                                      all          manager for multiple PostgreSQL client versions
ii  postgresql-common               257build1.1                                      all          PostgreSQL database-cluster manager
ii  postgresql-contrib              16+257build1.1                                   all          additional facilities for PostgreSQL (supported version)

===== Docker =====
/usr/bin/docker
Docker version 29.6.1, build 8900f1d
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES

===== MinIO =====
-rw------- 1 root root 99 Jul  6 23:44 /root/managecare-minio-credentials.txt
  minio.service                                  loaded active running MinIO Object Storage
minio-u+     651  0.0  1.3 1534024 110496 ?      Ssl  Jul08  12:41 /usr/local/bin/minio server --address :9000 --console-address :9001 /opt/minio/data

===== Listening ports =====
Netid State  Recv-Q Send-Q Local Address:Port  Peer Address:PortProcess                                                    
udp   UNCONN 0      0          127.0.0.1:1721       0.0.0.0:*    users:(("monarx-agent",pid=2071805,fd=8))                 
udp   UNCONN 0      0         127.0.0.54:53         0.0.0.0:*    users:(("systemd-resolve",pid=497,fd=16))                 
udp   UNCONN 0      0      127.0.0.53%lo:53         0.0.0.0:*    users:(("systemd-resolve",pid=497,fd=14))                 
tcp   LISTEN 0      4096       127.0.0.1:65529      0.0.0.0:*    users:(("monarx-agent",pid=2071805,fd=17))                
tcp   LISTEN 0      4096      127.0.0.54:53         0.0.0.0:*    users:(("systemd-resolve",pid=497,fd=17))                 
tcp   LISTEN 0      4096   127.0.0.53%lo:53         0.0.0.0:*    users:(("systemd-resolve",pid=497,fd=15))                 
tcp   LISTEN 0      200        127.0.0.1:5432       0.0.0.0:*    users:(("postgres",pid=729,fd=7))                         
tcp   LISTEN 0      4096       127.0.0.1:9000       0.0.0.0:*    users:(("minio",pid=651,fd=6))                            
tcp   LISTEN 0      4096         0.0.0.0:22         0.0.0.0:*    users:(("sshd",pid=1812169,fd=3),("systemd",pid=1,fd=157))
tcp   LISTEN 0      200            [::1]:5432          [::]:*    users:(("postgres",pid=729,fd=6))                         
tcp   LISTEN 0      4096           [::1]:9000          [::]:*    users:(("minio",pid=651,fd=8))                            
tcp   LISTEN 0      4096               *:9001             *:*    users:(("minio",pid=651,fd=9))                            
tcp   LISTEN 0      4096               *:9000             *:*    users:(("minio",pid=651,fd=7))                            
tcp   LISTEN 0      4096            [::]:22            [::]:*    users:(("sshd",pid=1812169,fd=4),("systemd",pid=1,fd=161))

===== PM2 processes =====
/usr/bin/pm2
┌────┬───────────────────────┬─────────────┬─────────┬─────────┬──────────┬────────┬──────┬───────────┬──────────┬──────────┬──────────┬──────────┐
│ id │ name                  │ namespace   │ version │ mode    │ pid      │ uptime │ ↺    │ status    │ cpu      │ mem      │ user     │ watching │
├────┼───────────────────────┼─────────────┼─────────┼─────────┼──────────┼────────┼──────┼───────────┼──────────┼──────────┼──────────┼──────────┤
│ 0  │ managecare-backend    │ default     │ 1.0.0   │ fork    │ 4122120  │ 0s     │ 190… │ online    │ 0%       │ 3.6mb    │ root     │ disabled │
└────┴───────────────────────┴─────────────┴─────────┴─────────┴──────────┴────────┴──────┴───────────┴──────────┴──────────┴──────────┴──────────┘
host metrics | cpu: 55.4% | ram usage: 8.8% | disk: ⇓ 0.002mb/s ⇑ 0.042mb/s |

===== Nginx =====
nginx: not installed/active

===== /opt contents =====
total 20
drwxr-xr-x  5 root       root       4096 Jul  6 23:44 .
drwxr-xr-x 22 root       root       4096 Jul 22 18:28 ..
drwx--x--x  4 root       root       4096 Jul  6 16:05 containerd
drwxr-xr-x  3 root       root       4096 Jul  6 23:48 managecare-backend
drwxr-xr-x  4 minio-user minio-user 4096 Jul  6 23:44 minio

===== root home contents (top level) =====
total 52
drwx------  7 root root 4096 Jul  6 23:58 .
drwxr-xr-x 22 root root 4096 Jul 22 18:28 ..
-rw-------  1 root root 8905 Jul  6 23:49 .bash_history
-rw-r--r--  1 root root 3106 Apr 22  2024 .bashrc
drwx------  2 root root 4096 Jul  6 16:57 .cache
drwx------  3 root root 4096 Jul  6 16:05 .config
drwxr-xr-x  4 root root 4096 Jul  6 23:44 .npm
drwxr-xr-x  5 root root 4096 Jul  8 02:19 .pm2
-rw-r--r--  1 root root  161 Apr 22  2024 .profile
drwx------  2 root root 4096 Jul 22 19:10 .ssh
-rw-------  1 root root   99 Jul  6 23:44 managecare-minio-credentials.txt