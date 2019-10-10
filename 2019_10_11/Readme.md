#### 11.10.2019
### Importieren der VM und erste Erfahrung im Elastic (früher ELK)-Stack 

#### 1) VM import + login
- kopiere alle Daten vom USB-Sick, und gib weiter
- installiere VirtualBox 
- Importiere Virtuelle Machine von USB-Stick
- Netzwerk / NAT anpassen 127.0.0.1 / 22 / - / 22
- installiere MobaXterm
- login (ssh mittels MobaXterm) in Virtuelle Maschine
- longin (users und pw sind in der Beschreibung)
 

#### 2) ELK in a nutshell
- (E)lasticsearch, (L)ogstash, (K)ibana
  - Diagramm Zusammenspiel
- Elasticsearch
  - Suchmaschine
- Logstash
  - DatenTransport (ein- und ausgehend), Modifikation, Filter 
- Kibana
   - GUI für Elastic-Stack, nicht nur für elastricsearch


#### 3) Logstash
- wie sieht eine config Datei aus?
- https://www.elastic.co/guide/en/logstash/7.4/configuration-file-structure.html
- einfaches input output sample
  - [logstash starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/logstash/Readme.md)
  - [lab01.conf](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/logstash/LAB/config/lab01.conf)
  - [lab02.conf](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/logstash/LAB/config/lab02.conf)
  - [lab03.conf](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/logstash/LAB/config/lab04.conf)

#### 4) Elasticsearch
-  [elasticsearch starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/elasticsearch/Readme.md)
-  curl -XGET 'http://localhost:9200/'

#### 5) Kibana
 - [kibana starten](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/ELK/kibana/Readme.md)
 - einloggen browser via 'http://localhost:5601'




