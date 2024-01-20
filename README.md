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
    1  mkdir shubham                                                                                                          2  ls                                                                                                                     3  docker ps                                                                                                              4  sudo usermod -aG docker ubuntu                                                                                         5  docker ps                                                                                                              6  docker images                                                                                                          7  docker pull ubuntu                                                                                                     8  docker images                                                                                                          9  docker pull alpine                                                                                                    10  docker images                                                                                                         11  docker pull busybox                                                                                                   12  docker iamges                                                                                                         13  docker images                                                                                                         14  docker run -itd --name akash -p 1122:80 httpd                                                                         15  docker ps                                                                                                             16  docker exec -it akash bash                                                                                            17  docker ps                                                                                                             18  docker network create akashnetwork                                                                                    19  docker network ls                                                                                                     20  docker run -d --name akashwordpress --network akashnetwork -p 1133:80 wordpress                                       21  docker ps                                                                                                             22  docker run -itd --name akashdb --network akashnetwork -p 1144:3306 -e MYSQL_ROOT_PASSWORD=q123@ -e MYSQL_DATABASE=mydb -e MYSQL_USER=akash -e MYSQL_PASSWORD=q123@ mysql                                                                        23  docker ps  
```
