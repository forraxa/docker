## Instalación de Docker en Ubuntu (Debian, Suse….)  
Versión Ubuntu para la instalación  
Ubuntu 18.04.4 LTS  
- [Instrucciones de página oficial ubuntu](https://docs.docker.com/install/)  

Actualización del sistema operativo (el índice de los paquetes)
```
sudo apt-get update
```
Instalar una serie de paquetes necesarios (utilizar repositorios sobre https)
```
sudo apt-get install -y --no-install-recommends \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common
```
Instalar la clave GPG de Docker necesaria para hacer la instalación de determinados paquetes desde https
```
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
```
Por defecto debería estar activado el repositorio estable "stable" pero por si acaso lo activamos de manera definitiva  
Stable: La última versión de Docker estable, correcta (producción)  
Test: Versión de pruebas y últimas novedades  
```
sudo add-apt-repository \
"deb [arch=amd64] https://download.docker.com/linux/ubuntu \
$(lsb_release -cs) \
stable"
```
Actualizar todo
```
sudo apt-get update
```
Instalar Docker community edition
```
sudo apt-get install docker-ce
```
Evaluar la versión de Docker
```
docker --version
```
## Instalación en Docker en Centos (Fedora, Red Hat y Oracle Linux)  

Instalar paquetes necesarios del Sistema operativo
```
yum install -y yum-utils device-mapper-persistent-data lvm2
```
Configurar el acceso al repositorio "stable"
```
yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
```
Instalar Docker community edition
```
yum install docker-ce
```
Comprobar que está instalado, arrancamos el servicio, comprobamos que está funcionando
```
systemctl start docker
```
Evaluar la versión
```
docker --version
```
