# Practica11

# Instalación de WordPress con Bitnami

Bitnami es una biblioteca de instaladores o paquetes de software para aplicaciones web y pilas de desarrollo, así como dispositivos virtuales. Bitnami es patrocinado por Bitrock, una compañía fundada en 2003 en Sevilla, España por Daniel Lopez Ridruejo y Erica Brescia.

## Creación de una máquina en EC2 para Bitnami.

1. Nos dirigiremos a ``Instances`` en el panel del margen izquierdo de EC2.
2. Pincharemos en ``Launch instance`` :
* 2.1. Debemos elegir una imagen para nuestra máquina virtual (``AMI``). En nuestro caso eligiremos la AMI: ``ubuntu-bionic-18.04-amd64-server-20180522-dotnetcore-2018.07.11 (ami-14fb1073)``.
* 2.2. Ahora elegiremos el tipo de instancia, utilizaremos la t2.micro.
* 2.3. En los detalles de la instancia, dejaremos la conifguración por defecto. 
* 2.4. Almacenamiento: También por defecto.
* 2.5. Etiquetas: Igual, la dejaremos por defecto.
* 2.6. Configuración de grupos de seguridad: En esta pestaña de configuración podemos configurar que protocolos tener activos y en que puertos. Por defecto vendrá abierto el TCP en el puerto 22. Añadiremos el protocolo HTTP y HTTPS con sus respectivos puertos 80 y 443.
* 2.7. Por último nos harán un resumen de nuestra conifguración e instalaremos la máquina que hemos elegido.

## Creación de la clave privada

1. Abrir la consola de Amazon EC2.
2. En el panel de navegación, en ``NETWORK & SECURITY``, Seleccionar ``Key Pairs``.
3. Seleccionara ``Create Key Pair``.
4. Escribir un nombre para el nuevo par de claves en el campo ``Key Pair name`` del cuadro de diálogo ``Create Key Pair``, y a continuación, selecciona ``Create``.
5. A continuación, su navegador descargará automáticamente.  El nombre de archivo base es el nombre que especificó como nombre del par de claves, y la extensión del archivo es .pem. Guarde el archivo de clave privada en un lugar seguro.

## Conectar a la máquina.

Para conectar a nuestra máquina debemos:

1. Abrir nuestra CMD.
2. Cambiar al directorio donde hemos descargado nuestra clave. El nombre de la clave será ``Ubuntu_Bitnami.pem``.
3. Utilizaremos el siguiente comando: ``ssh -i Ubuntu18.04_WP.pem ubuntu@ec2-35-178-67-210.eu-west-2.compute.amazonaws.com``.
4. Ya tendremos acceso a nuestra máquina. 

## Instalación de Bitnami 

1. Una vez dentro de la máquina de Ubuntu, debemos descargar el módulo WP de Bitnami.
2. ``wget https://bitnami.com/redirect/to/375342/bitnami-wordpress-5.0-1-linux-x64-installer.run.``
3. ``chmod 755 bitnami.com/redirect/to/375342/bitnami-wordpress-5.0-1-linux-x64-installer.run.``
4. Ejecutamos con: ``sudo ./bitnami.com/redirect/to/375342/bitnami-wordpress-5.0-1-linux-x64-installer.run.``