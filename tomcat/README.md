# Docker Tomcat War �����ϱ�

## 1. docker hub���� war ������ ���� tomcat ��������

```
docker pull tomcat:lastest
docker pull tomcat:8.5
```
![docker pull tomcat image](../img/docker_tomcat_8_5.png)
�� �׸��� ���� ��Ÿ���鼭 �̹����� �ٿ�ε�ȴ�.

## 2. war ������ ���� Dockerfile �����

![docker pull tomcat image](../img/dockerfile_tomcat.png)
��Ŀ������ �̿��Ͽ� �̹����� �����Ѵ�.

RUN�� ������ ��ɾ �����Ѵ�.
COPY�� ���� ��ġ������ ������ ��Ŀ �����̳� ��η� �����Ѵ�.
ENV�� ȯ�漳���� ���� ��ɾ��̴�.
EXPOSE�� �ش� ��Ʈ�� ����ϰڴٴ� ��ɾ��.

��Ŀ ������ �Ϸ� �Ǿ����� Dockerfile�� �ִ� ��ġ���� �Ʒ��� ��ɾ�� �̹����� ������ ���ִ�
```
docker build -t [�̹�����] .
```

## 3. ������� �̹��� �����ϱ�.

�Ʒ��� ��ɾ�� �ش� ��Ĺ �����̳ʸ� ������ �� �ִ�.
```
docker run -itd [�̹�����] -p 8080:8080 --name=[�����̳ʸ�]
```