# create-public-and-private-keys

Función
-----------

Script para crear un par de claves pública y privada para permitir la administración remota sin contraseña.
Se muestra en pantalla la clave pública generada y el recurso puppet que permite distribuirla.

Instalación
-----------

La forma más sencilla de instalarlo es ejecutar estos comandos en la máquina donde queramos crear el par de claves:  

   $ wget --no-check-certificate -O /usr/local/sbin/create-public-and-private-keys https://raw.githubusercontent.com/algodelinux/create-public-and-private-keys/master/create-public-and-private-keys  
   $ chmod 755 /usr/local/sbin/create-public-and-private-keys
  

Uso                   
---

   $ create-public-and-private-keys


Salida                   
------

   Clave pública para el usuario root en adminies:
> AAAAB3NzaC1yc2EAAAADAQABAAABAQCyGeWwqdvkxRU7XXc2OuR0++6M3Oh2ZWEakw1eyd9oDIUAp+4EQLdPA00OcXQwzb7oGvdBZrnr30wylWcEbQgSFAAmDEYzv0EFHPQdckETRMpjTFGYGQeHnpwriOsnsaaz4yIegXCFw9eOq6+ngccWHtjp19NrDnUsQLE1TEpQQYk+X/nD5X9kAWW6djuC+ot1f8ds6TKB+7s+IUt/2xlFssHrnJZQ7OxXd4GaYItcSyKPavi+j03qJQfeSTGeApuU06t+PGiw1OEC9idRopLkQDeLlWGFwycT2kMEK24bNcFIdW9EsESsIMBkNYslY0IN9igyyRwfZTxk18GkK/3h

Recurso puppet para distribuir la clave pública del usuario root@adminies:  
> ssh_authorized_key { "root@adminies":  
> &nbsp;&nbsp;&nbsp;ensure => present,  
> &nbsp;&nbsp;&nbsp;type => rsa,  
> &nbsp;&nbsp;&nbsp;key => "AAAAB3NzaC1yc2EAAAADAQABAAABAQCyGeWwqdvkxRU7XXc2OuR0++6M3Oh2ZWEakw1eyd9oDIUAp+4EQLdPA00OcXQwzb7oGvdBZrnr30wylWcEbQgSFAAmDEYzv0EFHPQdckETRMpjTFGYGQeHnpwriOsnsaaz4yIegXCFw9eOq6+ngccWHtjp19NrDnUsQLE1TEpQQYk+X/nD5X9kAWW6djuC+ot1f8ds6TKB+7s+IUt/2xlFssHrnJZQ7OxXd4GaYItcSyKPavi+j03qJQfeSTGeApuU06t+PGiw1OEC9idRopLkQDeLlWGFwycT2kMEK24bNcFIdW9EsESsIMBkNYslY0IN9igyyRwfZTxk18GkK/3h"
> &nbsp;&nbsp;&nbsp;user => root  
> }
