 Practica de Python  + Docker


---

* **Utiliza docker hub para localizar  la imagen de python**

```yml
FROM python:3

RUN pip install pytube

```º

    
* **Modificaremos la imagen realizando cambios en el fichero Dockerfile añadiendo lo siguiente dentro de el:**

Fichero dockerfile / docker-compose-yml
```yml
FROM python:3

RUN pip install pytube


```

```services:
  python:
    image: youtubeimagen:alpine
    build : .
    stdin_open: true
    tty: true
    command: ['python', 'hola.py']
```
* **Creamos la imagen nueva en el terminal con el comando 'docker build'**

Para construir la imagen primero me logueo en docker con el comando ```docker login ```
![Imagen](https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/1.png?raw=true)

https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/1.png?raw=true

A continuación creo la imagen con el comando ```docker build -t nombre_de_mi_imagen:latest .```

![Imagen](https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/2.png?raw=true)

* **Pruebala con "docker run"**

Comprobación de Docker run con el comando docker-compose up





* **Crea un docker-compose.yml para lanzar el contenedor**

Fichero docker-compose

  ``` services:
  python:
    image: youtubeimagen:alpine
    build : .
    stdin_open: true
    tty: true
    command: ['python', 'hola.py']
 
   ```
* **Date de alta en docker-hub, para poder subirla y hacerla pública**

Nos daremos de alta en la web siguiente enlace https://hub.docker.com



* **Crea un repositorio en docker-hub y sube tu imágen**

Nos loggeamos en docker con el comando ```docker login```



