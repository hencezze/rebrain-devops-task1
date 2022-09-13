This repo have default cfg file
## Description of the standard nginx configuration file and nginx

## About
    A web server and a mail proxy server running on Unix-like operating systems.
> It can also be used as a load balancer

## Installation

To install nginx, enter the following commands

## Ubuntu
```sh
sudo apt install nginx -y
```
## Centos
```sh
yum install nginx
```
> but if nginx service doesnt start "systemctl start nginx"

## Nginx Friends
The module can work with the services listed in the table

| Servuce | Site |
| ------ | ------ |
| Docker | [https://www.docker.com/][PlDb] |
| Kubernetes | [https://kubernetes.io/][PlGh] |
| MySQL | [https://www.mysql.com/][PlGd] |
| Postgresql | [https://www.postgresql.org/][PlOd] |
**and etc**

## Nginxr + Docker = Ngocker
If you want to use nginx with Docker, you need to install docker app on host, but if you're too lazy, docker have something for you - `docker-compose`

## Ubuntu
```sh
sudo apt install docker.io docker docker-compose -y
```
## Centos
```sh
yum install docker docker-compose
```
**Docker shell script**
```sh
sudo docker run -it -d --name nginx -p 80:80 nginx 
```
Script's fragment `-p 80:80` for forvarding port on host machine

**Docker-сompose script**
```sh
version: '3.3'
services:
  ngocker:
    image: nginx
    ports:
      - 80:80
    volumes:
      - /path/to/your/git/repo:/etc/nginx/nginx.conf
```
> But other servicesdont see each other, bc in this code network doesnt exist

Add to the end, without margins: 
```sh
networks:
    network_name:
        driver: bridge/host/ingress
```
