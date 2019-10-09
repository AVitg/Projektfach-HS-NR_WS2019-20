OS Changes:

  * /etc/sysctl.conf 
    * vm.max_map_count=262144 


  * /etc/security/limits.d/20-nproc.conf 

     *         soft    nofile      65535    
     *         hard    nofile      65535

 * firewall
    firewall-cmd --zone=public --add-port=9200/tcp --permanent 
