# 0 Lange nicht da - Alles Okay?
## 0.1 läuft unser "Stack" noch?
  *  systemctl status elasticsearch
  ![image](images/systemctl_elasticsearch.PNG)
  *  systemctl status kibana
  ![image](images/systemctl_kibana.PNG)
  *  systemctl status auditbeat
  ![image](images/systemctl_auditbeat.PNG)

*  netstat -tuan |grep -E "5601|9300|9200"

