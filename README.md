 Manual NAGIOS y NRPE 
=================

### Authors (Autores)

| Author                | Origin                               |
| --------------------- | ------------------------------------ |
| Brandon Arias    | UniBarranquilla - IUB                |
| Jorge Cerra           | UniBarranquilla - IUB                |



<h3>How to install Nagios on Ubuntu 20.04</h3>

### Abstract (Resumen)


Nagios is a prominent open source tool that provides network monitoring capabilities. This system is essential for monitoring routers, servers, applications and services, ensuring that they are operating optimally. In case of failures, Nagios sends notification alerts through various methods to prevent further damage. In addition, it offers visual representations and reports that make it easy to understand monitoring results.

The Nagios architecture is based on a main server that hosts the Nagios core, which uses plugins to interact with remote hosts. These hosts, in turn, have an agent such as NRPE installed to allow communication with the main server.
### Screenshots (Pantallazos)

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/be3f6481-ebfa-488c-84ce-6f3252825a71)


### TOOLS TIC'S (Herramientas TIC'S)
- Ubuntu server 20.04
- VirtualBox
- Putty

### Status (Estado del trabajo)

| Status            | Description                          |
| ----------------- | ------------------------------------ |
| <img src="https://img.shields.io/badge/Study%20Status-Design%20Finalized-brightgreen.svg" alt="Study Status: Design Finalized"> | The study was finished | 

### Keyworks (Palabras claves)

- Server
- Nagios
- Ubuntu
- Monitoring
- Network monitoring
- System alerts
- Infrastructure management
- Remote monitoring
- Task automation
- Problem diagnosis
- Network security
- Performance reports
### Requirements (Requisitos)

- An Ubuntu 20.04 server. (use Oracle VirtualBox to make a virtual machine on your PC)
- Root access on your server to install and deploy services. Or a user with sudo privileges

## Steps

### Step 1: Update the system

Make sure all package lists are up to date as follows:
```
sudo apt update
```

Update system packages to their latest versions:
```
sudo apt upgrade
```
##
### Step 2: Install the prerequisite packages

The following prerequisite packages are required when installing Nagios Core.
```
sudo apt install wget unzip vim curl gcc openssl build-essential libgd-dev libssl-dev libapache2-mod-php php-gd php apache2
```
##
### Step 3: Download Nagios Core on Ubuntu 20.04
Download the Nagios core. To download and extract Nagios Core run the command:
```
export VER="4.4.6"
```
Then use the curl command as follows.
```
curl -SL https://github.com/NagiosEnterprises/nagioscore/releases/download/nagios-$VER/nagios-$VER.tar.gz | tar -xzf -
```
This downloads a directory called nagios-4.4.6 to your current working directory.

![image-2-1024x110](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/3ff1690b-b6b7-4748-97e9-348ec7489281)
##
### Step 4: How to install Nagios on Ubuntu
Install Ubuntu by compiling from source code.

### Usage (Por qué es importante usarlo)

- Maintaining system availability: Nagios constantly monitors routers, servers, applications and services, ensuring they are operating optimally. This helps prevent unplanned disruptions to critical systems and services.
- Early problem detection: Nagios quickly detects any failure or anomaly in the monitored systems. This allows system administrators to take corrective action before problems become critical or impact end users.
- Prevention of further damage: In case of failures, Nagios sends notification alerts through various methods, such as email, SMS or integration with ticketing systems. This allows IT operations teams to respond quickly and minimize business impact.
- Facilitates decision making: Nagios offers visual representations and reports that make it easier to understand monitoring results. This helps system administrators identify trends, analyze performance, and make informed decisions about IT infrastructure.
  
### FAQ (Preguntas y respuestas)


**1. What is Nagios and what is it used for?**

   Nagios is an open source network monitoring tool used to monitor routers, servers, applications and services. It is used to ensure that these systems are in optimal operation and to detect any failures or anomalies in them.

**2. What is the basic architecture of Nagios?**
   
   The Nagios architecture is based on a main server that hosts the Nagios core. This kernel uses plugins to interact with remote hosts, which have an agent such as NRPE installed to allow communication with the main server.
   
**3. What type of alerts can Nagios send in case of failures?**
   
   Nagios can send notification alerts through various methods, such as email, SMS, or integration with ticketing systems. This allows IT operations teams to respond quickly and minimize business impact.
   
**4. What are some of the key features of Nagios?**
   
   Some key features of Nagios include the ability to monitor various types of devices and services, reporting and visual representations, scalability, and extensibility through plugins.
   
**5. How can I install Nagios on Ubuntu 20.04?**
   
   You can install Nagios on Ubuntu 20.04 by following the steps detailed in the official Nagios documentation or in tutorials available online. This involves installing the main Nagios server, configuring the necessary plugins and agents, and making the appropriate configuration to monitor your systems.
   
### Contacts (Contactos)

Place text here

### Acknowledgements (Agradecimientos)
