# Casos prácticos

# 1.- Versión de vsftpd instalado

![version](/imagenes/version.PNG)

# 2.- Usuarios creados en la instalación

Nos crea el usuario ftp

# 3.- Servicio asociado

vsftpd.serv

# 4.- Ficheros de configuración

vsftpd.conf

# 5.- Acceso al servidor FTP: 

### Antes de las prácticas copiaremos el archivo por si nos falla

cp vsftpd.conf vsftpd.conf.original

Nos conectamos con nuestro usuario del sistema


### Enjaular al los usuarios del sistema

- Modificamos el archivo de configuración vsdtpd.conf

![fichero](/imagenes/configuracion1.PNG)

![fichero](/imagenes/configuracion10.PNG)

- Nos creamos el usuario del sistema

adduser nombre_usuario

- Creamos directorio

mkdir /home/nombre_usuario

- Damos permisos al directorio creado

chown nombre_usuario:nombre_usuario /home/nombre_usuario
 
 - Quitamos los permisos de escritura
 
 chmod a-w /home/nombre-usuario
 
 - Comprobación
 
 ![fichero](/imagenes/comprobacion1.PNG)
 
 ### Anónimo tiene solo permiso de lectura en su directorio de trabajo
 
 - Modificamos el archivo vsftpd.conf para activar anonymous
 
  ![fichero](/imagenes/anonymous.PNG)
  
  - Creamos un archivo en /srv/ftp que es el directorio de anonymous
  
  ![fichero](/imagenes/anonymous2.PNG)
 
 - Nos conectamos como anonymous e intentamos crear un directorio
 
  ![fichero](/imagenes/anonymous3.PNG)
  
 ### Anónimo tiene permiso de escritura en el directorio sugerencias, que es un subdirectorio de su directorio raíz
 
 - Creamos el directorio sugerencias dentro de /srv/ftp y le damos los permisos ftp:nogroup y le quitamos el permiso de escritura
 
 ![fichero](/imagenes/anonymous4.PNG)
 
 - Modificamos el archivo vsftpd.conf
 
 ![fichero](/imagenes/escritura.PNG)
 
 - Comprobación
  
  Podemos subir un archivo al directorio sugerencias
  
  ![fichero](/imagenes/anonymous5.PNG)
 
 
 ### Creación de usuarios virtuales
 
 - Instalamos los siguientes paquetes
 
 apt install apache2-utils
 
 apt install libpam-pwdfile
 
 - Modificamos el archivo vsftpd.conf
 
 ![fichero](/imagenes/anonymous18.PNG)
 
 - Creamos la carpeta donde se van a guardan la lista de los usuarios virtuales.

  mkdir /etc/vsftpd
  
  ![fichero](/imagenes/anonymous18.PNG)
  
 - Modificamos el archivo /etc/pam.d/vsftpd
 
 ![fichero](/imagenes/anonymous20.PNG)
 
 - Creación del usuario virtual
 
 ![fichero](/imagenes/anonymous21.PNG)
 
 - Creamos el directorio
 
  ![fichero](/imagenes/anonymous22.PNG)
  
 - Dentro del directorio creamos un archivo por cada usuario 
 
 ![fichero](/imagenes/anonymous23.PNG)
 
 - Creamos el directorio donde podrá acceder 
 
 mkdir /srv/ftp/user1
 
 chown vsftpd:nogroup user1/
 
 - Comprobación

![fichero](/imagenes/anonymous25.PNG)

# 6.- Acceso seguro al servidor FTP

### Vamos a crear un certificado para la seguridad

- Instalamos el siguiente paquete 

apt install openssl

- Creamos el certificado

![fichero](/imagenes/anonymous15.PNG)

- Modificamos el archivo vsftpd.conf 

![fichero](/imagenes/anonymous16.PNG)

- Comprobación

Nos conectamos con un usuario y nos sale el siguiente certificado

![fichero](/imagenes/anonymous17.PNG)

