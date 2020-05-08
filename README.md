# Docker ��ɾ� ����

## 1. ��Ŀ ��ġ�ϱ�

Docker�� ������ ������ ������ �ڵ����� �ν��ؼ� ��Ű���� ��ġ���ִ� ��ũ��Ʈ�� �����մϴ�.
```
$ sudo wget -qO- https://get.docker.com/ | sh
```
���� MacOS�� ��ġ [��Ŀ ��ġ for MacOS](https://hub.docker.com/editions/community/docker-ce-desktop-mac/)�� ��ġ�߽��ϴ�.

## 2. ��Ŀ ����Ȯ��

```
docker --version
```
��� ��

![docker --version img](./img/docker_version.png)<br>

�Ʒ��� docker�� ����� �����Դϴ�.

## 3. ����� ��Ŀ �����̳ʷ� �����ϱ�

```
docker exec -it [container��] /bin/bash Ȥ�� "bash"
```

## 4. docker run�� ���Ǵ� ��ɾ� ����
-c, --cpu-shares=0: CPU �ڿ� �й� �����Դϴ�. ������ �⺻ ���� 1024�̸� �� ���� ��������� ����˴ϴ�. <br>
-d, --detach=false: Detached ����Դϴ�. ���� ���� ����� �θ��� �����̳ʰ� ��׶���� ����˴ϴ�.  <br>
-e, --env=[]: �����̳ʿ� ȯ�� ������ �����մϴ�. ���� ���� ���̳� ��й�ȣ�� ������ �� ����մϴ�. <br>
--entrypoint="": Dockerfile�� ENTRYPOINT ������ �����ϰ� ������ �ٸ� ���� �����մϴ�. <br>
--expose=[]: �����̳��� ��Ʈ�� ȣ��Ʈ�� ���Ḹ �ϰ� �ܺο��� �������� �ʽ��ϴ�. <br>
-i, --interactive=false: ǥ�� �Է�(stdin)�� Ȱ��ȭ�ϸ� �����̳ʿ� ����(attach)�Ǿ� ���� �ʴ��� ǥ�� �Է��� �����մϴ�. ���� �� �ɼ��� ����Ͽ� Bash�� ����� �Է��մϴ�. <br>
--link=[]: �����̳ʳ��� �����մϴ�. &lt;�����̳� �̸�&gt;:&lt;��Ī&gt; �����Դϴ�. <br>
-m, --memory="": �޸� �Ѱ踦 �����մϴ�. &lt;����&gt;&lt;����&gt; �����̸� ������ b, k, m, g�� ����� �� �ֽ��ϴ�.<br>
--rm=false: �����̳� ���� ���μ����� ����Ǹ� �����̳ʸ� �ڵ����� �����մϴ�. -d �ɼǰ� �Բ� ����� �� �����ϴ�.<br>
-t, --tty=false: TTY ���(pseudo-TTY)�� ����մϴ�. Bash�� ����Ϸ��� �� �ɼ��� �����ؾ� �մϴ�. �� �ɼ��� �������� ������ ����� �Է��� ���� ������ ���� ǥ�õ��� �ʽ��ϴ�. <br>
-u, --user="": �����̳ʰ� ����� ������ ����� ���� �̸� �Ǵ� UID�� �����մϴ�. <br>
-v, --volume=[]: ������ ������ �����Դϴ�. ȣ��Ʈ�� ������ ���͸��� �����Ͽ� ������ �����̳ʿ� �������� �ʰ� ȣ��Ʈ�� �ٷ� �����մϴ�.<br>
-w, --workdir="": �����̳� ���� ���μ����� ����� ���͸��� �����մϴ�.<br>
--name="": �����̳ʿ� �̸��� �����մϴ�.<br>
--net="bridge": �����̳��� ��Ʈ��ũ ��带 �����մϴ�.<br>
&nbsp;�� bridge: Docker ��Ʈ��ũ �긮���� �� ��Ʈ��ũ�� �����մϴ�.<br>
&nbsp;�� none: ��Ʈ��ũ�� ������� �ʽ��ϴ�.<br>
&nbsp;�� container:<�����̳� �̸�, ID>: �ٸ� �����̳��� ��Ʈ��ũ�� �Բ� ����մϴ�.<br>
&nbsp;�� host: �����̳� �ȿ��� ȣ��Ʈ�� ��Ʈ��ũ�� �״�� ����մϴ�. ȣ��Ʈ ��Ʈ��ũ�� ����ϸ� D-Bus�� ���Ͽ� ȣ��Ʈ�� ��� �ý��� ���񽺿� ������ �� �����Ƿ� ���ȿ� ��������ϴ�.<br>

###### [��ó: ���� ���� ������ Docker 20�� - 28. run](http://pyrasis.com/book/DockerForTheReallyImpatient/Chapter20/28)

## docker�� ������ ����
### [tomcat�� �̿��� war �����ϱ�](https://github.com/SeongJunKang/doicker_practice/tree/master/tomcat)
### [spring boot �����ϱ�](https://github.com/SeongJunKang/doicker_practice/tree/master/spring_boot)
### [docker compose�� ����Ͽ� spring boot ����](https://github.com/SeongJunKang/doicker_practice/tree/master/docker-compose)
### [docker�� jenkins ��ġ�ϱ�](https://github.com/SeongJunKang/doicker_practice/tree/master/jenkins)
### [Solr ��ġ �� spring boot ����](https://github.com/SeongJunKang/doicker_practice/tree/master/solr)
