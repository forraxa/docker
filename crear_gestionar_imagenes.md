## Crear y gestionar imágenes  
Los cambios creados en un contenedor se pueden consultar con diff. La primera letra del resultado es A =append, C= change, D=delete
```
docker diff ubuntu1 
```
#### Crear una imagen de un contenedor modificado
```
docker commit ubuntu1 mi_ubuntu #Se ha de indicar el contenedor y el nombre que le queremos dar a la imagen nueva
```
#### Se utiliza el dockerfile para construir las imágenes.  
El dockerfile es el fichero donde se construyen las distintas capas de una imagen en base a comandos propios
```
mkdir imagen_python #crear directorio para albergar la imagen
cd imagen_python
vi Dockerfile #crear Dockerfile con primera letra en mayúsculas y sin .*
FROM ubuntu #imagen de partida
RUN apt-get update
RUN apt-get install -y python #instala python y no nos preguntará nada (Yes por Default)
docker build -t imagen_python . #construir la imagen, -t es para el nombre de la imagen y . es la ruta donde están los archivos y el Dockerfile
```
