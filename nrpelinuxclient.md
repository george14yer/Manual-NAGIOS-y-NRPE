Install NRPE on the Linux client.
=================



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

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/5b213db3-5a81-48f4-b5d7-66b356d36691)
##
### Step 4: How to install Nagios on Ubuntu
We are going to install Ubuntu by compiling from source code. So, first of all, go to the Nagios directory:
```
cd nagios-4.4.6
```
Next, run the configuration script:
```
./configure
```
This will take a few seconds and make sure you get an example output shown below towards the end.

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/30e38771-c613-4c32-b93e-0fa3ebf3d521)

To compile the main program along with the CGIs, run the make all command as follows.
```
sudo make all
```
Next, create the group users as follows.
```
sudo make install-groups-users
```
```
sudo usermod -a -G nagios www-data
```

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/2d653ba7-1a46-4189-b198-7d6e6bcf207c)

Next, install Nagios Core 4.x on your Ubuntu 20.04 system
```
sudo make install
```

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/bb268ec4-0fbc-4497-916e-451178609834)

Towards the end, some additional instructions will print as shown above.

Therefore, run the following command to install the init script to the /lib/systemd/system 
```
sudo make install-init
```
Next, install and configure permissions on the directory that contains the external command file.
```
sudo make install-commandmode
```
Next, install the example configuration files in /usr/local/nagios/etc/
```
sudo make install-config
```
At this point, activate the Apache module necessary for the Nagios web interface
```
sudo make install-webconf
```
```
sudo a2enmod rewrite cgi
```
```
sudo systemctl restart apache2
```
Also, feel free to install the Nagios exfoliation theme as follows:
```
sudo make install-exfoliation
```
For the classic Nagios theme, run the following command.
```
sudo make install-classicui
```
##
### Step 5: Create a Nagios access web user
You need to create a login user that will be used to log in to the Nagios interface. We will create a user named nagiosadmin using the command.
```
sudo htpasswd -c /usr/local/nagios/etc/htpasswd.users nagiosadmin
```
You will be asked to provide a password for the user and confirm it.

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/2682c07b-226b-49e8-bbcf-a106a9eee500)

The password is written to the file
```
/usr/local/nagios/etc/htpasswd.users.
```
##
### Step 6: Install the Nagios plugins
Plugins are used to extend the functionality of Nagios. You can check out the latest plugins from GitHub.

To download the plugins, run the command
```
VER="2.3.3"
```
```
curl -SL https://github.com/nagios-plugins/nagios-plugins/releases/download/release-$VER/nagios-plugins-$VER.tar.gz | tar -xzf -
```

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/f23108c8-d5b1-4988-9ad4-359da0bb5b45)

In your current working directory, you will have another directory – nagios-plugins-2.3.3

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/3d4bc64f-69e6-4bd5-bb48-4ded5e0e7a4b)

To install the plugins, navigate to the plugins source directory:
```
cd nagios-plugins-2.3.3
```
Next, compile the Nagios plugins from source as follows:
```
./configure --with-nagios-user=nagios --with-nagios-group=nagios
```
```
sudo make install
```
Una vez terminada la instalación verifica que todas las configuraciones estén en orden como se muestra.
```
sudo /usr/local/nagios/bin/nagios -v /usr/local/nagios/etc/nagios.cfg
```

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/425b2774-26a4-43f9-aea7-3801da282dfe)

##
### Step 7: Start and enable the Nagios daemon
With all the configurations established and ready, proceed to start the nagios service as follows:

To start the Nagios service run:
```
sudo systemctl enable --now nagios
```
Confirm that the Nagios service is running.
```
sudo systemctl status nagios
```

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/41077cf1-e058-427f-997b-bc4a9d72c765)

The output confirms that Nagios is working.
##
### Step 8: Access Nagios
Finally, we reach the last step where we will access Nagios. To do this, simply open your web browser and go to the displayed URL.
```
http://ip_servidor/nagios
```
You will be asked to authenticate in the pop-up window that appears. Use the credentials you provided in step 5 and click the “Sign In” button.

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/b970af8d-50d5-4ead-9bae-a6839a39163f)

Once authenticated, you will be taken to the control panel shown below.

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/be3f6481-ebfa-488c-84ce-6f3252825a71)

##
### Step 9:Enable port 80 in Nagios Server Firewall
```
ufw allow 80
```
