# docker-nginx-laravel

## php
ver.5.6
## mysql
ver.5.7
## nginx
ver.1.10.3


## ssl設定
$ cd docker-configs/nginx-proxy/certs/  
$ sudo sh -c "openssl genrsa 2048 > [hostName].key"  
$ sudo sh -c "openssl req -new -key [hostName].key > [hostName].csr"  

common nameは[hostName]にする

$ sudo sh -c "openssl x509 -days 3650 -req -signkey [hostName].key < [hostName].csr > [hostName].crt"  

## 使用方法
docker-compose.ymlのVIRTUAL_HOSTに使用するバーチャルホストを設定  
www以下にgit clone  
$ composer install  
$ cp .env.example .env

