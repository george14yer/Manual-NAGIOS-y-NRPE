## Step 1: Downloading NRPE Source Code

1. Go to the [official Nagios website](https://github.com/NagiosEnterprises/nrpe) and download the NRPE package.
2. On your Nagios server, open a terminal and navigate to the directory where you want to download NRPE.
3. Use the `git clone`  command to clone the NRPE repository from GitHub:

   ```
   git clone https://github.com/NagiosEnterprises/nrpe.git
   ```
## Step 2: Installing Dependencies
Install the necessary tools and libraries to compile NRPE. On Debian/Ubuntu-based systems, you can use the following command:

```
sudo apt-get update
sudo apt-get install -y autoconf automake gcc libc6 libmcrypt-dev make libssl-dev wget dc build-essential

```
## Step 3: Compiling and Installing NRPE
Navigate to the nrpe directory created after cloning:
```
cd nrpe

```
Run the configuration script:
```
./configure --enable-command-args

```
Compile NRPE:
````
make all
````

Install NRPE and its plugins:
```
sudo make install
````
## Step 4: NRPE Configuration
Edit the nrpe.cfg configuration file located in /usr/local/nagios/etc/:

````
sudo nano /usr/local/nagios/etc/nrpe.cfg
````
Adjust the configurations according to your environment's needs, ensuring proper configuration of commands and security.



## Step 5: Firewall Configuration
If you are using a firewall, make sure to allow incoming traffic to port 5666 (the default NRPE port).
````
sudo ufw allow 5666
````

## Step 6: Connection Testing
From your Nagios server, test the connection to NRPE using the check_nrpe command with some test check. For example:
```
/usr/local/nagios/libexec/check_nrpe -H <IP_del_servidor_NRPE> -c <nombre_del_comando>
```
Replace <NRPE_server_IP> with the IP address of your NRPE server and <command_name> with the name of the check command you want to execute.

## Annexes
````
[Video Tutoriasl](https://www.youtube.com/watch?v=7qZv50kweys)
````
