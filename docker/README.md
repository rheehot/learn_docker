# Docker 설치하기

본 챕터에는 여러 섹션들이 포함되어 있으며 각 섹션은 Docker의 특정 측면에 대해서 설명합니다. 각 섹션에서는 명령어를 입력하거나 코드를 작성합니다. 본 책에서 사용된 모든 코드는 Gitlab 저장소에서 사용할 수 있습니다.

## 전제 조건

명령어 사용에 익숙하고 텍스트 편집기를 사용하는 것 외에는 이 학습에 필요한 특정 기술이 없습니다. 튜토리얼을 진행하면서 몇 가지 클라우드 서비스를 사용합니다. 아래의 사이트에서 계정을 만드세요.

* Docker Hub - [https://hub.docker.com/](https://hub.docker.com/)

## 컴퓨터 설정

컴퓨터에서 모든 툴 설정을 하는 것은 까다로운 작업 일 수 있지만, Docker가 안정적으로 제공되면서 Docker를 설치하는 것이 매우 쉬워졌습니다.

### Mac에서 Docker Desktop 설치

Docker Desktop을 다운로드 하려면 Docker Hub로 이동하여 Docker ID로 로그인 하세요.

* Docker Hub에서 다운로드 - [https://hub.docker.com/?overlay=onboarding](https://hub.docker.com/?overlay=onboarding)

#### 시스템 요구 사항

Docker Desktop을 성공적으로 설치하려면 Mac이 다음 요구 사항을 충족해야 합니다.

* Mac 하드웨어는 EPT\(확장 페이지 테이블\) 및 무제한 모드를 포함하여 MMU\(메모리 관리 장치\) 가상화를 위한 인텔의 하드웨어 지원 기능을 갖춘 2010 이상의 최신 모델이어야 합니다. 터미널에서 다음 명령어를 실행하여 지원이 가능한지 확인 할 수 있습니다.

```text
sysctl kern,.hv_support
```

* MacOS는 버전 10.13 이상이어야 합니다. 최신 버전의 MacOS로 업그레이드 하는 것이 좋습니다.
* 최소 4GB의 RAM
* 버전 4.3.30 이전의 VirtualBox는 Docker Desktop과 호환되지 않으므로 설치하지 않아야 합니다.

참고: 시스템이 위의 요구사항에 충족하지 않으면 HyperKit 대신 Oracle VirtualBox를 사용하는 Docker Toolbox를 설치할 수 있습니다.

#### 설치 프로그램에 포함된 내용

Docker Desktop 설치에는 Docker Engine, Docker CLI 클라이언트, Docker Compose, Docker Machine 및 Kitematic이 포함 됩니다.

#### Mac에서 Docker Desktop 설치 및 실행

1. Docker.dmg 파일을 두번 클릭하여 설치 프로그램에서 Docker 아이콘을 Applications 폴더로 드래그 합니다.

![](../.gitbook/assets/0%20%281%29.png)

1. Docker.app 어플리케이션을 두 번 클릭하여 Docker를 시작합니다.

상태 표시줄의 Docker 메뉴는 Docker Desktop이 실행 중이며 터미널에서 Access 할 수 있음을 나타냅니다.

![](../.gitbook/assets/1%20%281%29.png)

1. Docker 메뉴를 클릭하여 환경 설정 및 기타 옵션을 보세요.
2. Docker 정보를 선택하여 최신 버전인지 확인 하세요.

축하합니다!! 이제 Docker Desktop이 성공적으로 실행되고 있습니다.

### Windows에서 Docker Desktop 설치

[https://docs.docker.com/docker-for-windows/install/](https://docs.docker.com/docker-for-windows/install/) 참고하여 작성

### Linux에서 Docker Engine 설치

[https://docs.docker.com/install/linux/docker-ce/ubuntu/](https://docs.docker.com/install/linux/docker-ce/ubuntu/) 참고하여 작성

## 설치 완료

```text
$docker run hello-world

Hello from Docker .
This message show that your installation appears to be working correctly.
...
```

