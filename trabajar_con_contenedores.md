## Trabajar con contenedores e imágenes  

[manuales de referencia de docker](https://docs.docker.com/reference/)  
dockerd: daemon de docker (permite arrancar los servicios de docker)  
docker: Es la herramienta de cliente de docker  

### Arrancar docker 
En Ubuntu y Centos 7 y 8 se utilizan los mismos comandos
```
systemctl start docker
```
#### Activar docker para tener docker activado cuando se reinicie el sistema operativo
```
systemctl enable docker
```
#### Parar docker
```
systemctl stop docker
```
#### Comprobar estado
```
systemctl status docker
```
#### Ver información de docker
```
docker info
```
#### Ayuda de comandos
```
docker ps --help
```
#### descargar una imagen
```
docker run hello-wold
```
#### Examinar las imágenes descargadas
```
docker images
```
#### Examinar contenedores 
```
docker ps #muestra contenedores activos
docker ps -a #mostrar contenedores aunque no estén activos
```
#### Revisar el último contenedor sobre el que se realizó alguna actividad
```
docker ps -l
docker ps -n 4 #ver los 4 últimos contenedores sobre los que registró alguna actividad
```
#### Ver el tamaño de los contenedores
```
docker ps -a -n 3 -s #muestra el tamaño de los tres últimos contenedores con actividad aunque no estén activos
```
#### Descargar imagenes
```
docker pull ubuntu #la descarga pero no la ejecuta
```
#### Ejecutar contenedores
*docker run creará un contenedor por cada petición.
```
docker run -it ubuntu #modo interactivo con terminal 
docker start -i 2b5c #arrancar contenedor con modo interactivo indicando el comienzo del CONTANINER ID
docker run -d nginx #descarga "si no lo tienes" y ejecuta en backgroud el servidor web nginx
```
#### Salir de contenedor
```
exit
```
#### Borrar contenedores e imágenes
```
docker rm 9ecd #borrar a partir del id del contenedor
docker rm stoic_ellis #borrar a partir del nombre del contenedor
docker rmi 4r5t #borrar a partir del id de la imagen
```
#### Darle nombre a un contendor cuando se ejecuta
```
docker run -it --name mi_ubuntu ubuntu bash #arranca un ubuntu interactivo y llámale mi_ubuntu
```
#### Ejecutar comandos contra contenedores (util para contenedores backgroud
```
docker exec mi_ubuntu echo hola #ejecuta el comando echo hola con la salida hola por terminal
docker exec -it mi_ubuntu bash #abrir una bash en un contenedor ejecutado en segundo plano.
```
#### Ver comandos de imagenes y contenedores
```
docker image
docker container
```
#### Ver que está sacando por pantalla un contenedor que esté en background
```
docker logs 3f4r5t # muestra todo lo que ha devuelto
docker logs 3f4r5t --tail 5 # muestra las 5 últimas lineas que ha devuelto
docker logs 3f4r5t -f # muestra indefinidamente lineas que está devolviendo
```
#### Matar un contenedor
```
docker kill 4r5t
```
