# Docker

## Docker란?
- 컨테이너 기반의 가상화 시스템 (Container-based Virtualization System)
- 운영체제 위에 Docker만 설치하면 어느 컴퓨터에서든 똑같이 돌아가는 가상 환경을 여러개 띄울 수 있다.

## Doker 설치 
- Windows
  - [Docker Desktop for Windows](https://docs.docker.com/desktop/windows/install/) 설치 
  - WSL2 활성화
    - > Windows 환경에서도 Linux를 이용할 수 있고 Docker를 사용할 수 있다.
    1. Powershell 관리자 권한으로 실행하여 ```wsl --install``` 작성
    2. ```dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart``` 입력 (Windows 옵션 활성화)
    3. ```dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart``` 입력 후 재부팅 (가상머신 기능 활성화)
    4. [Linux 커널 업데이트 패키지 다운로드](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)
    5. WSL2를 기본 버전으로 설정   
    ``` wsl --set-default-version 2 ```
  - 정상 설치 확인
    - ``` docker ps ``` 입력으로 확인


- Mac
  > Apple Silicon