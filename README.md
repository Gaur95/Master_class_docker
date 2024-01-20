# Master_class_docker
# for_docker_desktop
## download docker desktop
https://www.docker.com/products/docker-desktop 

## enable wsl 
https://learn.microsoft.com/en-us/windows/wsl/install-manual
## or  copy below command and run from cmd (run as administrator)
```
dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
```
```
dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
```
### now update wsl --- install and run it. ->>>

https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi

### then install docker desktop
### and check from cmd 
```
docker --version
```
## docker 
 +  docker images ----- to show container images
 +  docker pull <image_name>  ----  pull container images
 +  docker ps ----   to show running conatiner 
 +  docker ps -a ---- to show all container 
 +  docker rmi <img_name /imgage_id> --- to remove container images
 +  docker run <image_name> ----  to run container
 +  docker exec -it <container_name> ---- to enter into the container
 +  docker stop <container_name/container_id>  --- to stop running
 +  docker rm <container name>  ---  to remove container 
 + docker start <container name >  -- to start stop container
 + docker rm -f <container name >  --- to remove running container 
<img src=20jan.jpg>
### docker exec --  ----> to change html code
```
ubuntu@ip-172-31-4-185:~$ docker exec -it akash bash
root@266ca2f4fc72:/usr/local/apache2# ls
bin  build  cgi-bin  conf  error  htdocs  icons  include  logs  modules
root@266ca2f4fc72:/usr/local/apache2# cd htdocs
root@266ca2f4fc72:/usr/local/apache2/htdocs# ls
index.html
root@266ca2f4fc72:/usr/local/apache2/htdocs# cat index.html
<html><body><h1>It works!</h1></body></html>
root@266ca2f4fc72:/usr/local/apache2/htdocs# cat >index.html
this is cool i am using dockerrrrr
^C
root@266ca2f4fc72:/usr/local/apache2/htdocs# cat index.html
this is cool i am using docker
rrr
root@266ca2f4fc72:/usr/local/apache2/htdocs# exit
exit
```
# history
```

C:\Users\ritik>ssh ubuntu@65.0.27.145
The authenticity of host '65.0.27.145 (65.0.27.145)' can't be established.
ECDSA key fingerprint is SHA256:OCKINjNrrkIyquKikKA7szCyGwejKKGui4cl34ZoANU.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '65.0.27.145' (ECDSA) to the list of known hosts.
ubuntu@65.0.27.145's password:
Welcome to Ubuntu 22.04.3 LTS (GNU/Linux 6.2.0-1017-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat Jan 20 11:50:15 UTC 2024

  System load:  0.0               Processes:                128
  Usage of /:   7.0% of 28.89GB   Users logged in:          1
  Memory usage: 8%                IPv4 address for docker0: 172.17.0.1
  Swap usage:   0%                IPv4 address for eth0:    172.31.4.185


Expanded Security Maintenance for Applications is not enabled.

40 updates can be applied immediately.
25 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Sat Jan 20 11:38:09 2024 from 152.58.70.65
ubuntu@ip-172-31-4-185:~$
ubuntu@ip-172-31-4-185:~$ docker ps
permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/containers/json": dial unix /var/run/docker.sock: connect: permission denied
ubuntu@ip-172-31-4-185:~$ sudo usermod -aG docker ubuntu
ubuntu@ip-172-31-4-185:~$
logout
Connection to 65.0.27.145 closed.

C:\Users\ritik>ssh ubuntu@65.0.27.145
ubuntu@65.0.27.145's password:
Welcome to Ubuntu 22.04.3 LTS (GNU/Linux 6.2.0-1017-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

  System information as of Sat Jan 20 11:50:15 UTC 2024

  System load:  0.0               Processes:                128
  Usage of /:   7.0% of 28.89GB   Users logged in:          1
  Memory usage: 8%                IPv4 address for docker0: 172.17.0.1
  Swap usage:   0%                IPv4 address for eth0:    172.31.4.185


Expanded Security Maintenance for Applications is not enabled.

40 updates can be applied immediately.
25 of these updates are standard security updates.
To see these additional updates run: apt list --upgradable

Enable ESM Apps to receive additional future security updates.
See https://ubuntu.com/esm or run: sudo pro status


Last login: Sat Jan 20 11:50:16 2024 from 103.87.58.32
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
ubuntu@ip-172-31-4-185:~$ docker images
REPOSITORY   TAG       IMAGE ID   CREATED   SIZE
ubuntu@ip-172-31-4-185:~$ docker pull ubuntu
Using default tag: latest
latest: Pulling from library/ubuntu
29202e855b20: Pull complete
Digest: sha256:e6173d4dc55e76b87c4af8db8821b1feae4146dd47341e4d431118c7dd060a74
Status: Downloaded newer image for ubuntu:latest
docker.io/library/ubuntu:latest
ubuntu@ip-172-31-4-185:~$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED      SIZE
ubuntu       latest    e34e831650c1   8 days ago   77.9MB
ubuntu@ip-172-31-4-185:~$ docker pull alpine
Using default tag: latest
latest: Pulling from library/alpine
661ff4d9561e: Pull complete
Digest: sha256:51b67269f354137895d43f3b3d810bfacd3945438e94dc5ac55fdac340352f48
Status: Downloaded newer image for alpine:latest
docker.io/library/alpine:latest
ubuntu@ip-172-31-4-185:~$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
ubuntu       latest    e34e831650c1   8 days ago    77.9MB
alpine       latest    f8c20f8bbcb6   6 weeks ago   7.38MB
ubuntu@ip-172-31-4-185:~$ docker pull busybox
Using default tag: latest
latest: Pulling from library/busybox
9ad63333ebc9: Pull complete
Digest: sha256:3d3698b745b0c67ddf2c515650b42955b0bcd123c92060008aae4f4aac1c77b3
Status: Downloaded newer image for busybox:latest
docker.io/library/busybox:latest
ubuntu@ip-172-31-4-185:~$ docker iamges
docker: 'iamges' is not a docker command.
See 'docker --help'
ubuntu@ip-172-31-4-185:~$ docker images
REPOSITORY   TAG       IMAGE ID       CREATED       SIZE
busybox      latest    3f57d9401f8d   2 days ago    4.26MB
ubuntu       latest    e34e831650c1   8 days ago    77.9MB
alpine       latest    f8c20f8bbcb6   6 weeks ago   7.38MB
ubuntu@ip-172-31-4-185:~$ docker run -itd --name akash -p 1122:80 httpd
266ca2f4fc72978990f865f4cd400ed59920251b3ef1869b45649121e9f4d291
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS         PORTS                                   NAMES
266ca2f4fc72   httpd     "httpd-foreground"   5 seconds ago   Up 4 seconds   0.0.0.0:1122->80/tcp, :::1122->80/tcp   akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED          STATUS          PORTS                                   NAMES
266ca2f4fc72   httpd     "httpd-foreground"   12 seconds ago   Up 12 seconds   0.0.0.0:1122->80/tcp, :::1122->80/tcp   akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED              STATUS              PORTS                                   NAMES
266ca2f4fc72   httpd     "httpd-foreground"   About a minute ago   Up About a minute   0.0.0.0:1122->80/tcp, :::1122->80/tcp   akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED              STATUS              PORTS                                   NAMES
266ca2f4fc72   httpd     "httpd-foreground"   About a minute ago   Up About a minute   0.0.0.0:1122->80/tcp, :::1122->80/tcp   akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS         PORTS                                                 NAMES
7a7baf09a9d7   httpd     "httpd-foreground"   8 seconds ago   Up 7 seconds   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp   saqeeb
a0b310a2bd8c   httpd     "httpd-foreground"   9 seconds ago   Up 8 seconds   0.0.0.0:1007->80/tcp, :::1007->80/tcp                 Unknown
266ca2f4fc72   httpd     "httpd-foreground"   2 minutes ago   Up 2 minutes   0.0.0.0:1122->80/tcp, :::1122->80/tcp                 akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED          STATUS          PORTS                                                 NAMES
7a7baf09a9d7   httpd     "httpd-foreground"   26 seconds ago   Up 25 seconds   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp   saqeeb
a0b310a2bd8c   httpd     "httpd-foreground"   27 seconds ago   Up 27 seconds   0.0.0.0:1007->80/tcp, :::1007->80/tcp                 Unknown
266ca2f4fc72   httpd     "httpd-foreground"   2 minutes ago    Up 2 minutes    0.0.0.0:1122->80/tcp, :::1122->80/tcp                 akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED              STATUS              PORTS                                                 NAMES
57f90730a63c   httpd     "httpd-foreground"   About a minute ago   Up About a minute   0.0.0.0:1128->80/tcp, :::1128->80/tcp                 shubham
7a7baf09a9d7   httpd     "httpd-foreground"   2 minutes ago        Up 2 minutes        80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp   saqeeb
a0b310a2bd8c   httpd     "httpd-foreground"   2 minutes ago        Up 2 minutes        0.0.0.0:1007->80/tcp, :::1007->80/tcp                 Unknown
266ca2f4fc72   httpd     "httpd-foreground"   4 minutes ago        Up 4 minutes        0.0.0.0:1122->80/tcp, :::1122->80/tcp                 akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED         STATUS         PORTS                                                 NAMES
57f90730a63c   httpd     "httpd-foreground"   2 minutes ago   Up 2 minutes   0.0.0.0:1128->80/tcp, :::1128->80/tcp                 shubham
7a7baf09a9d7   httpd     "httpd-foreground"   3 minutes ago   Up 3 minutes   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp   saqeeb
a0b310a2bd8c   httpd     "httpd-foreground"   3 minutes ago   Up 3 minutes   0.0.0.0:1007->80/tcp, :::1007->80/tcp                 Unknown
266ca2f4fc72   httpd     "httpd-foreground"   5 minutes ago   Up 5 minutes   0.0.0.0:1122->80/tcp, :::1122->80/tcp                 akash
ubuntu@ip-172-31-4-185:~$ docker exec -it akash bash
root@266ca2f4fc72:/usr/local/apache2# ls
bin  build  cgi-bin  conf  error  htdocs  icons  include  logs  modules
root@266ca2f4fc72:/usr/local/apache2# cd htdocs
root@266ca2f4fc72:/usr/local/apache2/htdocs# ls
index.html
root@266ca2f4fc72:/usr/local/apache2/htdocs# cat index.html
<html><body><h1>It works!</h1></body></html>
root@266ca2f4fc72:/usr/local/apache2/htdocs# cat >index.html
this is cool i am using dockerrrrr
^C
root@266ca2f4fc72:/usr/local/apache2/htdocs# cat index.html
this is cool i am using docker
rrr
root@266ca2f4fc72:/usr/local/apache2/htdocs# exit
exit
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE     COMMAND              CREATED          STATUS          PORTS                                                 NAMES
7665f2938526   httpd     "httpd-foreground"   8 minutes ago    Up 8 minutes    0.0.0.0:3322->80/tcp, :::3322->80/tcp                 sp
57f90730a63c   httpd     "httpd-foreground"   11 minutes ago   Up 11 minutes   0.0.0.0:1128->80/tcp, :::1128->80/tcp                 shubham
7a7baf09a9d7   httpd     "httpd-foreground"   12 minutes ago   Up 12 minutes   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp   saqeeb
a0b310a2bd8c   httpd     "httpd-foreground"   12 minutes ago   Up 12 minutes   0.0.0.0:1007->80/tcp, :::1007->80/tcp                 Unknown
266ca2f4fc72   httpd     "httpd-foreground"   14 minutes ago   Up 14 minutes   0.0.0.0:1122->80/tcp, :::1122->80/tcp                 akash
ubuntu@ip-172-31-4-185:~$ docker network create akashnetwork
ec3af178c6923bf425f2916d242c55409fc2b00d5128023162cffd59f08eb22a
ubuntu@ip-172-31-4-185:~$ docker network ls
NETWORK ID     NAME             DRIVER    SCOPE
ec3af178c692   akashnetwork     bridge    local
a573ad4d3015   bridge           bridge    local
2632be46bfb6   host             host      local
2d1933998e32   none             null      local
1fd2415c1d78   saqeebnetwork    bridge    local
10a9b7830bd2   shubhamnetwork   bridge    local
ubuntu@ip-172-31-4-185:~$ docker run -d --name akashwordpress --network akashnetwork -p 1133:80 wordpress
a20c9e5353c80ab0ddd21f233b65acb7ae30cde44481d0d685e1ce4d5f1ad505
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS          PORTS                                                 NAMES
676b083f4a75   wordpress   "docker-entrypoint.s…"   3 seconds ago    Up 2 seconds    80/tcp, 0.0.0.0:32769->4455/tcp, :::32769->4455/tcp   saqeebwordpress
a20c9e5353c8   wordpress   "docker-entrypoint.s…"   6 seconds ago    Up 5 seconds    0.0.0.0:1133->80/tcp, :::1133->80/tcp                 akashwordpress
77c8b73b3e0e   wordpress   "docker-entrypoint.s…"   18 seconds ago   Up 17 seconds   0.0.0.0:1138->80/tcp, :::1138->80/tcp                 shubhamwordpress
7665f2938526   httpd       "httpd-foreground"       18 minutes ago   Up 18 minutes   0.0.0.0:3322->80/tcp, :::3322->80/tcp                 sp
57f90730a63c   httpd       "httpd-foreground"       21 minutes ago   Up 21 minutes   0.0.0.0:1128->80/tcp, :::1128->80/tcp                 shubham
7a7baf09a9d7   httpd       "httpd-foreground"       22 minutes ago   Up 22 minutes   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp   saqeeb
a0b310a2bd8c   httpd       "httpd-foreground"       22 minutes ago   Up 22 minutes   0.0.0.0:1007->80/tcp, :::1007->80/tcp                 Unknown
266ca2f4fc72   httpd       "httpd-foreground"       24 minutes ago   Up 24 minutes   0.0.0.0:1122->80/tcp, :::1122->80/tcp                 akash
ubuntu@ip-172-31-4-185:~$ docker run -itd --name akashdb --network akashnetwork -p 1144:3306 -e MYSQL_ROOT_PASSWORD=q123@ -e MYSQL_DATABASE=mydb -e MYSQL_USER=akash -e MYSQL_PASSWORD=q123@ mysql
Unable to find image 'mysql:latest' locally
latest: Pulling from library/mysql
558b7d69a2e5: Pull complete
2cb5a921059e: Pull complete
b85878fb9bb2: Pull complete
d16f3fd26a82: Pull complete
afd51b5329cb: Pull complete
374d2f7f3267: Pull complete
4ea1bb2c9574: Pull complete
1c9054053605: Pull complete
d79cd2da03be: Pull complete
e3a1aa788d17: Pull complete
Digest: sha256:d7c20c5ba268c558f4fac62977f8c7125bde0630ff8946b08dde44135ef40df3
Status: Downloaded newer image for mysql:latest
c39d696aca11e153fee3035311592f1490a1d9f3486d0d6c52dd644f04cee8aa
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS          PORTS                                                  NAMES
d6b088acbf8b   mysql       "docker-entrypoint.s…"   7 seconds ago    Up 3 seconds    33060/tcp, 0.0.0.0:1148->3306/tcp, :::1148->3306/tcp   shubhamdb
c39d696aca11   mysql       "docker-entrypoint.s…"   7 seconds ago    Up 3 seconds    33060/tcp, 0.0.0.0:1144->3306/tcp, :::1144->3306/tcp   akashdb
7dad62442c54   wordpress   "docker-entrypoint.s…"   8 minutes ago    Up 8 minutes    0.0.0.0:2244->80/tcp, :::2244->80/tcp                  guwordpress
5e9f2a6df5c2   wordpress   "docker-entrypoint.s…"   8 minutes ago    Up 8 minutes    0.0.0.0:4455->80/tcp, :::4455->80/tcp                  saqeebwordpress1
676b083f4a75   wordpress   "docker-entrypoint.s…"   9 minutes ago    Up 9 minutes    80/tcp, 0.0.0.0:32769->4455/tcp, :::32769->4455/tcp    saqeebwordpress
a20c9e5353c8   wordpress   "docker-entrypoint.s…"   9 minutes ago    Up 9 minutes    0.0.0.0:1133->80/tcp, :::1133->80/tcp                  akashwordpress
77c8b73b3e0e   wordpress   "docker-entrypoint.s…"   9 minutes ago    Up 9 minutes    0.0.0.0:1138->80/tcp, :::1138->80/tcp                  shubhamwordpress
7665f2938526   httpd       "httpd-foreground"       28 minutes ago   Up 28 minutes   0.0.0.0:3322->80/tcp, :::3322->80/tcp                  sp
57f90730a63c   httpd       "httpd-foreground"       31 minutes ago   Up 31 minutes   0.0.0.0:1128->80/tcp, :::1128->80/tcp                  shubham
7a7baf09a9d7   httpd       "httpd-foreground"       32 minutes ago   Up 32 minutes   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp    saqeeb
a0b310a2bd8c   httpd       "httpd-foreground"       32 minutes ago   Up 32 minutes   0.0.0.0:1007->80/tcp, :::1007->80/tcp                  Unknown
266ca2f4fc72   httpd       "httpd-foreground"       34 minutes ago   Up 34 minutes   0.0.0.0:1122->80/tcp, :::1122->80/tcp                  akash
ubuntu@ip-172-31-4-185:~$ docker ps
CONTAINER ID   IMAGE       COMMAND                  CREATED          STATUS          PORTS                                                  NAMES
d6b088acbf8b   mysql       "docker-entrypoint.s…"   4 minutes ago    Up 4 minutes    33060/tcp, 0.0.0.0:1148->3306/tcp, :::1148->3306/tcp   shubhamdb
c39d696aca11   mysql       "docker-entrypoint.s…"   4 minutes ago    Up 4 minutes    33060/tcp, 0.0.0.0:1144->3306/tcp, :::1144->3306/tcp   akashdb
7dad62442c54   wordpress   "docker-entrypoint.s…"   13 minutes ago   Up 13 minutes   0.0.0.0:2244->80/tcp, :::2244->80/tcp                  guwordpress
5e9f2a6df5c2   wordpress   "docker-entrypoint.s…"   13 minutes ago   Up 13 minutes   0.0.0.0:4455->80/tcp, :::4455->80/tcp                  saqeebwordpress1
676b083f4a75   wordpress   "docker-entrypoint.s…"   14 minutes ago   Up 14 minutes   80/tcp, 0.0.0.0:32769->4455/tcp, :::32769->4455/tcp    saqeebwordpress
a20c9e5353c8   wordpress   "docker-entrypoint.s…"   14 minutes ago   Up 14 minutes   0.0.0.0:1133->80/tcp, :::1133->80/tcp                  akashwordpress
77c8b73b3e0e   wordpress   "docker-entrypoint.s…"   14 minutes ago   Up 14 minutes   0.0.0.0:1138->80/tcp, :::1138->80/tcp                  shubhamwordpress
7665f2938526   httpd       "httpd-foreground"       32 minutes ago   Up 32 minutes   0.0.0.0:3322->80/tcp, :::3322->80/tcp                  sp
57f90730a63c   httpd       "httpd-foreground"       35 minutes ago   Up 35 minutes   0.0.0.0:1128->80/tcp, :::1128->80/tcp                  shubham
7a7baf09a9d7   httpd       "httpd-foreground"       36 minutes ago   Up 36 minutes   80/tcp, 0.0.0.0:32768->2233/tcp, :::32768->2233/tcp    saqeeb
a0b310a2bd8c   httpd       "httpd-foreground"       36 minutes ago   Up 36 minutes   0.0.0.0:1007->80/tcp, :::1007->80/tcp                  Unknown
266ca2f4fc72   httpd       "httpd-foreground"       39 minutes ago   Up 39 minutes   0.0.0.0:1122->80/tcp, :::1122->80/tcp                  akash
```
