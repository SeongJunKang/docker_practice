# Spring Boot docker 만들기

## 1. 스프링 부트 jar 파일 생성

스프링 부트를 jar 파일로 생성하여 Dockerfile을 만듭니다.

## 2. Dockerfile

```
FROM java:8

ARG JAR_FILE=spring-boot-docker.jar 
ADD ${JAR_FILE} spring-boot-docker.jar
ENTRYPOINT ["java", "-jar", "spring-boot-docker.jar"]
```

ARG는 선언변수로 볼 수 있습니다.<br>
ADD는 해당 파일을 컨테이너에 추가한다는 의미입니다.<br>
RUN, CMD, ENTRYPOINT는 모두 명령어를 실행하는 명령어입니다.<br>
RUN. 새로운 레이어에서 명령어를 실행하고, 새로운 이미지를 생성합니다. 보통 패키지 설치 등에 사용된다. e.g. apt-get<br>
CMD. default 명령이나 파라미터를 설정합니다. docker run 실행 시 실행할 커맨드를 주지 않으면 이 default 명령이 실행됩니다. 
그리고 ENTRYPOINT의 파라미터를 설정할 수도 있습니다. CMD의 주용도는 컨테이너를 실행할 때 사용할 default를 설정하는 것입니다.<br>
ENTRYPOINT. 컨테이너를 실행할 수 있게 설정합니다.<br>

## 3.Dockerfile 빌드하기
```
docker build -t [이미지명] .
```

## 4.생성된 이미지 실행하기
아래의 명령어로 해당 톰캣 컨테이너를 실행할 수 있습니다.
```
docker run -itd [이미지명] -p 8080:8080 --name=[컨테이너명] 
```
env를 통해 환경변수를 추가할 수 있습니다.


## 5.  docker-compose로 관리하기

```
version: '3.4'

services:
  spring-boot-docker:
    image: spring-boot-docker
    build:
      context: /usr/local/docker/spring-boot-docker
      dockerfile: /usr/local/docker/spring-boot-docker/Dockerfile
    container_name: spring-boot
    volumes:
      - type: bind
        source: /usr/local/docker/spring-boot-docker/files
        target: /usr/local/share/files
    ports:
      - "8080:8080"
    environment:
      SPRING_PROFILES_ACTIVE: production
```
