## Trabajar con contenedores   

[manuales de referencia de docker](https://docs.docker.com/reference/)  
dockerd: daemon de docker (permite arrancar los servicios de docker)  
docker: Es la herramienta de cliente de docker  

## Arrancar docker 
En Ubuntu y Centos 7 y 8 se utilizan los mismos comandos
```
systemctl start docker
```
Activar docker para tener docker activado cuando se reinicie el sistema operativo
```
systemctl enable docker
```
Parar docker
```
systemctl stop docker
```
Comprobar estado
```
systemctl status docker
```
