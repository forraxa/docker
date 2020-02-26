## Volúmenes 

#### Comando docker para volúmenes (información de comandos)
```
docker volume
```
Los volúmenes en docker se guardan en la ruta /var/lib/docker/volumes  
#### Crear contenedor con volumen asociado 
```
docker run -it -v /datos --name ubuntu1 ubuntu bash
```
#### Obtener información del volumen
```
docker volume inspect 3bf2b5da0eefb63742a1bda6393908397aa4ed1617084e5a3753736aadd52478
```
#### Compartir directorio entre el Host y el volumen
```
docker run -it -v /root/dir1:/dir1 --name ubuntu2 ubuntu #comparte el directorio dir1 del root con el directorio dir1 del volumen y si no existen los directorios los creará
```
#### Compartir volumenes entre contenedores
```
docker run -it --name ubuntu5 --volumes-from ubuntu4 ubuntu bash #ubuntu5 usará como volumen el mismo que ubuntu4
```
#### Crear un volumen con nombre personalizado para posteriormente asociarlo a un contenedor
```
docker volume create vol1 #se creará el volumen vol1 en /var/lib/docker/volumes
docker run -it -name ubuntu7 -v vol1:dir1 ubuntu bash #creará el contenedor y asocia el volumen vol1 a la carpeta dir1 del contenedor
docker run -it -name ubuntu7 -v vol1:dir1:ro ubuntu bash #creará el contenedor y asocia el volumen vol1 a la carpeta dir1 del contenedor pero sólo con permisos de lectura (read only)
```

#### Borrar volumen
```
docker volume rm 3bf2b5da0eefb63742a1bda6393908397aa4ed1617084e5a3753736aadd52478
docker volume prune #borra volumenes sin uso en algún contenedor
```
