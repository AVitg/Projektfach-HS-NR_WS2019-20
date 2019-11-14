#
# 1 Metasploitable
* NET-Netzwerk in VirtualBox konfigurieren
  * File/Properties/Network ...
  * beide VMs entsprechend konfigurieren
* Datei von USB stick kopieren und in Virtualbox/vmware importieren o.ä.
* VM starten und per Natting auf port 22 und port 80 erreichbar machen
* msfadmin/msfadmin

## 1.2 In Metasploitable ( Ubuntu Hardy Heron == 8.04 LTS (2008)) 
* Firewall beispielhaft "aufsetzen"
  * iptables-save > iptables.dump [hier](iptables.dump)
  * iptables-restore < iptables.dump
* erzeuge eine ca. 100mb grosse Datei in /var/www/ mit zufälligem Inhalt
* lade die Datei auf deinen Rechner herunter via des installierten Webservers  

## 1.3 in Metasploitable
* filebeat installieren und konfigurieren, elasticsearch als destination eintragen
* ./filebeat setup -e 
   * dauert etwas
* https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-modules-quickstart.html
* https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-module-apache.html
* filebeat starten, elastic search und kibana anpassen, so dass sie "erreichbar sind" (config files)
* events in kibana? suchen, testen!
* date?!


# 2 in Elastic-VM
* download metasploit
 * curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall &&   chmod 755 msfinstall &&  sudo  ./msfinstall
* starte msfconsole
* Exploite die php-Lücke in Metasploitable (hint 2012)
 * search, use, show options, RHOST, RPORT, set payload, set LHOST (nicht 127.0.0.1)


## in Kibana
* http://127.0.0.1:5601/app/kibana ?
* events in kibana? suchen, testen!
* date?!

## watcher
* https://www.elastic.co/videos/watcher-lab-creating-your-first-alert
* https://www.elastic.co/guide/en/x-pack/6.2/watcher-getting-started.html
* https://www.elastic.co/blog/introducing-logstash-input-http-plugin




# Install Nessus
* Nessus vom [github](nessus/Nessus-8.8.0-es7.x86_64.rpm) laden
* per "scp" in die VM kopieren
* sudo yum install Nessus-8.8.0-es7.x86_64.rpm
* sudo service nessusd start
* [follow](https://docs.tenable.com/nessus/Content/ConfigureNessus.htm) 
* https://127.0.0.1:8834/
   * nessus essentials
   * register account
   * akitvierungscode aus mail ins WebFormular eingeben... Tee trinken gehn
   


