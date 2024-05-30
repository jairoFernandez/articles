---
runme:
  document:
    relativePath: README.md
  session:
    id: 01HZ3DWH37FE7PKJ2GGZCF3FXK
    updated: 2024-05-29 20:08:35-05:00
---

## README powers!

Ahora vamos a ejecutar un container muy simple "hello-world" para verificar que Docker está instalado y funcionando correctamente.

```bash
docker run hello-world
```

```sh {"id":"01HZ3FX1GJ2DN1TM40REMK8CXP"}
docker run hello-world
```

Vamos a ejecutar Dockerfile para construir una imagen de Docker. El Dockerfile es un archivo de texto que contiene todos los comandos que un usuario podría llamar en la línea de comandos para ensamblar una imagen.

```sh {"id":"01HZ3G23H92HFBEEK2PRQH69ZD"}
export DOCKER_LOCAL_NAME=my-image
docker build -t $DOCKER_LOCAL_NAME .

# Ran on 2024-05-29 20:08:15-05:00 for 1.371s exited with 0

[+] Building 0.0s (0/1)                                                         [+] Building 0.2s (1/2)                                                                         docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                            0.0s
[+] Building 0.3s (1/2)                                                                         docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                            0.0s
[+] Building 0.4s (2/3)                                                                         docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                            0.0s
[+] Building 0.5s (6/6) FINISHED                                                                docker:desktop-linux
 => [internal] load build definition from Dockerfile                                                            0.0s
 => => transferring dockerfile: 159B                                                                            0.0s
 => [internal] load metadata for do*****io/library/py**on:2.****im                                              0.4s
 => [internal] load .dockerignore                                                                               0.0s
 => => transferring context: 2B                                                                                 0.0s
 => [1/2] FROM do*****io/library/py**on:2.***********56:6c1ffdff499e29ea663e6e67c9b6b9a3b401d554d2c9f061f9a453  0.0s
 => => resolve do*****io/library/py**on:2.***********56:6c1ffdff499e29ea663e6e67c9b6b9a3b401d554d2c9f061f9a453  0.0s
 => CACHED [2/2] WORKDIR /app                                                                                   0.0s
 => exporting to image                                                                                          0.0s
 => => exporting layers                                                                                         0.0s
 => => exporting manifest sh**56:17c8ff4937202df7d141b7abfd9ca3de726ea9d90d7ff222a38770e7bdbef450               0.0s
 => => exporting config sh**56:e15b9f8e73c3047bcbe6917a7e2de6b822d1fa8a2037f9e57aa566f328a83ad1                 0.0s
 => => exporting attestation manifest sh**56:35334a1ea75344d96a428b234a1f0d79255242034cf73fde973175be45d6fa06   0.0s
 => => exporting manifest list sh**56:040ee381cf1ca2de20e25666a148ad8e993db80f1d96fb291aa5f1d0d1e2c0da          0.0s
 => => naming to docker.io/library/genial-image:latest                                                          0.0s
 => => unpacking to docker.io/library/genial-image:latest                                                       0.0s

**ew build details: ************op://dashboard/build/de*********ux/de*********ux/u5*********************49

t's Next?
  View a summary of image vulnerabilities and recommendations → r scout quickview

```

Intentemos acceder a la imagen y ejecutar algunos comandos en ella.

```sh {"id":"01HZ3G6WYXC4W5T4Q3HQWCM1MB"}
echo "accesing to my $DOCKER_LOCAL_NAME"
docker run --rm -it $DOCKER_LOCAL_NAME /bin/bash
```