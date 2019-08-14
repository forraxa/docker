Listar contenedores
docker ps

Ejecutar contendor hello-world pero si no lo tienes lo descarga desde docker registry
docker run hello-world

Descargar la ultima versión del contenedor alpine
docker pull alpine:latest

Descargar la versión 3.7 del contenedor alpine
docker pull alpine:3.7

Ejecutar comando dentro de contendor
docker run alpine:3.7 ls -l #listará la salida de directorios

Ejecutar una terminal "t" e interactiva "i" dentro de un contendor, "sh" sería una shell.
docker run -it alpine:3.7 sh

Ejecutar una terminal "t" e interactiva "i" dentro de un contendor, "bash" sería una shell.
docker exec -it alpine:3.7 bash

