## Docker Registry  
Docker registry da la opción de tener un registro de dockers privado.

#### Crear registro
```
docker run -d -p 5000:5000 --name registro1 registry
docker run -d -p 5001:5001 --name registro2 registry #Un segundo registro
```
#### Etiquetar imagen
Para poder subir imagenes al registro se tienen que etiquetar
```
docker tag ubuntu localhost:5000/mi-ubuntu # se tiene que indicar donde está la imagen, el puerto y darle un nombre
```
#### Subir una imagen
```
docker push localhost:5000/mi-ubuntu #Esto subiría la imagen al repositorio localhost:5000
```
#### Bajar imagen del repositorio
```
docker pull localhost:5000/mi-ubuntu
```
#### Modificar la ubicación donde dejar las imagenes
```
mkdir /reg_docker
docker run -d -name repo1 -p 5000:5000 -v /reg_docker:/var/lib/registry registry
```
