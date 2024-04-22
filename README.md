 Manual NAGIOS y NRPE 
=================

### Authors (Autores)

| Author                | Origin                               |
| --------------------- | ------------------------------------ |
| Brandon Arias    | UniBarranquilla - IUB                |
| Jorge Cerra           | UniBarranquilla - IUB                |



<h3>Cómo instalar Nagios en Ubuntu 20.04</h3>

### Abstract (Resumen)


Nagios es una destacada herramienta de código abierto que proporciona capacidades de monitorización de red. Este sistema es fundamental para supervisar routers, servidores, aplicaciones y servicios, garantizando que estén en funcionamiento óptimo. En caso de fallos, Nagios envía alertas de notificación a través de diversos métodos para evitar daños mayores. Además, ofrece representaciones visuales e informes que facilitan la comprensión de los resultados de la monitorización.

La arquitectura de Nagios se basa en un servidor principal que alberga el núcleo de Nagios, el cual utiliza plugins para interactuar con los hosts remotos. Estos hosts, a su vez, tienen instalado un agente como NRPE para permitir la comunicación con el servidor principal.

### Screenshots (Pantallazos)

![image](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/be3f6481-ebfa-488c-84ce-6f3252825a71)


### TOOLS TIC'S (Herramientas TIC'S)
- servidor Ubuntu 20.04
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
- Monitoreo de red
- Alertas de sistema
- Gestión de infraestructura
- Supervisión remota
- Automatización de tareas
- Diagnóstico de problemas
- Seguridad de red
- Informes de rendimiento

### Requirements (Requisitos)

- Un servidor Ubuntu 20.04. (usar Oracle VirtualBox para hacer una maquina virtual en tu PC)
- Acceso root en tu servidor para instalar y desplegar los servicios. O un usuario con privilegios sudo

## Pasos

### paso 1: Actualizar el sistema

Asegúrese de que todas las listas de paquetes están actualizadas como se indica a continuación:
```
sudo apt update
```

Actualiza los paquetes del sistema a sus últimas versiones:
```
sudo apt upgrade
```
### Paso 2: Instalar los paquetes de requisitos previos

Los siguientes paquetes de prerrequisitos son necesarios en la instalación de Nagios Core.
```
sudo apt install wget unzip vim curl gcc openssl build-essential libgd-dev libssl-dev libapache2-mod-php php-gd php apache2
```
### Paso 3: Descargar Nagios Core en Ubuntu 20.04
Descargar el núcleo de Nagios. Para descargar y extraer Nagios Core ejecuta el comando:
```
export VER="4.4.6"
```
A continuación, utilice el comando curl de la siguiente manera.
```
curl -SL https://github.com/NagiosEnterprises/nagioscore/releases/download/nagios-$VER/nagios-$VER.tar.gz | tar -xzf -
```
Esto descarga un directorio llamado nagios-4.4.6 en tu directorio de trabajo actual.
![image-2-1024x110](https://github.com/george14yer/Manual-NAGIOS-y-NRPE/assets/80540365/3ff1690b-b6b7-4748-97e9-348ec7489281)

### Paso 4: cómo instalar Nagios en Ubuntu
Instalar Ubuntu compilando desde el código fuente.

### Usage (Por qué es importante usarlo)

- Mantenimiento de la disponibilidad del sistema: Nagios monitorea constantemente los routers, servidores, aplicaciones y servicios, garantizando que estén en funcionamiento óptimo. Esto ayuda a prevenir interrupciones no planificadas en los sistemas y servicios críticos.
- Detección temprana de problemas: Nagios detecta rápidamente cualquier fallo o anomalía en los sistemas supervisados. Esto permite a los administradores de sistemas tomar medidas correctivas antes de que los problemas se vuelvan críticos o afecten a los usuarios finales.
- Prevención de daños mayores: En caso de fallos, Nagios envía alertas de notificación a través de diversos métodos, como correo electrónico, SMS o integración con sistemas de ticketing. Esto permite a los equipos de operaciones de TI responder rápidamente y minimizar el impacto en el negocio.
- Facilita la toma de decisiones: Nagios ofrece representaciones visuales e informes que facilitan la comprensión de los resultados de la monitorización. Esto ayuda a los administradores de sistemas a identificar tendencias, analizar el rendimiento y tomar decisiones informadas sobre la infraestructura de TI.

### FAQ (Preguntas y respuestas)


**1. ¿Qué es Nagios y para qué se utiliza?**

   Nagios es una herramienta de monitorización de red de código abierto utilizada para supervisar routers, servidores, aplicaciones y servicios. Se utiliza para garantizar que estos sistemas estén en funcionamiento óptimo y para detectar cualquier fallo o anomalía en ellos.

**2. ¿Cuál es la arquitectura básica de Nagios?**
   
   La arquitectura de Nagios se basa en un servidor principal que aloja el núcleo de Nagios. Este núcleo utiliza plugins para interactuar con los hosts remotos, los cuales tienen instalado un agente como NRPE para permitir la comunicación con el servidor principal.
   
**3. ¿Qué tipo de alertas puede enviar Nagios en caso de fallos?**
   
   Nagios puede enviar alertas de notificación a través de diversos métodos, como correo electrónico, SMS o integración con sistemas de ticketing. Esto permite a los equipos de operaciones de TI responder rápidamente y minimizar el impacto en el negocio.
   
**4. ¿Cuáles son algunas de las características clave de Nagios?**
   
   Algunas características clave de Nagios incluyen la capacidad de monitorear diversos tipos de dispositivos y servicios, la generación de informes y representaciones visuales, la escalabilidad y la capacidad de extensión a través de plugins.
   
**5. ¿Cómo puedo instalar Nagios en Ubuntu 20.04?**
   
   Puedes instalar Nagios en Ubuntu 20.04 siguiendo los pasos detallados en la documentación oficial de Nagios o en tutoriales disponibles en línea. Esto implica instalar el servidor principal de Nagios, configurar los plugins y agentes necesarios, y realizar la configuración adecuada para monitorear tus sistemas.
   
### Contacts (Contactos)

Place text here

### Acknowledgements (Agradecimientos)
