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

![fichero](/imagenes/configuracion2.PNG)

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
 

# 6.- Acceso seguro al servidor FTP
