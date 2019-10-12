# Elasticsearch parameters


- Elasticsearch default heap size, is 1GB, change to 512MB. 
   - elasticsearch/config/jvm.options 
   - Update both min (-Xms) and max (-Xmx) heap sizes to 512m (512MB)

- vm 
  -  hat noch "Fehler", bitte "[beseitigen"](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/tree/master/OS/configchanges) und reboote
  - sudo reboot
  

- Start elasticsearch mit
   - ./elasticsearch-7.4.0/bin/elasticsearch -E network.host=0.0.0.0
  
- Erreichen der rest-api via \<IP\>:9200  (Erster freier port ab 9200 bis 9299)

