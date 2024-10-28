# COMPLETAR  
Comparando sus conocimientos antes de hacer la práctica con sus conocimientos después de hacer la tarea, explicar los principales aprendizajes logrados para beneficio de su formación profesional.  
Si solucionó un problema presentado o utilizó otros comandos que no se mencionan al realizar la práctica también se debe documentar.

## Comparativa de Conocimientos Antes y Después de la Práctica

### Antes de la práctica

Conocía los conceptos básicos de contenedores, imágenes y volúmenes, pero no tenía experiencia práctica en la configuración de contenedores, la gestión de volúmenes o la creación de redes entre contenedores. Aunque estaba familiarizado con los comandos básicos de Docker, no los había aplicado en un entorno real.

### Después de la práctica
Al finalizar la práctica, adquirí conocimientos en:

#### Gestión de Contenedores y Redes
- Aprendí a gestionar contenedores para aplicaciones como nginx, PostgreSQL y Drupal, utilizando comandos para iniciar, detener y eliminar contenedores.
- Comprendí cómo establecer redes tipo bridge, permitiendo la comunicación entre contenedores en aplicaciones que requieren múltiples servicios.

#### Uso y Administración de Volúmenes
- Practiqué la creación y gestión de volúmenes nombrados, anónimos y bind mounts, lo que fue esencial para asegurar la persistencia de datos.

#### Resolución de Problemas
- Solucioné un conflicto donde un contenedor nginx ocupaba el puerto 80, lo que me enseñó a gestionar puertos y evitar conflictos entre contenedores.

## Conocimientos Específicos Adquiridos

### Comprensión de Volúmenes en Docker
- Aprendí a crear, montar y gestionar volúmenes nombrados y anónimos, así como a utilizar `docker volume prune` para eliminar volúmenes no utilizados.

### Creación y Configuración de Redes en Docker
- Aprendí a crear redes personalizadas y a conectar contenedores, facilitando la comunicación interna.

### Implementación de Servicios Complejos
- Configuré contenedores para PostgreSQL y pgAdmin, y desplegué un sitio web Drupal, incluyendo la gestión de volúmenes y permisos.

### Solución de Problemas Presentados
- **Problema**: Permisos de Archivos en Drupal
  - **Situación**: Un error surgió por permisos en `sites/default/files`.
  - **Solución**: Ajusté los permisos y propiedades de los directorios, permitiendo que la instalación de Drupal avanzara sin problemas.

## Reflexión Final
Esta práctica ha sido crucial para mi desarrollo profesional. Mejoré mis habilidades técnicas en la gestión de contenedores y aprendí a resolver problemas prácticos en entornos de desarrollo. Estas experiencias son fundamentales para mi futuro en DevOps y administración de sistemas.

