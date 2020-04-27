# Docker Tomcat War �����ϱ�

## 1. docker hub���� war ������ ���� tomcat ��������

```
docker pull tomcat:lastest
docker pull tomcat:8.5
```
![docker pull tomcat image](../img/docker_tomcat_8_5.png)<br>
�� �׸��� ���� ��Ÿ���鼭 �̹����� �ٿ�ε�˴ϴ�.

## 2. war ������ ���� Dockerfile �����

![docker pull tomcat image](../img/dockerfile_tomcat.png)<br>
��Ŀ������ �̿��Ͽ� �̹����� �����մϴ�.

RUN�� ������ ��ɾ �����մϴ�.
COPY�� ���� ��ġ������ ������ ��Ŀ �����̳� ��η� �����մϴ�.
ENV�� ȯ�漳���� ���� ��ɾ����Դϴ�.
EXPOSE�� �ش� ��Ʈ�� ����ϰڴٴ� ��ɾ��Դϴ�.

## 3. Dockerfile �����ϱ�.

��Ŀ ������ �Ϸ� �Ǿ����� Dockerfile�� �ִ� ��ġ���� �Ʒ��� ��ɾ�� �̹����� ������ �� �ֽ��ϴ�
```
docker build -t [�̹�����] .
```

## 4. ������� �̹��� �����ϱ�.

�Ʒ��� ��ɾ�� �ش� ��Ĺ �����̳ʸ� ������ �� �ֽ��ϴ�.
```
docker run -itd [�̹�����] -p 8080:8080 --name=[�����̳ʸ�]
```

--rm ��ɾ �߰��ϸ� �����̳ʰ� ����Ǹ� �ٷ� �����̳ʰ� �����Ǵ� ��ɾ��̴�.
