# Comandos mas útiles de Git
![alt text](https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/512px-Git-logo.svg.png)

En este repositorio, realizaremos un breve recorrido por los comandos más utilizados para trabajar con Git y gestionar adecuadamente la versión de nuestro código alojado en GitHub. Además, exploraremos cómo Git se ha convertido en una herramienta fundamental en el mundo del desarrollo de software, impulsando la colaboración y la innovación en proyectos de código abierto.
## **Introducción**
Antes de adentrarnos en los detalles de Git y su funcionamiento, es importante realizar un breve repaso para aquellos que puedan haber llegado hasta aquí sin tener conocimiento previo sobre este sistema de control de versiones y cuál es su propósito.

### ¿Qué es Git y cuál es su propósito?
Git es una poderosa herramienta de control de versiones que se utiliza en el mundo del desarrollo de software para rastrear y gestionar cambios en el código fuente de un proyecto. Su propósito principal es proporcionar un sistema eficiente y colaborativo para el seguimiento de modificaciones en archivos, lo que facilita el trabajo en equipo y la gestión de proyectos de cualquier tamaño.

### Importancia del control de versiones
Imagina trabajar en un proyecto de software donde varias personas colaboran en la creación, edición y mejora del código fuente. Sin un sistema de control de versiones como Git, esto podría resultar en un caos completo, con cambios sobrescribiéndose y la imposibilidad de rastrear quién hizo qué y cuándo.

Git resuelve estos problemas al mantener un historial detallado de todas las modificaciones realizadas en un proyecto. Esto significa que puedes:

* Volver atrás en el tiempo y restaurar una versión anterior del código si algo sale mal.
* Colaborar de manera efectiva con otros desarrolladores, fusionando sus cambios de manera ordenada.
* Registrar quién realizó cada cambio y cuándo lo hizo, lo que facilita la responsabilidad y la solución de problemas.

## **Comandos importantes antes de empezar a trabajar con git**

> [!NOTE]
> Previamente deberás haber descargado Git de su página oficial en GitHub.

Siempre es importante tener los siguientes comandos a la mano para poder trabajar correctamente con nuestro repositorio remoto y poder hacer `push` y `pull` sin problemas 

Para empezar siempre es bueno definir nuestro nombre de usuario y configurar nuestro correo electronico

### Configurar User

```
git config --global user.name "Tu Nick"
```
El nombre de usuario es importante para vincular los commits a tu nombre.
### Configurar correo electronico

También puedes cambiar la dirección de correo electrónico asociada a tus commits de git con el comando `git config`. 
```
git config --global user.email "tucorreo@gmail.com"
```

## **Comandos básicos**
### Creación de un repositorio  

Crear un repositorio Git vacío o reiniciar uno existente. Ejecutar `git init` crea un subdirectorio .git en el directorio de trabajo actual, que contiene todos los metadatos Git necesarios para el nuevo repositorio. Estos metadatos incluyen subdirectorios para objetos, referencias y archivos de plantilla.

```
git init
```

### Añadir archivos a la zona de escalonamiento
El comando git add command añade los archivos nuevos o modificados en tu directorio de trabajo al área de preparación de Git.

Añade algún archivo:
```
git add somefile.js
```
Añade todos los archivos:
```
git add .
```
> [!NOTE]
> Previamente deberás haber descargado Git de su páRecordemos que el área de preparación de git es un lugar en la memoria de acceso aleatoria donde se preparan todos los archivos antes de guardar definitivamente estos cambios en la memoria principal.

### Comprobación del estado repo
El comando `git status` muestra el estado del directorio de trabajo y del área de preparación. Te permite ver qué cambios han sido puestos en escena, cuáles no, y qué archivos no están siendo rastreados por Git.
```
git status
```

### Tomar una captura de los cambios
Grabar los cambios en el repositorio. Este comando se utiliza para guardar los cambios en el repositorio local. Se puede utilizar con algunas claves de git, como:

* `- m` para añadir un mensaje a su confirmación
* `- a` para poner en escena todos los archivos en su commit
* `--amend` para reescribir la última confirmación con los cambios que se estén realizando o con un nuevo mensaje de confirmación

```
git commit -m "Commit message"
git commit --amend
git commit --amend -m "New message"
```

### Git Clone
`Git clone` es un comando utilizado para obtener una copia del código fuente existente desde un repositorio remoto (como GitHub, por ejemplo). En términos simples, `Git clone` crea una réplica exacta de la última versión de un proyecto en un repositorio y la almacena en tu computadora." 
```
git clone https://Nombre-Link-DelRpositorio
```

### Git branch
Las ramas son muy importantes en el mundo de git. Mediante el uso de ramas, varios desarrolladores pueden trabajar en paralelo en el mismo proyecto simultáneamente. Podemos usar el comando `git branch` para crear, enumerar y eliminar ramas. Creando una nueva rama:
```
git branch <nombre-branch>
```
Este comando creará una rama localmente. Para insertar la nueva rama en el repositorio remoto, debes usar el siguiente comando:
```
git push -u <remote> <branch-name>
```
Para ver las ramas:
```
git branch or git branch --list
```
Para borrar las ramas:
```
git branch -d <branch-name>
```
### Git checkout
Este es también uno de los comandos Git más utilizados. Para trabajar en una rama, primero debe cambiarse a ella. Usamos `git checkout` principalmente para cambiar de una rama a otra. También podemos usarlo para verificar archivos y confirmaciones.
```
git checkout <nombre-de-tu-rama>
```
Hay algunos pasos que debes seguir para cambiar con éxito entre ramas:  

* Los cambios en tu rama actual deben confirmarse o guardarse antes de cambiar.
* La rama que deseas verificar debe existir en tu local.

También hay un comando de acceso directo que te permite crear y cambiar a una rama al mismo tiempo:
```
git checkout -b <nombre-de-tu-rama>
```
Este comando crea una nueva rama en su local (-b significa rama) y marca la rama como nueva justo después de que se haya creado, si observas bien, el cambio se encuentra en -b.

### Etiquetado
`git tag` etiqueta puntos específicos en la historia de un repositorio.
```
git tag v1.1
```
Para acceder a la lista de etiquetas utilice `git tag -l`. Para borrar sólo hay que pasar una clave específica `git tag -d v1.0`. Para listar las etiquetas remotas: `git ls-remote --tags`. Para reetiquetar Para reetiquetar (cambiar el nombre de la etiqueta existente) sólo tienes que enviar con la tecla de fuerza: `git tag -f v1 v1.1` , en este caso renombrando `v1` con el nuevo `v.1.1.`

## **Comandos básicos para trabajar con repositorios remotos**
### Git push
Después de confirmar los cambios (con git commit), lo siguiente que hay que hacer es enviar estos cambios al servidor remoto. `Git push` sube tus confirmaciones al repositorio remoto.
```
git push <remote> <nombre-rama>
```
Sin embargo, si tu rama se creó recientemente, también debes cargar la rama con el siguiente comando:
```
git push --set-upstream <remote> <nombre-de-tu-rama>
```
O bien:
```
git push -u origin <nombre_de_rama>
```
y listo.

> [!NOTE] 
> Git push solo carga los cambios que están confirmados.

### Git pull
El comando `git pull` se usa para obtener actualizaciones del repositorio remoto. Este comando es una combinación de `git fetch` y `git merge`, lo que significa que, cuando usamos `git pull`, obtienes las actualizaciones del repositorio remoto (`git fetch`) e inmediatamente aplica los últimos cambios en su local (`git merge`). (En simples palabras, sirve para traer el repositorio remoto a tu repositorio local).
```
git pull <remote>
```

> [!WARNING]
> Esta operación puede causar conflictos que debes resolver manualmente.

_Esta guía fue hecha con el apoyo de_ [Apiumhub](https://apiumhub.com/es/tech-blog-barcelona/20-comandos-basicos-de-git-que-todo-ingeniero-qa-debe-conocer/) _y_ [FreeCodeCamp](https://www.freecodecamp.org/espanol/news/10-comandos-de-git-que-todo-desarrollador-debe-conocer/) 
