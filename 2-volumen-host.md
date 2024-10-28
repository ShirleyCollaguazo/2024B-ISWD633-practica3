# VOLUMEN TIPO HOST
Un volumen host (o bind mount) es un tipo de volumen donde se monta un directorio o archivo específico del sistema de archivos del host en un contenedor.

```
docker run -d --name <nombre contenedor> -v <ruta carpeta host>:<ruta carpeta contenedor> <imagen> 
```
### En tu computador crear una carpeta llamada nginx y dentro de esta carpeta crea otra llamada html. Como se aprecia en la figura.
![Volúmenes](img/directorio.PNG)

### Crear un volumen tipo host con la imagen nginx:alpine, mapear todos por puertos, para la ruta carpeta host colocar el directorio en donde se encuentra la carpeta html en tu computador y para la ruta carpeta contenedor: /usr/share/nginx/html (esta ruta se obtiene al revisar la documentación de la imagen)
![Volúmenes](img/volumen-host.PNG)
# COMPLETAR CON EL COMANDO /
```
docker run -d --name my_nginx -p 80:80 -v C:\Users\ASUS\OneDrive - Escuela Politécnica Nacional\7MO Semestre\Construccion\practica3\nginx\html":/usr/share/nginx/html nginx:alpine
```

### ¿Qué sucede al ingresar al servidor de nginx?
Cuando ingreso a http://localhost:8080, nginx servirá el contenido desde el directorio especificado en tu host. Esto significa que cualquier archivo HTML o recurso estático en esa carpeta será proporcionado por nginx. Si no hay un archivo index.html, nginx mostrará una página de error o un listado de directorios, dependiendo de la configuración.

### ¿Qué pasa con el archivo index.html del contenedor?
mostrara en el localhost el contenido que esta dentro del index. el directorio del host no tiene un archivo index.html, nginx mostrará un error 403 o 404

### Ir a https://html5up.net/ y descargar un template gratuito, descomprirlo dentro de tu computador en la carpeta html
### ¿Qué sucede al ingresar al servidor de nginx?
El archivo index.html original del contenedor nginx será sobrescrito por el index.html de la carpeta html de tu computadora. Al ingresar al servidor de nginx, verás la nueva plantilla HTML actualizada.

### Eliminar el contenedor
```
docker rm -f my_nginx
```
### ¿Qué sucede al crear nuevamente el mismo contenedor con volumen de tipo host a los directorios definidos anteriormente?
Al recrear el mismo contenedor con el volumen de tipo host apuntando a los mismos directorios definidos, nginx mostrará el contenido actualizado de la carpeta html de tu computadora, que contiene el template HTML5 descargado

### ¿Qué hace el comando pwd?
El comando pwd (print working directory) muestra la ruta absoluta del directorio de trabajo actual.

Si quieres incluir el comando pwd dentro de un comando de Docker, lo puedes hacer de diferentes maneras dependiendo del shell que estés utilizando.


### Volumen tipo host usando PWD y PowerShell
```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v ${PWD}/<ruta relativa>:<ruta absoluta> <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (Git Bash)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd -W)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

### Volumen tipo host usando PWD (en Linux)

```
docker run -d --name <nombre contenedor> --publish published=<valorPuertoHost>,target=<valor> -v $(pwd)/html:/usr/share/nginx/html <nombre imagen>:<tag> 
```

