# Práctica DNS

1. Docker-compose.yml :
      *Servidor*
        
       - imagen,puertos,volumenes: >carpetas /var/lib/bind // /etc/bind
       -  definir ip y subred
        
      *Cliente*
         
        - imagen
        - subred          stdin_open: true  # docker run -i
                         tty: true         # docker run -t
        - definir una ip distinta del server
        - dns==ip servidor
        - Network
            external true
         
2. named.conf
   ***
   hacer los includes a los siguientes puntos
   ***
3. named.conf.local 
   ***
   ""base de datos"" guarda los logs en el file que indiques
    Crear este file en la ruta apropiada.
   ***
4. named.conf.options
      ***
      aqui indicamos DNSs que se guardaran en cache
      ruta /var/cache/bind
      forwarders -- dns que queramos
      listen on any
***
5. crear la red en docker
   ***
   docker network create bind9_subnet
   ***
6. lanzamos los contenedores con docker compose


7. comprobamos(desde el cliente)
***
  - apk add --no-cache bind-tools (alpine)
  - ping 172.28.5.1
  - dig @172.28.5.1 test.asircastelao.int 
***
