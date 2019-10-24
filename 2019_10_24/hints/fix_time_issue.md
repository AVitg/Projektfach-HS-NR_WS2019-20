## 0 fix time issue
*  yum install ntp ntpdate
*  systemctl start ntpd
*  systemctl enable ntpd
*  systemctl status ntpd
*  ntpdate -u -s 0.centos.pool.ntp.org 1.centos.pool.ntp.org 2.centos.pool.ntp.org
*  systemctl restart ntpd
*  timedatectl
*  hwclock -w
*  Quelle https://thebackroomtech.com/2019/01/17/configure-centos-to-sync-with-ntp-time-servers/