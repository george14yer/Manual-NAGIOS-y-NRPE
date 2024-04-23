CONFIGURATION ON THE NAGIOS SERVER.
=================

### Create the servers directory in /usr/local/nagios/etc/
##
### Create the clients.cfg file in /usr/local/nagios/etc/servers and add the following:
```
define host {
    use                     linux-server
    host_name               client
    alias                   client
    address                 192.168.1.54
    max_check_attempts      5
    check_period            24x7
    notification_interval   30
    notification_period     24x7
}
```
```
define service {
    use                     generic-service
    host_name               client
    service_description     http
    check_command           check_http! -H 192.168.1.54 -p 4200
    notifications_enabled   1
}
```
```
define service {
    use                     generic-service
    host_name               client
    service_description     ssh
    check_command           check_ssh
    notifications_enabled   1
}
```
```
define service {
    use                     generic-service
    host_name               client
    service_description     connected users
    check_command           check_nrpe!check_users
    notifications_enabled   1
}
```
```
define service {
    use                     generic-service
    host_name               client
    service_description     SSD
    check_command           check_nrpe!check_sda3
    notifications_enabled   1
}
```
