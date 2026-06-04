# **1. git add**

## Descripción

El comando **`git add`** permite pasar archivos _nuevos o modificados_ a lo que se conoce como _staging area_, el cual es un espacio "intermedio" donde se van enlistando los archivos que van a ser guardados en el siguiente commit a ejecutar, para posteriormente ser guardados.

No existe un límite de usos para este comando, se puede utilizar tantas veces como sea necesario para incluir los archivos o parte de archivos que el programador desee pasar al staging area con el fin de mantener un órden y coherencia entre las cosas que se van a guardar en el commit.
Para esto, existen diferentes parámetros que se deben utilizar para realizar diferentes funciones en lo que se refiere a añadir, quitar o modificar archivos en el staging area.

## Sintaxis y parámetros

El comando se utiliza de la siguiente forma en una terminal:

```
git add [<parámetro>] [--] (ruta)
```

### (ruta):

En esta parte del comando, van los archivos a añadir al staging area.

Se puede usar rutas específicas para añadir archivos específicos, o se puede utilizar `*` o `.` para añadir todos los archivos modificados y creados hasta el momento. De la misma manera, se puede añadir todos archivos del mismo tipo escribiendo la extensión luego del asterisco. Por ejemplo, con `*.js`, se añadirán al staging area todos los archivos JavaScript modificados o creados desde cero.

También puede escribirse la ruta de una carpeta entera para realizar la misma acción con los archivos de una carpeta en particular.

La única excepción a este comando, son aquellos archivos que sean explícitamente excluidos de ser agregados al staging area luego de su creación o modificación. por medio del uso del archivo `.gitignore`. Este archivo funciona a modo de 'lista negra', en la cual se puede escribir rutas de archivos específicos o carpetas enteras para que estos no sean guardados en los commits, así como el mismo archivo.

### Parámetros

Estos son las opciones que se pueden escribir en el espacio de `[<parámetro>]` en la sintaxis del comando para ejecutar el comando de diferente manera y realizar distintas acciones relacioandas con la adición de los archivos al index.

- `-A` `--all`
  Especificando este parámetro, hace que todos los cambios realizados se registren en el staging area: agrega archivos nuevos, modificados y eliminados.
- `-u` `--update`
  Solo se agregan al staging area los archivos que ya se han rastreado previamente, deja de lado los archivos nuevos.
- `-i` `--interactive`
  Permite gestionar los cambios a agregar al staging area de forma interactiva a través de un menú.
- `-p` `--patch`
  Permite seleccionar y agregar fragmentos de archivos de forma interactiva, a modo de "parches".
- `-e` `--edit`
  Permite editar manualmente el parche a agregar, similar a `--patch` pero de forma no interactiva y más precisa.
- `-f` `--force`
  Permite saltarse las restricciones de `.gitignore`, añadiendo forzosamente estos archivos ignorados.
- `-n` `--dry-run`
  Muestra los archivos que se van a agregar, sin agregarlos realmente. Funciona a modo de previsualización.
- `-v` `--verbose`
  Muestra información detallada sobre los archivos que se están agregando al staging area.
- `-h` `--help`
  Muestra estos comandos para ayudar al usuario a saber qué puede hacer el comando y cómo, a modo de ayuda.
- `--refresh`
  Actualiza la información del staging area sin agregar cambios nuevos.
- `--ignore-errors`
  Continúa agregando otros archivos en caso de encontrar errores, los archivos con errores los salta.

## Comandos similares

- `git stage...`
  Realiza exactamente la misma función que `git add...`.
- `git commit -a...`
  Similar a `git add -u...`, permitiendo actualizar los archivos ya trackeados.
- `git update-index...`
  Es posible añadir archivos con el comando `git update-index --add...`, manipulando directamente el staging area, pero Git, de forma interna, ya usa mecanismos relacionados para implementar `git add...`. Resulta, al final, más complejo y menos intuitivo.
- `git restore --staged...`
  Operación directamente inversa. Quita archivos del staging area sin perder los cambios realizados en el directorio de trabajo.
