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
