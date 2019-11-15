# 0 Blue- vs. Red-Team
As part of the United States computer security defense initiative, red teams were developed to exploit other malicious entities that would do them harm. As a result, blue teams were developed to design defensive measures against such red team activities
[wikipedia](https://en.wikipedia.org/wiki/Blue_team_(computer_security))

# 1 Blue-Team-tasks
## 1.1 Metasploitable
* Datei von USB stick kopieren und in Virtualbox/vmware importieren o.ä.
* VM starten und per Natting auf port 22 und port 80 erreichbar machen
* msfadmin/msfadmin
* testen, ob von elastic VM ping/telnet Port 80 auf metasploitable funktioniert (Ansonsten NAT-Netzwerk o.ä. einrichten) 

## 1.2 In Metasploitable - _Preparation_
* ( Ubuntu Hardy Heron == 8.04 LTS (2008)) 
* Firewall beispielhaft "aufsetzen"
  * iptables-save > iptables.dump [hier](iptables.dump)
  * iptables-restore < iptables.dump
* erzeuge eine ca. 100mb grosse Datei in /var/www/ mit zufälligem Inhalt
* lade die Datei auf deinen Rechner herunter via des installierten Webservers, beobachte dabei /var/log/messages

## 1.3 in Metasploitable - _Preperation_
* filebeat installieren und konfigurieren, elasticsearch als destination eintragen
* ./filebeat setup -e 
   * dauert etwas
* iptables und apache modul enablen und evtl. konfigurieren   
* https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-modules-quickstart.html
* https://www.elastic.co/guide/en/beats/filebeat/current/filebeat-module-apache.html
* filebeat starten (Dateirechte/Root), elastic search und kibana anpassen, so dass sie "erreichbar sind" (config files)
* events in kibana  http://127.0.0.1:5601/app/kibana ? suchen, testen!
* date?!


# 2 Red-Team-tasks - _Initial access_ 
## 2.1 in Elastic-VM
* download metasploit
 * ```url https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall &&   chmod 755 msfinstall &&  sudo  ./msfinstall ```
* starte msfconsole
* Exploite die php-Lücke in Metasploitable (hint 2012)
 * search, use, show options, RHOST, RPORT, set payload, set LHOST (nicht 127.0.0.1)

## 2.2 PHP-Lücke - _Persistence_
* manuell ohne metasploit ausnutzen und webshell hochladen (via webserver auf elasti-search vm)
* logs?, watcher? 

# 3 Blue-Team-tasks - _Identification_ 
## 3.1 in Kibana 
* Events in kibana? suchen, testen!
* date?! index, timestamp

## 3.2 watcher
* setup watcher 
  * https://www.elastic.co/videos/watcher-lab-creating-your-first-alert
  * https://www.elastic.co/guide/en/x-pack/6.2/watcher-getting-started.html
  * https://www.elastic.co/blog/introducing-logstash-input-http-plugin
* schicke die Watcher Events in einen eigenen Index


# 4 Red-Team-tasks 
## 4.1 _Discovery_ und _Exfiltration_
* nutze die webshell um dich umzusehen /etc/passwd/ /etc/shadow etc. und eine 150mb grosse Datei zu erstellen
* lade die soeben erstelle Datei herunter 


# 5 Blue-Team-tasks - _Identification_
## 5.1 watcher
* watcher für grossen Dateitransfer (x-megabyte in N-Minuten)
* watcher für "lange Verbindungen"
* eure Ideen



