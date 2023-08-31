# Docker_and_odoo

#Instalación de docker-compose y odoo 16
------------------
Descargamos e instalamos docker desde su sitio oficial en este caso desde Fedora:
https://docs.docker.com/desktop/install/fedora/

docker odoo imagen oficial
https://hub.docker.com/_/odoo

Una vez instalado docker lo inciamos:
$sudo systemctl start docker

Verificar que los servicios esten iniciados en docker
$sudo docker container ls -a

Encender el contenedor  
$sudo docker container start "nombre del servicio"

Iniciar el contenedor
$sudo docker container restart "Nombre del servicio"

Para ver los logs
$sudo docker container logs --follow "nombre del contenedor"

Crear el contenedor con la imagen y solucionar el tema del guardado de los archivos utilizando "persistencia" Volumenes
$docker run -d -v odoo-db:/var/lib/postgresql/data -e POSTGRES_USER=odoo -e POSTGRES_PASSWORD=odoo -e POSTGRES_DB=postgres --name db postgres:latest

Lanzar o arrancar la imagen de odoo
$docker run -v odoo-data:/var/lib/odoo -d -p 8069:8069 --name odoo --link db:db -t odoo:latest

<image src="/images/screenshot.png" alt="Activar docker e iniciar servicios">





