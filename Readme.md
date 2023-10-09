# Práctica DNS

1º Docker-compose.yml :
      Servidor
         imagen,puertos,volumenes: en carpeta /var/lib/bind // /etc/bind
         definir ip
      Cliente
         imagen
         definir subred stdin_open: true  # docker run -i
                         tty: true         # docker run -t
         dns==ip servidor
      Network
         external true
2º named.conf
   hacer los includes a los siguientes puntos

3º named.conf.local 
      ""base de datos"" guarda los logs en el file que indiques


4º Crear el file que describimos anteriormente en la ruta indicada.

5º named.conf.options
      aqui indicamos DNSs que se guardaran en cache
      ruta /var/cache/bind
      forwarders -- dns que queramos
      listen on any

6º crear la red en docker
   docker network create bind9_subnet


