# Projektfach_18_10_2019
## 0
  * yum install net-tools
  * vm bitte noch [anpassen](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/tree/master/OS/configchanges)

## 1 Recap
  * VM starten, login via ssh, evtl. port 22022 sonst 22, [logstash starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/logstash/LAB/config/lab03.conf)
  *    head iptablesyslog  | nc localhost 22514
  * Regex Exkurs [LINK](http://www.regex101.com)
  *  [samples](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/2019_10_18/samples.iptables)

## 2 GROK/iptables

  * [regex in GROK oder eigene "patterns"](https://www.elastic.co/guide/en/logstash/7.4/plugins-filters-grok.html#_custom_patterns)
  * [Liste von Grok Patterns](https://github.com/logstash-plugins/logstash-patterns-core/blob/master/patterns/grok-patterns)
  * erweitert [die Datei](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/2019_10_11/hints/hint3.conf) um source.port, destination.port  
  * wie viele __verschiedene__ log messages hat unsere Sample Datei?
    * Tipp: "grep -v"
    * [hint](https://github.com/AVitg/Projektfach_18_10_2019/blob/master/GROK/hint_grok.png)  
  * iptables logs "vollständig" parsen
  *   was heisst vollständig?


## 3 "Standardisierte" Log-Formate
  * (BTW: [syslog protocol](https://tools.ietf.org/html/rfc5424))
  * [CEF](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/Library/standardized_log_formats/CEF/)
  * [LEEF]()
  * [ECS]()  
  * [Readme](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/tree/master/Library/standardized_log_formats)


## 4  GROK/snort logs
  * samples/snort/snortsyslog
  * und iptables?

## 5 Elastic-Stack, jetzt aber...

#### 5.1 Elasticsearch
*  [elasticsearch starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/elasticsearch/Readme.md)
*    curl -XGET 'http://localhost:9200/'

#### 5.2 Kibana
  * [kibana starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/kibana/Readme.md)
  * [vm firewall anpassen](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/2019_10_18/samples.iptables)
  * VirtualBox Port-Weiterleitung einrichten (NAT)
  * einloggen via Browser  [http://localhost:5601](http://localhost:5601)

#### 5.3 Logstash
  * [logstash starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/logstash/Readme.md)
  *  output nach elasticsearch und stdout
  *    [hint1](https://www.elastic.co/guide/en/logstash/7.4/output-plugins.html)
  *    [hint2](https://www.elastic.co/guide/en/logstash/7.4/plugins-outputs-elasticsearch.html)
  *    [hint3](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/2019_10_18/hint3.conf)
  * Suche der Daten in Kibana
    *  index  
