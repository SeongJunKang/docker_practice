# docker-network

##  docker-network �� ���� ����

### docker0 interface
docker�� ��ġ�ϰ� ifconfig docker0 ��ɾ �Է��ϸ� ������ ������ Ȯ���� �� �ִ�.<br>

![docker0](../img/docker_network_docker0.png)<br>

IP�� inet addr�� 172.17.0.1 �� �⺻ bridge network�� �����Եǰ� netmask�� 255.255.0.0���� �����ȴ�.<br>
network�� �����ϸ� 172.18.0.1 ó�� ���ڰ� �����ϰ� �ȴ�.<br>
�׸��� docker0�� docker ���ο��� �����ϴ� ���� �̴��� �긴���̴�.<br>

container�� �����ϸ� 172.17.???.???/16�� IP �뿪�� �Ҵ�ްԵȴ�.<br>
�ռ� solr�� spring-boot�� �����ϱ� ���� ������ �ۼ��ߴµ�, network�� �����ϸ� ��Ŀ ���� ip�� ������ �� �ְ�, ���� ������ �� �ְԵȴ�.