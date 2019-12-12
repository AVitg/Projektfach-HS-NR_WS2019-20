https://www.elastic.co/guide/en/elasticsearch/reference/current/rpm.html
https://www.elastic.co/guide/en/kibana/current/rpm.html

install elasticsearch, kibana,  filebeat


vi /etc/elasticsearch/elasticsearch.yml
change:
node.name: node-1
cluster.initial_master_nodes: ["node-1"]

logs:
/var/log/elasticsearch/



filebeat modules enable system
filebeat setup -e

check for data in filebeat

GET _nodes/stats/ingest

https://sysdig.com/blog/detecting-cve-2019-14287/

enable 30-days trial

add watcher

https://www.elastic.co/guide/en/elasticsearch/reference/7.5/watching-meetup-data.html

POST _watcher/watch/meetup/_execute
