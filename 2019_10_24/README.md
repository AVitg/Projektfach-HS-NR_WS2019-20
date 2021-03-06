# 2019_10_25
## 0  
  *  time issue, wenn die VM "durchläuft"
     *    date, diff from now()?! --> [fix](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/2019_10_24/hints/fix_time_issue.md)
  *  --log-prefix TCP/udp
     *   -A INPUT -p udp -j LOG --log-prefix "iptables DROP udp: " 
     *   [samples](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/2019_10_18/samples.iptables)

## 0.1 recap
  *   vm
  *   logstash
  *   input/filter/output plugins
  *   grok
  *   regex
  
## 1 Hands on:
  *   parsen von iptables ( name,S.address,S.port,D.address,D.port,TTL,protocol)
  *   parsen von snort logs
  *   cat iptablesyslog | sed s/'Drop udp after 23 attempts'/'Drop udp after 23 attempts:'/g > iptablesyslog.1
  *   cat iptablesyslog,1 | sed s/'Drop TCP after 17 attempts'/'Drop TCP after 17 attempts: '/g > iptablesyslog.2

## 2 "Standardisierte" Log-Formate
  * (BTW: [syslog protocol](https://tools.ietf.org/html/rfc5424))
  * [CEF](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/Library/standardized_log_formats/CEF/)
  * [LEEF]()
  * [ECS]()  
  * [Readme](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/tree/master/Library/standardized_log_formats)

## 3 index und Mapping 
  *  Was / Warum?
  
## 3.1 Mapping
  *  GET /_cat/indices?v
  *  GET /my-index/_mapping
  *  https://www.elastic.co/guide/en/elasticsearch/reference/current/indices-create-index.html
  *  https://www.elastic.co/guide/en/elasticsearch/reference/current/mapping-types.html

## 4 your own index
  *  GET /iptables-2019.10.24/_mapping
  *  put /iptables-2019.10.24/
  *  put /iptables-2019.10.24/_mapping

## 5 Visualisierung
  *  Tag Cloud SrcIP / DPort
  *  Top 5 DPorts / Least 5 DPorts
  *  Heatmap
