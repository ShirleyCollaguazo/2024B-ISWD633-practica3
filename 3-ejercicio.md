## Esquema para el ejercicio
![Imagen](img/esquema-ejercicio3.PNG)

### Crear red net-wp
# COMPLETAR CON EL COMANDO COMANDO /
```
docker network create net-wp
```
### Para que persista la información es necesario conocer en dónde mysql almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/ /
En el esquema del ejercicio carpeta del contenedor (a) es /var/lib/mysql (COMPLETAR CON LA RUTA: host: .../ejercicio3/db)

Ruta carpeta host: .../ejercicio3/db

### ¿Qué contiene la carpeta db del host?
La carpeta db del host contiene los archivos de base de datos de MySQL, tales como archivos de tabla, logs de transacciones, registros, etc.

### Crear un contenedor con la imagen mysql:8  en la red net-wp, configurar las variables de entorno: MYSQL_ROOT_PASSWORD, MYSQL_DATABASE, MYSQL_USER y MYSQL_PASSWORD
# COMPLETAR CON EL COMANDO /
```
docker run -d --name my_mysql --network net-wp -e MYSQL_ROOT_PASSWORD=my_root_password -e MYSQL_DATABASE=my_database -e MYSQL_USER=my_user -e MYSQL_PASSWORD=my_password -v C:\Users\ASUS\OneDrive - Escuela Politécnica Nacional\7MO Semestre\Construccion\practica3\ejercicio3\db":/var/lib/mysql mysql:8
```

### ¿Qué observa en la carpeta db que se encontraba inicialmente vacía?
La carpeta db ahora contiene archivos y directorios de base de datos MySQL, incluyendo datos del sistema, tablas, logs de transacciones y archivos de configuración.

### Para que persista la información es necesario conocer en dónde wordpress almacena la información.
# COMPLETAR LA SIGUIENTE ORACIÓN. REVISAR LA DOCUMENTACIÓN DE LA IMAGEN EN https://hub.docker.com/ /
En el esquema del ejercicio la carpeta del contenedor (b) es (COMPLETAR CON LA RUTA: host: .../ejercicio3/www)

Ruta carpeta host: .../ejercicio3/www

### Crear un contenedor con la imagen wordpress en la red net-wp, configurar las variables de entorno WORDPRESS_DB_HOST, WORDPRESS_DB_USER, WORDPRESS_DB_PASSWORD y WORDPRESS_DB_NAME (los valores de estas variables corresponden a los del contenedor creado previamente)
# COMPLETAR CON EL COMANDO /
```
docker run -d --name my_wordpress --network net-wp -p 80:80 -e WORDPRESS_DB_HOST=my_mysql:3306 -e WORDPRESS_DB_USER=my_user -e WORDPRESS_DB_PASSWORD=my_password -e WORDPRESS_DB_NAME=my_database -v "C:\Users\ASUS\OneDrive - Escuela Politécnica Nacional\7MO Semestre\Construccion\practica3\ejercicio3\www":/var/www/html wordpress
```
### Personalizar la apariencia de wordpress y agregar una entrada

### Eliminar el contenedor y crearlo nuevamente, ¿qué ha sucedido?
Al eliminar y recrear el contenedor de WordPress utilizando los mismos volúmenes, las personalizaciones y entradas se conservan. Esto se debe a que los datos se almacenan en carpetas del host (www para WordPress y db para MySQL) que no se eliminan con los contenedores. Docker garantiza la persistencia de datos a través de volúmenes montados, asegurando la continuidad del servicio y la integridad de datos




