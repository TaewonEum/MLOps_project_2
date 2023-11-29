# MLOps_project_2

- Docker images: 코드뿐만 아니라 사용자 환경 자체를 패키징하여 가져온 데이터
- Docker file: Docker image를 만드는 데 필요한 텍스트 파일

# Docker file write

- 폴더 생성
![image](https://github.com/TaewonEum/MLOps_project_2/assets/104436260/8c80828a-b35a-4ba0-9be8-2cf32858518c)

- 기본 명령어

1) From: 어떠한 이미지를 base image로 사용할 것인지를 명시하는 명령어

ex) From ubuntu, From ubuntu:18.04, From nginx:latest AS ngx

2) COPY: 파일 혹은 디렉토리를 다른 경로에 복사해주는 명령어

ex) COPY a.txt /some-directory/b.txt, COPY my-directory /some-directory-2
