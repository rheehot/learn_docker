# 4. Docker Hub 알아보기

Docker 레지스트리 작업에 대해서 알아보도록 하겠습니다.   
Docker 툴셋은 아래처럼 구성되어 있습니다.

1. Docker 데몬
2. Docker 클라이언트
3. Docker 허브

Docker Architecture는 아래처럼 구성 됩니다.

![](https://lh5.googleusercontent.com/kZRVOt04wGxwuc4j93lhoQJ7GheNv_MAMjDAMvtn1OB9OFZStFdbixlIt4I0e7pf4KDMB88vx5k3qTQA4Z1UhOYOticD7o_3_KDmsQWTZvRqZ0iHFSC3tG6MM8_J-HOihlzKY1Hh)

위의 그림에서 레지스트리 부분에 초점을 맞추겠습니다. 레지스트리는 허브라고도 합니다. 따라서 이 문서에서는 두 용어를 서로 바꿔서 사용할 수 있습니다.

Docker는 공용 Docker 이미지 목록을 찾을 수 있는 Docker Registry\(Hub\)라는 공용 저장소를 호스팅합니다. 많은 개발자들이 이미지를 준비해 주었기에 상당히 편리합니다. 이미지를 가져와서 컨테이너를 시작하기만 하면 되기 때문입니다.

개발자에게 미치는 영향은 엄청납니다. 로컬에서 필요한 애플리케이션을 다운로드/설정하는 시간이 크게 줄어 듭니다. 예를 들어서 MySQL을 사용해야 한다고 가정 합시다. 사용 가능한 방법 중 하나는 공식 MySQL 사이트에서 설치 프로그램을 다운로드 하는 것입니다. 그리고 설치 가이드에 따라 설치하고 설정을 합니다. 이 프로세스는 시간이 오래 걸리고 오류가 발생할 여지가 존재합니다.

반면, 컨테이너는 Docker와 같은 툴체인을 사용하여 쉽게 빠르게 작업을 할 수 있습니다. 이를 위해서는 아래의 단계를 수행해야 합니다.

1. Docker Hub 방문: [https://hub.docker.com](https://hub.docker.com)
2. 허브에 가입하면 로컬에서 생성한 Docker 이미지를 허브에 Push할 수 있습니다. 이는 본인 뿐만아니라 다른 누군가에게도 도움이 됩니다.
3. 위의 사이트에 등록된 Docker 이미지 목록을 확인해보세요.

