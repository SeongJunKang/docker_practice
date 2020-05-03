# docker�� Jenkins ��ġ�ϱ�

## 1. jenkins �̹��� �ٿ�ε�

```
docker pull jenkins/jenkins:lts
```

������ ��Ʈ�� jar ���Ϸ� �����Ͽ� Dockerfile�� ����ϴ�.

## 2. �ٿ�ε�� jenkins �̹��� ����

```
docker run -d -p 8080:8080 -v /jenkins:/var/jenkins_home --name jenkins -u root \
-e JAVA_OPTS='-Duser.timezone=Asia/Seoul -Dfile.encoding=UTF-8 -Dsun.jnu.encoding=UTF-8' jenkins/jenkins:lts
```
���⼭ �ɼ��� ���캸��<br>
-d : ��׶��� ����<br>
-p : ��Ʈ ���� (������ linux / �������� container)<br>
-name : container �̸�<br>
-u : �����<br>
-e : ȯ�漳�� (���⼭�� Ÿ������ ����� ����, �⺻ jenkins�� Ÿ���� �ٸ� ������ �����Ǿ�����)<br>

## 3. jenkins �������� ����

�� �������� �����ϸ� ������ ���� ȭ���� �����µ�<br>

![jenkins �ʱ�ȭ��](../img/docker_jenkins.png)<br>

docker�� jenkins�� �����Ͽ� �ش� ��η� ���� Ȯ���Ѵ�.<br>

```
docker exec -it jenkins /bin/bash
cat /var/jenkins_home/secrets/initialAdminPassword
```
![jenkins �ʱ� ��й�ȣ](../img/docker_jenkins_init.png)<br>

## 4.�÷����� ��ġ
�÷������� ��ġ�ϰ�, ������ �����϶�� �������� ���´�.<br>
������ ������ �����ϰ� �������� �Ѿ�� ������ ������.<br>

## 5. docker-compose�� �̿��Ͽ� ����

```
version: '3.3'

services:
        jenkins:
                container_name: jenkins
                restart: always
                image: jenkins/jenkins:lts
                user: root #root Ȥ�� ������ �����ؾ� ����
                ports:
                        - '8080:8080'
                volumes:
                        - type: bind
                          source: /jenkins
                          target: /var/jenkins_home
                environment:
                      TZ: "Asia/Seoul"
```