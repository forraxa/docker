## Redes en Docker  

#### Convertir puertos de contendor en públicos para que se pueda acceder desde el exterior al contenedor  
```
docker run -d -P nginx  # ejecutar en background y asignar puerto de salida automáticamente
```
Si inspeccionamos el contenedor vemos que el puerto 80 del contenedor se mapeó al 32768 de la maquina por lo que para acceder desde el  exterior apuntando al puerto 32768 nos redirigirá automaticamente al 80 interno.  
Por ejemplo acceder desde navegador localhost:32768  
PORTS: 0.0.0.0 nos indica que cualquier ip del contendor será redireccionada, se podría especificar una concreta en contenedores con más de una ip.  

CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                   NAMES  
9f9f471a3925        nginx               "nginx -g 'daemon of…"   3 seconds ago       Up 2 seconds        0.0.0.0:32768->80/  

#### Asignar puerto público para que se pueda acceder desde el exterior al contenedor  
```
docker run -d --name nginx2 -p 8080:80 ngix  # ejecutar en background y asignar puerto 8080 de salida
```
