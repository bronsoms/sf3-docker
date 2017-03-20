# Symfony 3.2 sobre Docker #

## Instalación ##

### Clonar el proyecto ###

```bash
$ git clone https://github.com/bronsoms/sf3-docker.git
```

### Build de los contenedores ###
En la raíz del proyectos ejectuar el siguiente comando para generar los contenedores. Esta operación puede tardar varios minutos.

```bash
$ docker-compose build
```

### Ejecución ###

Para levantar los contenedores, ejecutar el siguiente comando en el terminal en la raíz del proyecto:

```bash
$ docker-compose up
```

Para finalizar la ejecución sólo hará falta ejecutar la combinación de teclas `Ctrl + C` en el terminal.

### Acceso a la consola de UNIX ###

Para acceder a la consola de UNIX, se puede realizar mediante el siguiento comando:

```bash
bash -c "clear && docker exec -it sf3docker_web_1 sh"
```
Donde `sf3docker_web_1` es el nombre del contenedor que contiene el UNIX.

Para mayor comodidad para controlar los contenedores, se recomienda el uso de la aplicación Kitematic, que se puede descargar desde [este enlace](https://kitematic.com/).

