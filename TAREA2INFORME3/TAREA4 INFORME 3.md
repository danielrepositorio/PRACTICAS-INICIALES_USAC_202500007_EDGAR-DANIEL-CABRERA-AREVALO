# Actividad Práctica: Instalación y Configuración de Apache2 en Ubuntu

## Introducción

En esta actividad se utilizaron diferentes comandos desde la terminal de Ubuntu para realizar la instalación y configuración básica del servidor web Apache2.

La actividad permitió poner en práctica el uso de privilegios de superusuario mediante `sudo`, la gestión de paquetes mediante `apt`, la navegación entre directorios utilizando comandos de terminal, la edición de archivos mediante el editor de texto `nano` y la verificación del funcionamiento de un servidor web local.

Apache2 es un servidor web que permanece ejecutándose en el sistema y permite responder a solicitudes HTTP. Por defecto, Apache2 utiliza el directorio `/var/www/html/` para almacenar los archivos que serán mostrados a través del navegador.

El archivo principal utilizado por Apache2 es `index.html`, el cual se muestra automáticamente cuando se accede a la dirección:

```text
http://localhost
```

A continuación se presentan los comandos utilizados durante la actividad, su función y las evidencias correspondientes.

---

# 1. Actualización del índice de paquetes

## Comando utilizado

```bash
sudo apt update
```

## Descripción

El comando `sudo apt update` se utiliza para actualizar el índice de paquetes disponibles en el sistema operativo Ubuntu.

Este comando consulta los repositorios configurados en el sistema y obtiene información actualizada acerca de los paquetes y versiones disponibles.

El comando se compone de las siguientes partes:

- `sudo`: permite ejecutar un comando utilizando privilegios de superusuario o administrador.
- `apt`: es la herramienta utilizada por Ubuntu para administrar paquetes.
- `update`: indica que se desea actualizar el índice o lista de paquetes disponibles.

Es importante mencionar que `apt update` no instala nuevos programas ni actualiza directamente los programas que ya se encuentran instalados. Su función es actualizar la información de los paquetes disponibles en los repositorios.

Al ejecutar el comando puede solicitarse la contraseña del usuario.

```text
[sudo] password for usuario:
```

Al momento de escribir la contraseña en la terminal no aparecen letras, puntos ni asteriscos. Esto es un comportamiento normal de Ubuntu por motivos de seguridad.

Al finalizar correctamente el comando pueden observarse mensajes similares a:

```text
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
```


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\SUDO APT UPDATE 1.png
![alt text](<../../../../PRACTICAS/CAPTURAS TARE4/SUDO APT UPDATE 2.png>)
---

# 2. Instalación del servidor web Apache2

## Comando utilizado

```bash
sudo apt install apache2
```

## Descripción

El comando `sudo apt install apache2` permite instalar el servidor web Apache2 en Ubuntu.

El comando está compuesto por:

- `sudo`: permite ejecutar la operación con permisos administrativos.
- `apt`: herramienta utilizada para la gestión de paquetes.
- `install`: indica que se desea instalar un paquete.
- `apache2`: es el nombre del paquete correspondiente al servidor web Apache.

Apache2 es un servidor HTTP que permite que una computadora pueda responder a solicitudes realizadas desde un navegador web.

Durante el proceso de instalación, Ubuntu descarga Apache2 y las dependencias necesarias para su funcionamiento.

Dependiendo de la configuración del sistema puede aparecer una confirmación similar a:

```text
Do you want to continue? [Y/n]
```

o:

```text
¿Desea continuar? [S/n]
```

En ese caso se confirma la instalación y se espera a que el proceso termine.

Durante la instalación pueden mostrarse mensajes similares a:

```text
Unpacking apache2...
Setting up apache2...
Processing triggers...
```

Una vez finalizada la instalación, Apache2 queda disponible en el sistema.




c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\SUDO APT INSTALL APACHE2.png
---

# 3. Verificación del estado del servicio Apache2

## Comando utilizado

```bash
sudo systemctl status apache2
```

## Descripción

El comando `sudo systemctl status apache2` se utiliza para verificar el estado actual del servicio Apache2.

El comando está compuesto por:

- `sudo`: ejecuta el comando con privilegios administrativos.
- `systemctl`: herramienta utilizada para administrar y consultar servicios del sistema.
- `status`: indica que se desea consultar el estado de un servicio.
- `apache2`: corresponde al servicio que se desea consultar.

Si Apache2 se encuentra instalado y funcionando correctamente, entre la información mostrada debe encontrarse una línea similar a:

```text
Active: active (running)
```

El texto:

```text
active (running)
```

indica que Apache2 se encuentra activo y ejecutándose correctamente.

Esto confirma que el servidor web está funcionando en el sistema.

## Salida del visor de estado

Después de consultar el estado del servicio, la terminal puede permanecer mostrando la información de Apache2.

Para regresar nuevamente a la terminal se presiona la tecla:

```text
q
```

La letra `q` corresponde a la opción de salir del visor.


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\SUDO SYSTEMCTL START APACHE 2.png
---

# 4. Comprobación inicial de Apache2 desde el navegador

## Dirección utilizada

```text
http://localhost
```

## Descripción

Después de instalar Apache2 y verificar que el servicio se encontraba activo, se realizó una comprobación desde el navegador.

Se ingresó la siguiente dirección:

```text
http://localhost
```

`localhost` hace referencia a la misma computadora desde la cual se está realizando la actividad.

Cuando se ingresa a `http://localhost`, el navegador realiza una solicitud HTTP al servidor Apache2 que se encuentra instalado en la misma computadora.

Si Apache2 está funcionando correctamente, el servidor responde mostrando su página web predeterminada.

Esta comprobación permite verificar que:

- Apache2 se encuentra instalado.
- El servicio está activo.
- El servidor está respondiendo a solicitudes HTTP.
- La computadora puede actuar al mismo tiempo como servidor y como cliente.

Apache2 utiliza normalmente el puerto HTTP 80 para atender estas solicitudes.


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\APACHE WORKS.png
---

# 5. Acceso al directorio utilizado por Apache2

## Comando utilizado

```bash
cd /var/www/html/
```

## Descripción

El comando `cd` se utiliza para cambiar de directorio dentro de la terminal.

`cd` significa:

```text
Change Directory
```

En este caso se utilizó:

```bash
cd /var/www/html/
```

para ingresar al directorio:

```text
/var/www/html/
```

Este es el directorio utilizado por defecto por Apache2 para almacenar los archivos web que serán servidos y mostrados al navegador.

Después de ejecutar el comando, la terminal queda ubicada dentro de dicho directorio.

La línea de la terminal puede cambiar de algo similar a:

```text
usuario@ubuntu:~$
```

a:

```text
usuario@ubuntu:/var/www/html$
```

Esto indica que se ingresó correctamente al directorio correspondiente.

---

# 6. Verificación del directorio actual

## Comando utilizado

```bash
pwd
```

## Descripción

El comando `pwd` permite conocer el directorio actual en el que se encuentra ubicado el usuario dentro de la terminal.

`pwd` significa:

```text
Print Working Directory
```

Después de haber ejecutado:

```bash
cd /var/www/html/
```

se utilizó:

```bash
pwd
```

para comprobar que realmente se había ingresado al directorio correcto.

El resultado esperado es:

```text
/var/www/html
```

Esto permite verificar de manera directa la ubicación actual dentro del sistema de archivos.

---

# 7. Visualización de los archivos del directorio

## Comando utilizado

```bash
ls -l
```

## Descripción

El comando `ls` permite mostrar los archivos y directorios existentes dentro de la ubicación actual.

Al agregar la opción:

```text
-l
```

la información se muestra en un formato detallado.

Por lo tanto:

```bash
ls -l
```

permite visualizar información como:

- Permisos del archivo.
- Propietario.
- Grupo.
- Tamaño del archivo.
- Fecha de modificación.
- Nombre del archivo.

Al ejecutar este comando dentro de:

```text
/var/www/html/
```

se puede observar el archivo principal utilizado por Apache2.

Uno de los archivos que puede encontrarse es:

```text
index.html
```

El archivo `index.html` es el documento que Apache2 muestra automáticamente cuando un usuario ingresa a:

```text
http://localhost
```

sin especificar otro archivo.

## Evidencia


![alt text](<../../../../PRACTICAS/CAPTURAS TARE4/CAP5 .png>)
```bash
cd /var/www/html/
pwd
ls -l
```

También debe observarse la ruta:

```text
/var/www/html
```

y el archivo:

```text
index.html
```

<!-- INSERTAR AQUÍ LA CAPTURA DEL PASO 5, 6 Y 7 -->

---

# 8. Creación de una copia de respaldo del archivo index.html

## Comando utilizado

```bash
sudo mv index.html index.html.bak
```

## Descripción

Antes de crear el nuevo archivo `index.html`, se realizó una copia de respaldo del archivo original de Apache2 mediante un cambio de nombre.

El comando utilizado fue:

```bash
sudo mv index.html index.html.bak
```

El comando está compuesto por:

- `sudo`: permite realizar la operación con privilegios administrativos.
- `mv`: permite mover archivos o cambiar su nombre.
- `index.html`: corresponde al archivo original.
- `index.html.bak`: corresponde al nuevo nombre asignado al archivo.

En este caso, el archivo no fue eliminado.

Únicamente se cambió su nombre de:

```text
index.html
```

a:

```text
index.html.bak
```

La extensión `.bak` se utiliza comúnmente para identificar archivos de respaldo o copias de seguridad.

De esta manera se conserva el archivo original de Apache2 en caso de que posteriormente sea necesario restaurarlo.

---

# 9. Verificación de la copia de respaldo

## Comando utilizado

```bash
ls -l
```

## Descripción

Después de cambiar el nombre del archivo original, se utilizó nuevamente:

```bash
ls -l
```

para verificar el contenido del directorio.

Después del cambio debería observarse el archivo:

```text
index.html.bak
```

Esto confirma que el archivo original de Apache2 fue conservado como una copia de respaldo.

## Evidencia


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\CAP5 .png
---

# 10. Creación y edición del nuevo archivo index.html

## Comando utilizado

```bash
sudo nano index.html
```

## Descripción

El comando `nano` permite crear y editar archivos de texto directamente desde la terminal de Ubuntu.

Para esta actividad se utilizó:

```bash
sudo nano index.html
```

El comando está compuesto por:

- `sudo`: permite abrir y modificar el archivo con privilegios administrativos.
- `nano`: corresponde al editor de texto utilizado desde la terminal.
- `index.html`: es el archivo que se desea crear o modificar.

Fue necesario utilizar `sudo` debido a que el directorio:

```text
/var/www/html/
```

es un directorio protegido del sistema y normalmente requiere privilegios administrativos para poder modificar sus archivos.

Al ejecutar el comando se abre el editor Nano directamente dentro de la terminal.

---

# 11. Contenido agregado al archivo index.html

Dentro del editor Nano se agregó un documento HTML sencillo que contiene la información solicitada en la actividad.

El contenido utilizado sigue una estructura similar a la siguiente:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Actividad Apache2</title>
</head>
<body>
    <p>Carne: CARNÉ DEL ESTUDIANTE</p>
    <p>Nombre completo: NOMBRE COMPLETO DEL ESTUDIANTE</p>
</body>
</html>
```

Dentro del archivo se sustituyeron los datos de ejemplo por el carné y el nombre completo correspondientes.

La etiqueta:

```html
<p>
```

se utiliza para crear un párrafo dentro de una página HTML.

Por ejemplo:

```html
<p>Carne: CARNÉ DEL ESTUDIANTE</p>
```

muestra el carné del estudiante.

Mientras que:

```html
<p>Nombre completo: NOMBRE COMPLETO DEL ESTUDIANTE</p>
```

muestra el nombre completo.

No fue necesario agregar diseño, estilos CSS, imágenes ni otros elementos debido a que la actividad únicamente solicita mostrar el carné y nombre completo.

## Evidencia


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\NANO.png
---

# 12. Guardado del archivo utilizando Nano

## Combinación utilizada

```text
Ctrl + O
```

## Descripción

Después de escribir el contenido del archivo dentro de Nano, se utilizó la combinación:

```text
Ctrl + O
```

para guardar los cambios.

En Nano, la combinación:

```text
^O
```

representa:

```text
Ctrl + O
```

Después de presionar esta combinación, Nano solicita confirmar el nombre del archivo.

Puede mostrarse algo similar a:

```text
File Name to Write: index.html
```

Debido a que el archivo debe conservar el nombre `index.html`, no es necesario modificarlo.

Para confirmar el guardado se presiona:

```text
Enter
```

Después de esto, Nano guarda el contenido dentro del archivo.

---

# 13. Salida del editor Nano

## Combinación utilizada

```text
Ctrl + X
```

## Descripción

Después de guardar correctamente el archivo, se utilizó:

```text
Ctrl + X
```

para salir del editor Nano.

Dentro de Nano, la opción:

```text
^X
```

significa:

```text
Ctrl + X
```

Al presionar esta combinación, el editor se cierra y se regresa nuevamente a la terminal de Ubuntu.

---

# 14. Verificación del nuevo archivo index.html

## Comando utilizado

```bash
ls -l
```

## Descripción

Después de salir de Nano, se utilizó nuevamente:

```bash
ls -l
```

para verificar los archivos existentes dentro de:

```text
/var/www/html/
```

En este punto deberían observarse al menos los siguientes archivos:

```text
index.html
index.html.bak
```

El archivo:

```text
index.html
```

corresponde al nuevo archivo creado con el carné y nombre completo.

El archivo:

```text
index.html.bak
```

corresponde a la copia de respaldo del archivo original de Apache2.

De esta manera se verifica que el nuevo archivo fue creado correctamente sin eliminar definitivamente el archivo original.

---

# 15. Visualización del contenido de index.html desde la terminal

## Comando utilizado

```bash
cat index.html
```

## Descripción

El comando `cat` permite visualizar directamente desde la terminal el contenido de un archivo de texto.

En este caso se ejecutó:

```bash
cat index.html
```

para comprobar que el archivo contenía correctamente el código HTML creado anteriormente.

El resultado mostrado en la terminal debe ser similar a:

```html
<!DOCTYPE html>
<html>
<head>
    <meta charset="UTF-8">
    <title>Actividad Apache2</title>
</head>
<body>
    <p>Carne: CARNÉ DEL ESTUDIANTE</p>
    <p>Nombre completo: NOMBRE COMPLETO DEL ESTUDIANTE</p>
</body>
</html>
```

Esta comprobación permite verificar desde la propia terminal que el archivo fue guardado correctamente.

También permite demostrar que el contenido solicitado se encuentra almacenado dentro de:

```text
/var/www/html/index.html
```

## Evidencia


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\CATINDEX.png
---

# 16. Verificación final del archivo desde el navegador

## Dirección utilizada

```text
http://localhost
```

## Descripción

Finalmente, se regresó al navegador y se actualizó la página:

```text
http://localhost
```

Para recargar la página puede utilizarse la opción de actualización del navegador o la combinación:

```text
Ctrl + R
```

Cuando el navegador solicita nuevamente la página a Apache2, el servidor busca automáticamente el archivo:

```text
/var/www/html/index.html
```

y envía su contenido al navegador.

Debido a que el archivo original fue reemplazado por el nuevo documento HTML, la página predeterminada de Apache2 deja de mostrarse.

En su lugar deben aparecer los datos ingresados dentro del archivo:

```text
Carne: CARNÉ DEL ESTUDIANTE

Nombre completo: NOMBRE COMPLETO DEL ESTUDIANTE
```

Esto confirma que el servidor Apache2 está leyendo correctamente el nuevo archivo `index.html`.

## Evidencia


c:\Users\mocho\OneDrive\Escritorio\USAC DANIEL CABRERA\4to SEMESTRE\PRACTICAS\CAPTURAS TARE4\EN NAVEGADOR.png
---

