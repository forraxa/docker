## Redes en Docker  

#### Convertir puertos de contendor en públicos para que se pueda acceder desde el exterior al contenedor  
```
docker run -d -P nginx  # ejecutar en background y asignar puerto de salida automáticamente
```
Si inspeccionamos el contenedor vemos que el puerto 80 del contenedor se mapeó al 32768 de la maquina por lo que para acceder desde el  exterior apuntando al puerto 32768 nos redirigirá automaticamente al 80 interno. 

Por ejemplo acceder desde navegador localhost:32768  

PORTS: 0.0.0.0 nos indica que cualquier ip del contendor será redireccionada, se podría especificar una concreta en contenedores con más de una ip.  
```
CONTAINER ID    IMAGE   COMMAND                  CREATED         STATUS           PORTS                NAMES  
9f9f471a3925    nginx   "nginx -g 'daemon of…"   3 seconds ago   Up 2 seconds     0.0.0.0:32768->80/  
```
#### Asignar puerto público para que se pueda acceder desde el exterior al contenedor  
```
docker run -d --name nginx2 -p 8080:80 ngix  # ejecutar en background y asignar puerto 8080 de salida
```
#### Comandos para manejar redes dentro de docker
```
docker network
```
#### Listar redes en docker
```
docker network ls
```

#### Los contenedores por defecto utilizan la red bridge

#### Inspeccionar red de tipo bridge
```
docker network inspect bridge > bridge.txt
```

#### Comprobar conexión entre dos contenedores.
Ejemplo conexión a base de datos desde terminal mongo a mongo2:   
Datos respectivamente:  
Instancias: mongo, mongo2  
ip: 172.17.0.2, 172.17.0.3
puerto: 27017, 27018
```
mongo --host 172.17.0.3 --port 27018
```
#### Información para crear una red
```
docker network create --help
```
#### Crear red
Por defecto crea redes bridge  
```
docker network create red1
docker network create --subnet=192.168.0.0/16 red2 #declarar la red con una subnet determinada 
```
#### Información de las redes
```
nmcli on
```
#### Conectar un contenedor con una red
```
docker run -it --name ubuntu1 --network red1 ubuntu #creará un ubuntu en la red1
docker inspect ubuntu1 | grep IPAdd # ver que dirección de ip se le asignó
docker network connect red2 ubuntu1 #conectar a la red2 el contenedor ubuntu1 pero sin quitarlo de la red donde está actualmente
docker network disconnect red2 ubuntu1 #desconectar el contenedor de la red2
```
#### Borrar una red
```
docker network rm red1 
```
