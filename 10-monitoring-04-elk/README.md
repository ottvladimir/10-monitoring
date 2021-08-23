# Домашнее задание к занятию "10.04. ELK"

## Задание 1

`$ docker ps
CONTAINER ID   IMAGE                                                  COMMAND                  CREATED         STATUS         PORTS                                        NAMES  
f4e923cb7928   docker.elastic.co/beats/filebeat:7.2.0                 "/usr/local/bin/dock…"   7 minutes ago   Up 7 minutes                                                filebeat  
9ce8020bb669   docker.elastic.co/kibana/kibana:7.11.0                 "/bin/tini -- /usr/l…"   7 minutes ago   Up 7 minutes   0.0.0.0:5601->5601/tcp                       kibana  
f7e39fad9dd9   docker.elastic.co/logstash/logstash:6.3.2              "/usr/local/bin/dock…"   7 minutes ago   Up 7 minutes   5044/tcp, 9600/tcp, 0.0.0.0:5046->5046/tcp   logstash  
b1835d78a469   docker.elastic.co/elasticsearch/elasticsearch:7.11.0   "/bin/tini -- /usr/l…"   7 minutes ago   Up 7 minutes   0.0.0.0:9200->9200/tcp, 9300/tcp             es-hot  
2fe6b04e9e9b   python:3.9-alpine                                      "python3 /opt/run.py"    7 minutes ago   Up 7 minutes                                                some_app  
aef62b2593e6   docker.elastic.co/elasticsearch/elasticsearch:7.11.0   "/bin/tini -- /usr/l…"   7 minutes ago   Up 7 minutes   9200/tcp, 9300/tcp                           es-warm`   

![img](IMG_20210823_115657_668.jpg)

## Задание 2


Перейдите в меню [создания index-patterns  в kibana](http://localhost:5601/app/management/kibana/indexPatterns/create)
и создайте несколько index-patterns из имеющихся.

Перейдите в меню просмотра логов в kibana (Discover) и самостоятельно изучите как отображаются логи и как производить 
поиск по логам.

В манифесте директории help также приведенно dummy приложение, которое генерирует рандомные события в stdout контейнера.
Данные логи должны порождать индекс logstash-* в elasticsearch. Если данного индекса нет - воспользуйтесь советами 
и источниками из раздела "Дополнительные ссылки" данного ДЗ.
 
---

### Как оформить ДЗ?

Выполненное домашнее задание пришлите ссылкой на .md-файл в вашем репозитории.

---

 
