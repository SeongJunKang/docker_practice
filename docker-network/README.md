# docker-network

##  docker-network �� ���� ����

### docker0 interface
docker�� ��ġ�ϰ� ifconfig docker0 ��ɾ �Է��ϸ� ������ ������ Ȯ���� �� �ִ�.<br>

![docker0](../img/docker_network_docker0.png)<br>

IP�� inet addr�� 172.17.0.1 �� �⺻ bridge network�� �����Եǰ� netmask�� 255.255.0.0���� �����ȴ�.<br>
network�� �����ϸ� 172.18.0.1 ó�� ���ڰ� �����ϰ� �ȴ�.<br>
�׸��� docker0�� docker ���ο��� �����ϴ� ���� �̴��� �긴���̴�.<br>

container�� �����ϸ� 172.aa.xxx.xxx/16�� IP �뿪�� �Ҵ�ȴ�.<br>
aa�� network�� ������ȣ�� ���� ��Ʈ��ũ�� ���� �Ҵ�ȴ�.<br>
�ռ� [solr�� spring-boot�� ����](https://github.com/SeongJunKang/doicker_practice/tree/master/solr)�ϱ� ���� ������ �ۼ��ߴµ�,<br>
spring-boot���� solr �˻��� ���� url�� ȣ���� �� network�� �����Ͽ� ��Ŀ ���ο��� ip�� ������ �� �ְ�, ���� ������ �� �ְ� �ȴ�.<br>
�� ������ ������ ���� �ܺ�IP�� ��Ʈ�� �̿��Ͽ� solr�� �����߰�, docker�� ���鼭 docker ���� ��Ʈ��ũ ������ ���� �����ϸ鼭 ������ �����̴�.<br>