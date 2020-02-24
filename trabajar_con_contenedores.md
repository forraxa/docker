## Trabajar con contenedores   

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
#### Ejecutar contenedores
*docker run creará un contenedor por cada petición.
```
docker run -it ubuntu #modo interactivo con terminal 
docker start -i 2b5c #arrancar contenedor con modo interactivo indicando el comienzo del CONTANINER ID
```
#### Salir de contenedor
```
exit
```
