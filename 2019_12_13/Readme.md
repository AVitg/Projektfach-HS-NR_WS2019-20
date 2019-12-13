# Installiere Elastic Search 7.5 , kibana und filebeat 
*  https://www.elastic.co/guide/en/elasticsearch/reference/current/rpm.html
*  https://www.elastic.co/guide/en/kibana/current/rpm.html

*  yum install elasticsearch kibana filebeat

# Konfiguriere elastic
 * vi /etc/elasticsearch/elasticsearch.yml
    *  change:
    *  node.name: node-1
    * cluster.initial_master_nodes: ["node-1"]

*  logs:
    * /var/log/elasticsearch/

# Konfiguriere filebeat
*  filebeat modules enable system
*  filebeat setup -e

* filebeat data in Kibana sichtbar?

(kein hint: GET _nodes/stats/ingest)

# Erzeugen und finden von CVE-2019-14287 

*  https://sysdig.com/blog/detecting-cve-2019-14287/

* Kibana, lizenzmanagement:
    * enable 30-days trial
*  add watcher
*  https://www.elastic.co/guide/en/elasticsearch/reference/7.5/watching-meetup-data.html
* Watcher Ausführe 
    * POST _watcher/watch/..watchername../_execute
