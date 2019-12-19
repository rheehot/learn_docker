# 3.1 Apache 웹 서버 실행

이제 조금 더 자세히 Docker내에서 실행되는 애플리케이션을 어떻게 구상하는지 알아보도록 하겠습니다.  
우리는 Apache Web Server를 실행해야 합니다. 이렇게 하려면 누군가에 의해 이미 생성된 Docker 이미지가 있어야겠죠?

따라서 첫 번째로 아래를 수행합니다.

| `grouq:~ giljae$ docker search httpd` |
| :--- |


위의 명령어에 대한 결과는 아래와 같습니다.

| `grouq:~ giljae$ docker search httpd NAME                                 DESCRIPTION           STARS OFFICIAL AUTOMATED httpd                                The Apache HTTP Server Project                  2771 [OK] centos/httpd-24-centos7              Platform for running Apache httpd 2.4 or bui...   27 centos/httpd                                                                         26 [OK] armhf/httpd                          The Apache HTTP Server Project                  8 salim1983hoop/httpd24                Dockerfile running apache config                2                                       [OK] dariko/httpd-rproxy-ldap             Apache httpd reverse proxy with LDAP authent...   1                                     [OK] solsson/httpd-openidc                mod_auth_openidc on official httpd image, ve...   1                                     [OK] lead4good/httpd-fpm                  httpd server which connects via fcgi proxy h...   1                                     [OK] interlutions/httpd                   httpd docker image with debian-based config ...   0                                     [OK] dockerpinata/httpd                                                                   0 itsziget/httpd24                     Extended HTTPD Docker image based on the off...   0                                     [OK] manasip/httpd                                                                        0 manageiq/httpd_configmap_generator   Httpd Configmap Generator           0 [OK] appertly/httpd                       Customized Apache HTTPD that uses a PHP-FPM ...   0                                     [OK] izdock/httpd                         Production ready Apache HTTPD Web Server + m...   0 trollin/httpd                                                                        0 amd64/httpd                          The Apache HTTP Server Project                  0 publici/httpd                        httpd:latest           0 [OK] e2eteam/httpd                                                                        0 manageiq/httpd                       Container with httpd, built on CentOS for Ma...   0                                     [OK] buzzardev/httpd                      Based on the official httpd image           0 [OK] hypoport/httpd-cgi                   httpd-cgi           0 [OK] alvistack/httpd                      Docker Image Packaging for Apache               0                   [OK] ppc64le/httpd                        The Apache HTTP Server Project                  0 tugboatqa/httpd                      The Apache HTTP Server Project                  0` |
| :--- |


httpd를 검색하니 많은 이미지 목록이 출력됩니다. 이 중에서 우리는 공식 이미지를 설치할 계획입니다.  
어떻게 해야 할까요? 위에서 배운 명령어 중 docker pull을 사용합니다.

| `grouq:~ giljae$ docker pull httpd Using default tag: latest latest: Pulling from library/httpd 000eee12ec04: Pull complete 32b8712d1f38: Pull complete f1ca037d6393: Pull complete c4bd3401259f: Pull complete 51c60bde4d46: Pull complete Digest: sha256:ac6594daaa934c4c6ba66c562e96f2fb12f871415a9b7117724c52687080d35d Status: Downloaded newer image for httpd:latest docker.io/library/httpd:latest` |
| :--- |


httpd 이미지가 다운로드 되었습니다. docker images를 이용해서 확인합니다.

| `grouq:~ giljae$ docker images REPOSITORY          TAG                 IMAGE ID            CREATED     SIZE httpd               latest 2ae34abc2ed0        2 weeks ago         165MB alpine              latest 965ea09ff2eb        7 weeks ago         5.55MB` |
| :--- |


httpd 이미지에 대한 자세한 내용은 [공식 문서](https://registry.hub.docker.com/_/httpd/)를 확인하시면 됩니다. 각 이미지에 대한 설명 페이지를 살펴보는 것은 중요합니다. 해당 페이지에 이미지 실행 방법 및 기타 구성 사항에 대해서 상세하게 작성되어 있습니다.

공식 이미지에서 제공하는 Apache 웹 서버를 컨테이너에서 실행하려면 다음을 수행해야 합니다.  
아래의 명령어에는 -d 옵션을 사용하고 있습니다. \(e.g -d 옵션은 컨테이너를 분리 모드로 실행\)  
그리고 --name 옵션으로 컨테이너 이름을 지정했습니다.

| `grouq:~ giljae$ docker run -d --name apache httpd c55c64b2c763bf4d0e3670301a2afb2903479f7aa42ff84d01cb82fefd700fe7` |
| :--- |


이렇게 되면 httpd 이미지를 기반으로 기본 Apache Web Server가 시작됩니다. 컨테이너를 분리 모드로 시작했기 때문에 컨테이너 ID를 다시 얻습니다.

docker ps 명령어로 httpd가 구동되었는지 확인합니다.

| `grouq:~ giljae$ docker ps CONTAINER ID        IMAGE COMMAND              CREATED STATUS PORTS               NAMES c55c64b2c763        httpd             "httpd-foreground"   45 seconds ago      Up 44 seconds       80/tcp              apache` |
| :--- |


실행 상태입니다. NAMES에는 구동하기전 지정한 apache가 있습니다.

