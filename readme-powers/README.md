## README powers!

Ahora vamos a ejecutar un container muy simple "hello-world" para verificar que Docker está instalado y funcionando correctamente.

```sh {"id":"01HZ3FX1GJ2DN1TM40REMK8CXP"}
docker run hello-world
```

Vamos a ejecutar Dockerfile para construir una imagen de Docker. El Dockerfile es un archivo de texto que contiene todos los comandos que un usuario podría llamar en la línea de comandos para ensamblar una imagen.

```sh {"id":"01HZ3GNPEQJSCW5W06QE4VJWVG"}
# Exportamos el nombre de nuestra imagen docker
export DOCKER_LOCAL_NAME=other-data

```

```sh {"id":"01HZ3G23H92HFBEEK2PRQH69ZD"}
docker build -t $DOCKER_LOCAL_NAME .
```

Intentemos acceder a la imagen y ejecutar algunos comandos en ella.

```sh {"id":"01HZ3G6WYXC4W5T4Q3HQWCM1MB"}
echo "accesing to my $DOCKER_LOCAL_NAME"
docker run --rm -it $DOCKER_LOCAL_NAME /bin/bash

unset DOCKER_LOCAL_NAME
```
