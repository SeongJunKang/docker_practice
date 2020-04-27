# Spring Boot docker �����

## 1. ������ ��Ʈ jar ���� ����

������ ��Ʈ�� jar ���Ϸ� �����Ͽ� Dockerfile�� ����ϴ�.

## 2. Dockerfile

```
FROM java:8

ARG JAR_FILE=spring-boot-docker.jar 
ADD ${JAR_FILE} spring-boot-docker.jar
ENTRYPOINT ["java", "-jar", "spring-boot-docker.jar"]
```

ARG�� ���𺯼��� �� �� �ֽ��ϴ�.<br>
ADD�� �ش� ������ �����̳ʿ� �߰��Ѵٴ� �ǹ��Դϴ�.<br>
RUN, CMD, ENTRYPOINT�� ��� ��ɾ �����ϴ� ��ɾ��Դϴ�.<br>
RUN. ���ο� ���̾�� ��ɾ �����ϰ�, ���ο� �̹����� �����մϴ�. ���� ��Ű�� ��ġ � ���ȴ�. e.g. apt-get<br>
CMD. default ����̳� �Ķ���͸� �����մϴ�. docker run ���� �� ������ Ŀ�ǵ带 ���� ������ �� default ����� ����˴ϴ�. 
�׸��� ENTRYPOINT�� �Ķ���͸� ������ ���� �ֽ��ϴ�. CMD�� �ֿ뵵�� �����̳ʸ� ������ �� ����� default�� �����ϴ� ���Դϴ�.<br>
ENTRYPOINT. �����̳ʸ� ������ �� �ְ� �����մϴ�.<br>

## 3.Dockerfile �����ϱ�
```
docker build -t [�̹�����] .
```

## 4.������ �̹��� �����ϱ�
�Ʒ��� ��ɾ�� �ش� ��Ĺ �����̳ʸ� ������ �� �ֽ��ϴ�.
```
docker run -itd [�̹�����] -p 8080:8080 --name=[�����̳ʸ�] 
```
env�� ���� ȯ�溯���� �߰��� �� �ֽ��ϴ�.
