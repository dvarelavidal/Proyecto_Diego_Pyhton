 Practica de Python  + Docker


---

* **Utilizamos docker hub para localizar la imagen de python**

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

* **Probamos con "docker run"**

Comprobación de Docker run con el comando docker-compose up


![Imagen](https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/4.png?raw=true)


* **Crearemos un docker-compose.yml para arrancar el contenedor**

Fichero docker-compose

  ``` services:
  python:
    image: youtubeimagen:alpine
    build : .
    stdin_open: true
    tty: true
    command: ['python', 'hola.py']
 
   ```
* **Nos damos de alta en  docker-hub, para poder subir la imagen y hacerla pública**

La web será esta: https://hub.docker.com


![Imagen](https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/Captura%20de%20pantalla%20de%202023-03-09%2015-55-53.png?raw=true)


* **Crea un repositorio en docker-hub y sube tu imágen**

Nos loggeamos en docker con el comando ```docker login```

![Imagen](https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/5.png?raw=true)

Despues, creo un tag con el comando siguiente ```docker tag youtubeimagen:alpine dvarelavidal/appyoutube:latest ```

Por ultimo subo la imagen con el comando ``` sudo docker push dvarelavidal/appyoutube:latest ```
Introducimos la contraseña y estará subido.

![Imagen](https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/6.png?raw=true)


Me encontré con el problema que en docker hub, tenía el repositorio en modo "privado".
A continuación, lo que hago es crear el repositorio appyoutube2 en modo "publico".

![Imagen] (https://github.com/dvarelavidal/Proyecto_Diego_Pyhton/blob/master/7.png?raw=true)


