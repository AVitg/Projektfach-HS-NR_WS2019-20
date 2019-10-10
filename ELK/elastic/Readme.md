# Elasticsearch parameters

- Start elasticsearch with
   - ./elasticsearch-7.4.0/bin/elasticsearch -E network.host=0.0.0.0
  


- Elasticsearch default heap size, is 1GB, change to 512MB. 
   - elasticsearch/config/jvm.options 
   - Update both min (-Xms) and max (-Xmx) heap sizes to 512MB


