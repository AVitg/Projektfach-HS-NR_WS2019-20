# Genral
  *     [OS-Changes](https://github.com/AVitg/Projektfach-HS-NR_WS2019-20/blob/master/OS/configchanges/Readme.md)

# Elastic
  *    Start elasticsearch:
  *    ./elasticsearch-7.4.0/bin/elasticsearch -E network.host=127.0.0.1

# Kibana
Start kibana:
  *    ./kibana-7.4.0-linux-x86_64/bin/kibana --host 0.0.0.0
  *    einloggen browser via 'http://localhost:5601'

# logstash
  *    Start logstash:
  *    ./logstash-7.4.0/bin/logstash -f config/lab.conf --config.reload.automatic

# Daten nach logstash schicken
  *    head iptablessyslog | nc localhost 22514 
