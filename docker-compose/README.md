# Docker compose 
## 0. docker compose�� ?
�������� docker container�� �ϳ��ϳ� �ٷ����ʰ�, YAML ������ �̿��Ͽ� �������� �����̳� ���α׷��� �����ϰ� �����ϱ� ���� �����Դϴ�.<br>
���� �����̳��� ������ �����ϰ�, ��ɾ� �ϳ��� docker container�� ���¸� �ٷ� �� �ֽ��ϴ�.

```
docker-compose up -d  // ��׶���� docker-compose.yml�� ���Ե� ��� �����̳ʸ� �����Ѵ�.
docker-compose down  //docker-compose.yml�� ���Ե� ��� �����̳ʸ� �����Ѵ�.
```

## 1. docker compose install

�� [��ũ](https://docs.docker.com/compose/install/)�� ���� docker-compose�� �ٿ�ε��ϰ� ��ġ�� �� �ֽ��ϴ�.<br>
OS�� ��ġ����� �ٸ��� Ȯ���Ͽ� ��ġ�� �մϴ�.

�������� ���� ��ɾ ���� docker-compose�� �ٿ�ε� �޽��ϴ�.<br>
������ �ֽ�ȭ�Ͽ� �޵��� �Ѵ�. �ֽ� ������ �� [��ũ](https://github.com/docker/compose/releases)�� ���� Ȯ���� �� �ֽ��ϴ�.
```
sudo curl -L "https://github.com/docker/compose/releases/download/1.25.5/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
```
## 2. ��ġ�� docker compose ����� �� �ֵ��� ���� ����
```
sudo chmod +x /usr/local/bin/docker-compose
```

## 3. docker-compose ���� Ȯ��
```
$ docker-compose --version
docker-compose version 1.25.5, build 1110ad01
```


## 4. docker-compose.yml ���� ����
�Ʒ��� ��ɾ ����Ͽ� commands�� Ȯ���� �� �ֽ��ϴ�.<br>
```
docker-compose --help
```
![docker compose command](../img/docker-compose-help.png)<br>
```
vi docker-compose.yml
```

## 5. docker-compose ����(������ ��Ʈ)
docker compose�� ������ ��Ʈ ��Ʈ���ϱ�<br>
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
version�� docker compose�� ������ ��Ÿ���ϴ�.<br>
services�� �����������̳��� ������ �����մϴ�.<br>
- ����� ���񽺸��� �����մϴ�.<br>
- image�� ���񽺸� ������ �� ����� image�� �Է��մϴ�.<br>
- build�� �̹����� ���� ��� image�� �����Ͽ� �����մϴ�.<br>
-- context�� dockerfile�� image�� ������ ��, �ʿ��� ���� Ȥ�� ������ ��ġ�� ������ �� ����մϴ�.<br>
-- dockerfile�� ���� ������ �̹����� dockerfile ��θ� �����մϴ�.<br>
- container_name�� ���� ���� �����̳��� �̸��� �����մϴ�.<br>
- volumes �� �����̳ʿ� ȣ��Ʈ���� ������ ������ �����մϴ�.<br>
-- source�� ȣ��Ʈ�� ���� Ȥ�� ���� ��θ� �����մϴ�.<br>
-- target�� �����̳��� ���� ��θ� �����մϴ�.<br>
- ports �� [ȣ��Ʈ port]:[�����̳� port]<br>
- environment�� ȯ�溯���� �����̳ʰ� ������ �� ����ϴ� ȯ�溯���� �Է��մϴ�.<br>
network�� �ִµ� �̴� �����̳ʰ��� ��Ʈ��ũ������ ���ؼ� ����մϴ�.(���⼱ ������)<br>