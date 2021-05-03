# Nginx PHP MySQL With Docker 

Docker running Nginx, PHP-FPM, Composer, MySQL 

https://github.com/nanoninja/docker-nginx-php-mysql 에서 분기되었습니다.

## Overview

1. [필수 구성요소 설치](#필수-구성요소-설치)

    설치전 구성요소를 확인 합니다.

2. [프로젝트 복제](#프로젝트-복제)

    Github 저장소의 프로젝트 코드를 다운로드 합니다.

3. [어플리케이션 시작](#어플리케이션-시작)

    프로젝트 시작

___

## 필수 구성요소 설치 

다음 구성 요소가 필요합니다. 


* [Git](https://git-scm.com/downloads)
* [Docker](https://docs.docker.com/engine/installation/)
* [Docker Compose](https://docs.docker.com/compose/install/)
* Windows 경우 [Docker Desktop](https://docker.com/get-started/)

### 사용되는 이미지

* [Nginx](https://hub.docker.com/_/nginx/)
* [MySQL](https://hub.docker.com/_/mysql/)
* [PHP-FPM](https://hub.docker.com/r/nanoninja/php-fpm/)
* [Composer](https://hub.docker.com/_/composer/)
* [Generate Certificate](https://hub.docker.com/r/jacoelho/generate-certificate/)

이 프로젝트는 다음 포트를 사용합니다.

| Server     | Port |
|------------|------|
| MySQL      | 8989 |
| Nginx      | 8000 |
| Nginx SSL  | 3000 |

___

## 프로젝트 복제

Git 프로젝트를 다운로드 합니다. 

```sh
git clone https://github.com/YooSeungJin/DNPM.git 
```

프로젝트 디렉토리로 이동합니다.

```sh
cd DNPM
```

### Project  트리

```sh
.
├── Makefile
├── README.md
├── data
│   └── db
│       ├── dumps
│       └── mysql
├── docker-compose.yml
├── etc
│   ├── nginx
│   │   ├── default.conf
│   │   └── default.template.conf
│   ├── php
│   │   └── php.ini
│   └── ssl
└── web
    └── public
        └── index.php
```

___


## 어플리케이션 시작

1. Docker 시작 :

    ```sh
    docker-compose up -d
    ```

    **Please wait this might take a several minutes...**

    ```sh
    docker-compose logs -f # Follow log output
    ```

3. 다음과 같이 확인 가능합니다. :

    * [http://localhost:8000](http://localhost:8000/)
    * [https://localhost:3000](https://localhost:3000/) (HTTPS 는 기본으로 설정되어 있지 않습니다. )


4. Docker 종료

    ```sh
    docker-compose down -v
    ```
