Install NRPE on the Linux client.
=================

## Steps

### Installing NRPE and Nagios Plugins
```
sudo apt-get install nagios-nrpe-server nagios-plugins
```
##
### NRPE Configuration
```
sudo nano/etc/nagios/nrpe.cfg
```
```
Add the IP of the Nagios server in the line, allowed_hosts=127,0,0,1,ip_servidor_nagios
```

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/0ec6979c-7670-40fc-b065-be7d314b2080)

##
### Restart NRPE
```
sudo /etc/init.d/nagios-nrpe-server restart
```

In the /etc/nagios/nrpe.cfg file you have to define the services that are going to be monitored on the server, an example would be this:

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/0b3c221d-069a-4bd9-b8e9-f8b830c52089)

```
command[check_users]=/usr/lib/nagios/plugins/check_users -w 5 -c 10
```
```
command[check_load]=/usr/lib/nagios/plugins/check_load -r -w .15,.10,.05 -c .30,.25,.20
```
```
command[check_sda3]=/usr/lib/nagios/plugins/check_disk -w 20% -c 10% -p /dev/sd
```
```
command[check_zombie_procs]=/usr/lib/nagios/plugins/check_procs -w 5 -c 10 -s Z
```
```
command[check_total_procs]=/usr/lib/nagios/plugins/check_procs -w 150 -c 200
```
```
command[check_users]=/usr/lib/nagios/plugins/check_users -w 2 -c 3
```
```
command[check_load]=/usr/lib/nagios/plugins/check_load -w 15,10,5 -c 30,25,20
```
```
command[check_mem]=/usr/lib/nagios/plugins/check_mem -f -w 10 -c 5
```
```
command[check_/dev/sda1]=/usr/lib/nagios/plugins/check_disk -w 20% -c 5% -p
/dev/sda1
```
```
command[check_/dev/sda8]=/usr/lib/nagios/plugins/check_disk -w 20% -c 5% -p /dev/sda8
```
```
command[check_smtp]=/usr/lib/nagios/plugins/check_smtp
```
```
command[check_sftp]=/usr/lib/nagios/plugins/check_sftp -H localhost -p 22 -u username -p passwordcommand[check_sftp]=/usr/lib/nagios/plugins/check_sftp -H localhost -p 22 >
```
```
command[check_smtp]=/usr/lib/nagios/plugins/check_smtp -H localhost
```


