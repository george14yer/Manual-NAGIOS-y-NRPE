## Paso 1: Descarga del código fuente de NRPE

1. Dirígete al [sitio web oficial de Nagios](https://github.com/NagiosEnterprises/nrpe) y descarga el paquete NRPE.
2. En tu servidor Nagios, abre una terminal y navega hasta el directorio donde deseas descargar NRPE.
3. Usa el comando `git clone` para clonar el repositorio NRPE desde GitHub:

   ```
   git clone https://github.com/NagiosEnterprises/nrpe.git
   ```
## Paso 2: Instalación de dependencias
Instala las herramientas y las bibliotecas necesarias para compilar NRPE. En sistemas basados en Debian/Ubuntu, puedes usar el siguiente comando:

```
sudo apt-get update
sudo apt-get install -y autoconf automake gcc libc6 libmcrypt-dev make libssl-dev wget dc build-essential

```
## Paso 3: Compilación e instalación de NRPE
Navega al directorio nrpe que se ha creado después de la clonación:
```
cd nrpe

```
Ejecuta el script de configuración:
```
./configure --enable-command-args

```
Compila NRPE:
````
make all
````

Instala NRPE y sus plugins:
```
sudo make install
````
## Paso 4: Configuración de NRPE
Edita el archivo de configuración nrpe.cfg ubicado en /usr/local/nagios/etc/:

````
sudo nano /usr/local/nagios/etc/nrpe.cfg
````
Ajusta las configuraciones según las necesidades de tu entorno, asegurándote de configurar adecuadamente los comandos y la seguridad.



## Paso 5: Configuración del firewall
Si estás utilizando un firewall, asegúrate de permitir el tráfico entrante al puerto 5666 (el puerto predeterminado de NRPE).
````
sudo ufw allow 5666
````

## Paso 6: Prueba de conexión
Desde tu servidor Nagios, prueba la conexión a NRPE usando el comando check_nrpe con algún chequeo de prueba. Por ejemplo:
```
/usr/local/nagios/libexec/check_nrpe -H <IP_del_servidor_NRPE> -c <nombre_del_comando>
```
Sustituye <IP_del_servidor_NRPE> con la dirección IP de tu servidor NRPE y <nombre_del_comando> con el nombre del comando de chequeo que deseas ejecutar
