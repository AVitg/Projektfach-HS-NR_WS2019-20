# 0 Lange nicht da - Alles Okay?
## 0.1 läuft unser "Stack" noch?
  * elasticsearch  
    *  systemctl status elasticsearch
    ![image](images/systemctl_elasticsearch.PNG)
     *  sudo journalctl -u elasticsearch
     *  sudo tail -f /var/log/elasticsearch/elasticsearch.log
     *  if-not: 
         *  systemctl start elasticsearch
         *  systemctl enable elasticsearch

  * kibana   
     *  systemctl status kibana
      ![image](images/systemctl_kibana.PNG)
     *  sudo journalctl -u kibana
     *  netstat -tuan |grep 5601
     *  [http://localhost:5601/](http://localhost:5601/)
     *  if-not: 
         *  systemctl start kibana
         *  systemctl enable kibana

  * auditbeat
    *  systemctl status auditbeat
    ![image](images/systemctl_auditbeat.PNG)
    *  sudo journalctl -u auditbeat
    *  if-not: 
         *  systemctl start auditbeat
         *  systemctl enable auditbeat

## 
