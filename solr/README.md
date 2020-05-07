# Solr ��ġ�ϱ�

## 1. Solr docker pull

Solr docker image�� �����´�.
```
docker pull docker.io/solr:7-slim
```

## 2. Dockerfile�� �����Ͽ� solr �̹����� �����Ѵ�.

```
FROM docker.iod/solr:7-slim

# solr�� ���¼Һм��⸦ �ش� ��η� �����Ѵ�.
ADD ���¼Һм����÷����� /opt/solr/server/solr-webapp/webapp/WEB-INF/lib/
```

## 3.Dockerfile �����ϱ�
```
docker build -t solr-7 .
```

## 4.������ �̹��� �����ϱ�
�Ʒ��� ��ɾ�� �ش� Solr �����̳ʸ� ������ �� �ֽ��ϴ�.
```
docker run -itd solr-7 -p 8983:8983 --name="solr-7-container"
```
## 5.  solr-core host�� �����Ͽ� �����ϱ�
```
docker cp solr-7-container:/opt/solr/server/solr /usr/local/solr/cores
```


## 6.  docker-compose�� �����ϱ�

```
version: '3.4'

services:
  solr-7-container:
    image: solr-7
    build:
      context: /usr/local/docker/solr-7
      dockerfile: /usr/local/docker/solr-7/Dockerfile
    container_name: solr-7-container
    volumes:
      - type: bind
        source: /usr/local/solr/cores
        target: /opt/solr/server/solr
    ports:
      - "8983:8983"
    environment:      
      TZ: "Asia/Seoul"
      SOLR_JAVA_MEM: "-Xms1g -Xmx2g"
```


## 7. spring-boot �� solr container network �����ϱ�
```
version: '3.4'
networks:
  solr-network:
    driver: bridge
    ipam:
      driver: default
      
services:
  solr-7-container:
    image: solr-7
    build:
      context: /usr/local/docker/solr-7
      dockerfile: /usr/local/docker/solr-7/Dockerfile
    container_name: solr
    volumes:
      - type: bind
        source: /usr/local/solr/cores
        target: /opt/solr/server/solr
    ports:
      - "8983:8983"
    environment:      
      TZ: "Asia/Seoul"
      SOLR_JAVA_MEM: "-Xms1g -Xmx2g" 
    network:
      - solr-network
      
  spring-boot-docker:
    image: spring-boot-docker
    build:
      context: /usr/local/docker/spring-boot-docker
      dockerfile: /usr/local/docker/spring-boot-docker/Dockerfile
    container_name: web
    volumes:
      - type: bind
        source: /usr/local/docker/spring-boot-docker/files
        target: /usr/local/share/files
    ports:
      - "8080:8080"
    environment:
      SPRING_PROFILES_ACTIVE: production
    network:
      - solr-network
```

ip ��������� �ƴ� container ��ĵ� �ִ� �� ������ ���� Ȯ������ ���ߴ�.
�� docker�� �����ϸ� network�� ����µ� �Ʒ� ��ɾ�� Ȯ���� �� �ִ�.
```
docker network ls
```

�ڼ��� ������ ��������� �Ʒ��� ��ɾ ����ϸ� ��Ŀ ������ ip�� Ȯ���� �� �ִ�.
web���� �ش� ip�� ����Ͽ� solr �˻��� ���� �� �ֵ��� �����ؾ��Ѵ�. ȯ�溯���� �̿��ؼ� ����� �� �� �ִ�.
```
docker network inspect [name]
```

![docker inspect for network](../img/docker-solr.png)<br>
