# MLOps_project_2

- Docker images: 코드뿐만 아니라 사용자 환경 자체를 패키징하여 가져온 데이터
- Docker file: Docker image를 만드는 데 필요한 텍스트 파일

# Docker build 기본 명령어

- 폴더 생성
![image](https://github.com/TaewonEum/MLOps_project_2/assets/104436260/8c80828a-b35a-4ba0-9be8-2cf32858518c)

- 기본 명령어

1) From: 어떠한 이미지를 base image로 사용할 것인지를 명시하는 명령어

ex) From ubuntu, From ubuntu:18.04, From nginx:latest AS ngx

2) COPY: 파일 혹은 디렉토리를 다른 경로에 복사해주는 명령어

ex) COPY a.txt /some-directory/b.txt, COPY my-directory /some-directory-2

3) Run: 명시한 커맨드를 도커 컨테이너에서 실행하는 명령어

ex) RUN pip install torch, RUN pip install -r requirements.txt

4) CMD: 명시한 커맨드를 도커 컨테이너가 시작될 때, 실행하는 것을 명시하는 명령어

ex) CMD python main.py

5) WORKDIR: 이후 작성될 명령어를 컨테이너 내의 어떤 디렉토리에서 수행할 것인지를 명시하는 명령어

ex) WORKDIR /home/demo

6) ENV: 컨테이너 내부에서 지속적으로 사용될 environment variable 값을 설정하는 명령어

ex) RUN locale-gen ko_KR.UTF-8, ENV LANG ko_KR.UTF-8, ENV LANGUAGE ko_KR.UTF-8, ENV LC_ALL ko_KR.UTF-8

7) EXPOSE: 컨테이너를 뚫어줄 포트/프로토콜 지정

ex) EXPOSE 8080

# Docker image build & hub push

![image](https://github.com/TaewonEum/MLOps_project_2/assets/104436260/58f80bfb-8073-42e7-8093-536671a65c1f)

- Docker build 명령어

1) docker build -t my-image:v1.0 .(이미지 구축)

2) docker run my-image:v1.0(작동 확인)

3) docker run -d -p 5000:5000 --name registry registry(Docker 레지스트리 실행 및 로컬 접근 5000번 포트에 맵핑)

4) docker tag my-image:v1.0.0 localhost:5000/my-image:v1.0(생성한 registry에 tag)

5) docker push localhost:5000/my-image:v1.0(레지스트리에 푸시)

6) docker login-  username, password 입력

7)  docker tag my-image:v1.0 username/my-image:v1.0

8)  docker push username/my-image:v1.0

![image](https://github.com/TaewonEum/MLOps_project_2/assets/104436260/58d539cf-3d5f-4780-93b3-771649c87205)

Push된 이미지 확인
