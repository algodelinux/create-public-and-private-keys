# create-public-and-private-keys

Función
-----------

Script para crear un par de claves pública y privada para permitir la administración remota sin contraseña.
Se muestra en pantalla la clave pública generada y el recurso puppet que permite distribuirla.

Instalación
-----------

La forma más sencilla de instalarlo es ejecutar estos comandos en la máquina donde queramos clear el par de claves:

   $ wget --no-check-certificate -O /usr/local/sbin/create-public-and-private-keys https://raw.githubusercontent.com/algodelinux/create-public-and-private-keys/master/create-public-and-private-keys
   $ chmod 755 /usr/local/sbin/create-public-and-private-keys
  

Uso                   
---

   $ create-public-and-private-keys
