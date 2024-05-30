---
runme:
  document:
    relativePath: README.md
  session:
    id: 01HZ3GNFX63RBQ5QB6Y3K1N6Y7
    updated: 2024-05-29 20:18:38-05:00
---

## README powers!

Ahora vamos a ejecutar un container muy simple "hello-world" para verificar que Docker está instalado y funcionando correctamente.

```bash {"id":"01HZ3GNG0J4FEGBVPFC1FQ34E5"}
docker run hello-world

# Ran on 2024-05-29 20:17:06-05:00 for 1.099s exited with 0

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (ar***v8)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 ht******************om/

For more examples and ideas, visit:
 ht*******************************ed/
```

```sh {"id":"01HZ3FX1GJ2DN1TM40REMK8CXP"}
docker run hello-world

# Ran on 2024-05-29 20:17:11-05:00 for 797ms exited with 0

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (ar***v8)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 ht******************om/

For more examples and ideas, visit:
 ht*******************************ed/
```

Vamos a ejecutar Dockerfile para construir una imagen de Docker. El Dockerfile es un archivo de texto que contiene todos los comandos que un usuario podría llamar en la línea de comandos para ensamblar una imagen.

```sh {"id":"01HZ3GNPEQJSCW5W06QE4VJWVG"}
# Exportamos el nombre de nuestra imagen docker
export DOCKER_LOCAL_NAME=other-data


# Ran on 2024-05-29 20:17:13-05:00 for 5.465s exited with 0
```

```sh {"id":"01HZ3G23H92HFBEEK2PRQH69ZD"}
docker build -t $DOCKER_LOCAL_NAME .

# Ran on 2024-05-29 20:17:21-05:00 for 1.527s exited with 0

[+] Building 0.6s (6/6) FINISHED                            docker:desktop-linux
 => [internal] load build definition from Dockerfile                        0.0s
 => => transferring dockerfile: 159B                                        0.0s
 => [internal] load metadata for do*****io/library/py**on:2.****im          0.5s
 => [internal] load .dockerignore                                           0.0s
 => => transferring context: 2B                                             0.0s
 => [1/2] FROM do*****io/library/py**on:2.***********56:6c**************66  0.0s
 => => resolve do*****io/library/py**on:2.***********56:6c**************66  0.0s
 => CACHED [2/2] WORKDIR /app                                               0.0s
 => exporting to image                                                      0.0s
 => => exporting layers                                                     0.0s
 => => exporting manifest sh**56:17c8ff4937202df7d141b7abfd9ca3de726ea9d90  0.0s
 => => exporting config sh**56:e15b9f8e73c3047bcbe6917a7e2de6b822d1fa8a203  0.0s
 => => exporting attestation manifest sh**56:99*************************02  0.0s
 => => exporting manifest list sh**56:bb508be1ff91a03a251cf96d9e3913c85d6a  0.0s
 => => naming to docker.io/library/hey:latest                               0.0s
 => => unpacking to docker.io/library/hey:latest                            0.0s

**ew build details: ************op://dashboard/build/de*********ux/de*********ux/sv*********************as

t's Next?
  View a summary of image vulnerabilities and recommendations → r scout quickview

```

Intentemos acceder a la imagen y ejecutar algunos comandos en ella.

```sh {"id":"01HZ3G6WYXC4W5T4Q3HQWCM1MB"}
echo "accesing to my $DOCKER_LOCAL_NAME"
docker run --rm -it $DOCKER_LOCAL_NAME /bin/bash

unset DOCKER_LOCAL_NAME

# Ran on 2024-05-29 20:17:26-05:00 for 16.017s exited with 0
accesing to my hey
ro*************9b:/app# python
Python 2.7.18 (default, Apr 20 2020, 19:49:40) 
[GCC 8.3.0] on li**x2
Type "help", "copyright", "credits" or "license" for more information.
>>> exit
Use exit() or Ctrl-D (i.e. EOF) to exit
>>> 
ro*************9b:/app# exit
```