# Taller pre Hackathon Express 2017. Versionado. Git y Github

Enlace a la presentación: [https://goo.gl/q8Y8CF](https://goo.gl/q8Y8CF)

# Mini Tutorial Git

Los siguientes comandos están sacados de la referencia que pueden descargar desde éste [enlace](https://services.github.com/on-demand/downloads/github-git-cheat-sheet.pdf "GIT Cheat Sheet"). Según mi criterio los que tendrían que saber usar son los siguientes:

#### 1. Creando el repositorio local
Podemos crear un repositorio de dos maneras:

#### 1.1. Clonando un repositorio existente en GitHub o BitBucket: git clone
Podemos descargarnos el repositorio en cuestión de la siguiente manera:

```bash
$ git clone https://github.com/Arcangel617/Legislacion_GNUsticia.git

```
Con eso se nos crea una copia exacta de lo que tengamos en GitHub y solo restaría configurarlo.

#### 1.2. Inicializando un repositorio: git init
Otra forma de crear un repositorio local es la siguiente:

```bash
$ git init nombre_del_proyecto

```
Esto nos creará una carpeta en la cual vamos a tener que especificar la url del repositorio de la siguiente manera:
```bash
$ git remote add origin https://github.com/Arcangel617/Legislacion_GNUsticia.git
```

Suponiendo que ya tenemos nuestro proyecto creado pero aún no creamos nuestro repositorio en GitHub por ejemplo, lo que 
tenemos que hacer es lo siguiente:
```bash
$ cd nombre_del_proyecto
$ git init
$ git remote add origin https://github.com/Arcangel617/Legislacion_GNUsticia.git

```
ahora, si no tenemos nada creado... lo mas conveniente es hacer lo siguiente:
```bash
$ mkdir nombre_del_proyecto
$ cd nombre_del_proyecto
$ git init
$ git remote add origin https://github.com/Arcangel617/Legislacion_GNUsticia.git

```

#### 2. Configurando el repositorio local: git config

Si van a realizar contribuciones, es decir, hacer commits a un repositorio externo ya sea GitHub o BitBucket, lo primero
que tienen que hacer es configurar su repositorio local de la siguiente manera:

> Nota: Tanto el usuario como el correo tienen que ser los mismos que utilizaron para
crear su cuenta. La importancia de realizar este paso es que sin esto no van a poder hacer commits.

Para setear el usuario tienen que utilizar que utilizar el siguiente parámetro:
```bash
$ git config user.name "[su_usuario]"

```
Para setear el correo tienen que utilizar que utilizar el siguiente parámetro:
```bash
$ git config user.email "[correo]"

```

> Nota: El ejemplo que les muestro aca se aplica solo a un repositorio. Lo hago asi porque tengo cuentas distintas
en GitHub y BitBucket. Si lo quieren configurar de manera global tienen que agregar el flag --global.
```bash
$ git config --global user.name "[su_usuario]"
$ git config --gloabl user.email "[correo]"

```

#### 3. Trabajando sobre el repositorio
Cuando se trabaja en sobre el repositorio casi siempre se sigue el siguiente flujo:

#### 3.1. Actualizando nuestro repositorio local: git pull

En algunas ocasiones será necesario actualizar nuestro repositorio debido a que otros colaborares pudieron haber
realizados cambios en el repositorio remoto. Para actualizar hacemos lo siguiente:

```bash
$ git pull

```
> Nota: Es posible que se tengan que resolver conflictos después de ejecutar éste comando.

#### 3.2. Consultando el estado del respositorio: git status

Muestra el estado del respositorio local, es decir, se muestra si hubo un cambio en un archivo, si se borró algún
archivo o si se agregaron nuevos archivos.

```bash
$ git status

```

#### 3.3. Agregando modificaciones al stagin area: git add
Antes de subir cambios al repositorio remoto primero tenemos que ir agregando al stagin area los cambios que
queremos incluir. Lo podemos hacer de las siguientes maneras:

+ especificando los archivos que queremos agregar

```bash
$ git add archivo1.txt archivo2.xml

```
+ especificando que queremos agregar todos los archivos que no se encuentren ignorados ni hayan sido borrados
```bash
$ git add . 
```
+ especificando todos los archivos que fueron modificados (presta atención al .gitignore)
```bash
$ git add *

```
+ especificando que agregue todos los archivos que no se encuentren ignorados, incluyendo además aquellos que fueron borrados.
```bash
$ git add --all

```

#### 3.4. Dejando registro de los cambios realizados: git commit
Siempre que hagamos modificaciones es recomendable notificar que fue lo que se hizo. Para ello tenemos que hacer lo
siguiente:

```bash
$ git commit -m "descripción_de_la_tarea_realizada"

```

#### 3.5. Subiendo los cambios en el reposotorio remoto: git push
Una vez que se realizaron todas las tareas, hay que subir los cambios. Para ello hacemos lo siguiente:

```bash
$ git push -u origin master

```
> Nota: Para éste ejemplo se asume que los cambios se realizan en la rama master.

#### 4. Deshaciendo cambios: git reset

Supongamos que hicimos agregamos un archivo y después nos arrepentimos de lo que hicimos. La forma 
correcta de sacarlo del stagin area es la siguiente:

```bash
$ git reset archivo1.txt

```

### 5. Trabajando con ramas: git branch

+ Para listar todas las ramas que tegamos hacemos lo siguiente:
```bash
$ git branch

```

+ Para crear una rama basta con escribir lo siguiente:

```bash
$ git branch nombre_de_la_rama

```

+ Si queremos trabajar en una rama especifica, debemos hacer lo siguiente:

```bash
$ git checkout nombre_de_la_rama

```

+ Si queremos borrar una rama, tenemos que hacer lo siguiente:

```bash
$ git branch -d "nombre_de_la_rama"

```