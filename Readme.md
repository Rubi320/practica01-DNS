# Práctica DNS

1º Docker-compose.yml :
      *Servidor*
         imagen,puertos,volumenes: carpetas /var/lib/bind // /etc/bind
         definir ip y subred

      *Cliente*
         imagen
         subred          stdin_open: true  # docker run -i
                         tty: true         # docker run -t
         definir una ip distinta del server
         dns==ip servidor
         Network
            external true

2º named.conf
   
   hacer los includes a los siguientes puntos

3º named.conf.local 
      
   ""base de datos"" guarda los logs en el file que indiques
    Crear este file en la ruta apropiada.

4º named.conf.options
      
      aqui indicamos DNSs que se guardaran en cache
      ruta /var/cache/bind
      forwarders -- dns que queramos
      listen on any

5º crear la red en docker

   docker network create bind9_subnet

6º lanzamos los contenedores con docker compose


7º comprobamos(desde el cliente)

  ping 172.28.5.1
  dig @172.28.5.1 test.asircastelao.int 

