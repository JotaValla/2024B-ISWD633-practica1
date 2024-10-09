# Imagen
Es un archivo único que contiene todos los programas, librerías, dependencias y configuraciones necesarias para instalar y/o ejecutar una aplicación o un conjunto de aplicaciones.
![Imagen](img/imagen.PNG)


## ¿Cuál es la relación entre una imagen y un contenedor? 
La relación entre una imagen y un contenedor en Docker es similar a la de un plano y una casa:

Imagen:
- Plano: La imagen de Docker es como el plano de una casa. Contiene todas las instrucciones y especificaciones necesarias para construir - un entorno de ejecución (la "casa").
- Inmutable: Una vez creada, la imagen no cambia. Es como un plano impreso que define una configuración específica.
- Plantilla: Sirve como plantilla para crear uno o varios contenedores idénticos.

Contenedor:

- Casa: El contenedor es la instancia en ejecución de una imagen. Es la "casa" construida a partir del plano.
- Dinámico: A diferencia de la imagen, el contenedor es un entorno activo que puede cambiar. Puedes ejecutar aplicaciones, modificar archivos, etc.
- Aislado: Cada contenedor se ejecuta en un entorno aislado, como si fuera una casa independiente. Los cambios en un contenedor no afectan a otros contenedores ni al sistema anfitrión.
  
En resumen:
- La imagen es la plantilla estática que define el entorno.
- El contenedor es la instancia dinámica y en ejecución de esa imagen.

![Imagen y contenedores](img/imagenContenedores.JPG)
## Comandos para imágenes

### Descargar imagen
Descarga la última versión de la imagen disponible en el registro de Docker.

```
docker pull <nombre imagen> 
```

Descarga una versión específica de la imagen, cada imagen tiene etiquetas (tags) para diferentes versiones.
Una imagen puede tener la etiqueta latest para representar la última versión, si no se especifica una etiqueta se hará referencia a la versión latest.

```
docker pull <nombre imagen>:<tag>
```

Descargar la imagen **hello-world**

# COMPLETAR

**¿Qué es nginx?**
Nginx es un software que actúa como un potente intermediario entre los usuarios que solicitan contenido web (como páginas web o imágenes) y los servidores que lo almacenan.

Imaginemos un semáforo inteligente: Nginx dirige el tráfico web, asegurándose de que llegue al destino correcto de la manera más rápida y eficiente posible, a la vez que protege los servidores de sobrecargas.

Descargar la imagen  **nginx** en la versión **alpine**
# COMPLETAR

### Listar imágenes

```
docker images
```

# COLOCAR UNA CAPTURA DE PANTALLA DEL RESULTADO 

**Identificadores**

En Docker, se utilizan varios identificadores para diferenciar de manera única los elementos del sistema, como imágenes, contenedores, volúmenes y redes. Estos identificadores son generados automáticamente por Docker y son únicos dentro del contexto del sistema Docker en el que se encuentran. 

### Inspeccionar una imagen
El comando docker inspect se utiliza para obtener información detallada sobre un objeto de Docker específico, como un contenedor, una imagen, un volumen o una red.  Proporciona información en formato JSON sobre el objeto especificado.

```
docker inspect <nombre imagen>
docker inspect <nombre imagen>:<tag>
```

Inspeccionar la imagen hello-world 
# COMPLETAR

**¿Con qué algoritmo se está generando el ID de la imagen?** sha256
# COMPLETAR

### Filtrar imágenes

```
docker images | grep <termino a buscar>

```

### Para eliminar una imagen
Eliminar permanentemente la imagen de tu sistema Docker.

```
docker rmi <nombre imagen>:<tag>
```

Eliminar la imagen hello-world 
# COMPLETAR

-f: Es la opción para forzar la eliminación de la imagen incluso si hay contenedores en ejecución que utilizan esa imagen.
Cuando eliminas una imagen Docker, Docker no elimina automáticamente los contenedores que se han creado a partir de esa imagen. Esto significa que, aunque hayas eliminado la imagen, el contenedor seguirá ejecutándose normalmente.  
**Considerar**
Eliminar una imagen no afecta a los contenedores que se han creado a partir de esa imagen, a menos que esos contenedores dependan de archivos o configuraciones específicas de la imagen eliminada. En ese caso, es posible que los contenedores se comporten de manera inesperada después de eliminar la imagen.
Es una buena práctica detener y eliminar todos los contenedores que dependan de una imagen antes de eliminar la imagen en sí.

```
docker rmi -f <nombre imagen>:<tag>
```

