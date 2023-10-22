# 포트폴리오 사이트

### - `github.io` 배포
### - `web.app` 배포 (`firebase`)

## `Docker test` 환경 세팅 및 실행

### docker build
- https://hub.docker.com/_/httpd
```bash
$ docker build -t my-apache2 .
$ sudo docker images
REPOSITORY   TAG       IMAGE ID       CREATED         SIZE
my-apache2   latest    e133bdde4db8   2 minutes ago   173MB
```

### docker run
``` bash
$ sudo docker run -dit --name my-webapp -p 8080:80 my-apache2
$ sudo docker ps
CONTAINER ID   IMAGE        COMMAND              CREATED         STATUS         PORTS                                   NAMES
c52058cd5124   my-apache2   "httpd-foreground"   6 seconds ago   Up 5 seconds   0.0.0.0:8080->80/tcp, :::8080->80/tcp   my-webapp
```

### into docker
```bash
$ sudo docker exec -it my-webapp bash

root@c52058cd5124:/usr/local/apache2# ls -l

root@c52058cd5124:/usr/local/apache2# cd htdocs/

root@c52058cd5124:/usr/local/apache2/htdocs# ls -l

#파일 확인 후 http://localhost:8080 으로 웹 확인
```