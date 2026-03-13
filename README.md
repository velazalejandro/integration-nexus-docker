# integration-nexus-docker
# Título
Integración de Nexus en Docker

## Comenzando 🚀
_Estas instrucciones te permiten obtener una copia del proyecto en funcionamiento en tu máquina local para propósitos de desarrollo y pruebas._

### Pre-requisitos 📋
_Que cosas necesitas para instalar el software y como instalarlas_
- Manejar la consola de CMD para la ejecución de comandos.
- Manejar el editor Notepad o Bloc de Notas para la creación de los archivos de despliegue.


### Instalación 🔧 Pruebas ⚙️ y Despliegues 📦
Integración de Nexus en Docker:
https://hub.docker.com/r/sonatype/nexus/
docker pull sonatype/nexus
Para ejecutar (si el puerto 8081 está abierto en su host):
docker run –d –p 8081:8081 --name nexus sonatype/nexus:oss

Usando docker-compose:
Con docker-compose, vamos a poder configurar con más facilidad el Nexus, como por ejemplo, separar los datos del repositorio y llevarlo fuera del contenedor, de manera tal que si en algún momento se quiere actualizar a la última versión no se pierda la información. A continuación, el archivo de configuración de docker-compose que debe crearse.
Creamos en la carpeta opt – docker , una carpeta llamada nexus:
Creamos y añadimos el archivo docker-compose.yaml:

# docker-compose.yaml
version: '3.3'
services:
  nexus:
    images: sonatype/nexus
    restart: always
    ports:
      -8088:8081
    volumes:
      - /path/to/nexus/data:/nexus-data

Dentro de la carpeta nexus situada en opt – docker, ejecutamos el comando docker-compose up –d.


## Licencia 📄
Bajo licencia GNU General Public License v3.0


## Autor
Alejandro Velaz
🎓 Formación: ASIR
