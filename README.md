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
