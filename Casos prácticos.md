# Casos prácticos

# 1.- Versión de vsftpd instalado

![version](/imagenes/version.PNG)

# 2.- Usuarios creados en la instalación

Nos crea el usuario ftp

# 3.- Servicio asociado



# 4.- Ficheros de configuración

![fichero](/imagenes/fichero.png)

# 5.- Acceso al servidor FTP: 

### Antes de las prácticas copiaremos el archivo por si nos falla

cp vsftpd.conf vsftpd.conf.original

Nos conectamos con nuestro usuario del sistema

![fichero](/imagenes/sistema.png)

 - A los usuarios del sistema los enjaularemos

Copiamos nuestro archivo por si nos ocurre algún error



Configuramos el archivo vsftpd.conf
 


Creamos nuevo usuario

![fichero](/imagenes/usuario.png)

Añadimos el usuario al fichero chroot_list

![fichero](/imagenes/anadir.png)

- Anónimo tiene solo permiso de lectura


- Anónimo tiene permiso de escritura en el directorio sugerencias, que es un subdirectorio de su directorio raíz


- Creación de usuarios vituales


# 6.- Acceso seguro al servidor FTP
