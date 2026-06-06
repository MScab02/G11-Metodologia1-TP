# **6. git commit**

## Descripción

Este comando crea un "commit" con el contenido actual en el "staging area".

Un commit es una captura permanente del estado del proyecto, guardando los archivos deseados con el contenido hasta ese momento. Para cada commit se genera un identificador único (hash) y almacena metadatos importantes, como la fecha y hora en la que se creó, nombre y mail (si el usuario ingresó uno) del autor del commit y una breve descripción del contenido o cambio realizado redactado por el autor. Cada commit se convierte en la nueva cabeza (HEAD) de la rama actual en la que el commit fue creado.

La principal funcionalidad de los commits es como punto de control, resultando útiles tanto como para tener un registro histórico del proyecto con los cambios que se han realizado a través del tiempo y poder utilizarse como documentación, como para reestablecer estos datos anteriores y así volver a un estado anterior del proyecto.

## Sintaxis y parámetros

El comando para realizar commits se escribe de la siguiente manera:

```
git commit [<parámetro>] [--] [<ruta>...]
```

Al ejecutar `git commit`, se abrirá en el editor de código una pestaña nueva a modo de bloc de notas, donde se puede escribir el mensaje del commit que se va a incluir en los metadatos de forma más interactiva, la primera línea se considera el título del commit, y la descripción del commit se suele escribir a partir de la tercera línea. Cuando se finaliza, se oprime el botón "Confirmar" y se realiza el commit.

En `[<parámetro>]` se puede especificar diferentes opciones para "configurar" el comando según se necesite para realizar acciones específicas relacionada a crear commits, los cuales se detallan a continuación:

- `-a` / `--all`

  Lleva a los archivos previamente trackeados con un `git add...` (es decir, aquellos modificados o eliminados) al index de forma automática para realizar un commit rápido.

- `-p` / `--patch`

  Permite seleccionar interactivamente los archivos a incluirse en el commit. Funcionalmente igual al mismo parámetro del comando `git add...`.

- `-m` `<msg>` / `--message=<msg>`

  Omite la pantalla de escritura de commit interactiva, y en su lugar usa el contenido de `<msg>` como mensaje para el commit. En caso de usar múltiples `-m`, se concatenan como párrafos distintos. Los comentarios deben escribirse entre dos comillas dobles `" "`.

  Ejemplo:

  ```
  git commit -m "Este es un mensaje para un commit."
  ```

- `--amend`

  Permite modificar el último commit realizado, cambiando su título o su contenido, en caso de haber olvidado archivos, o incluido archivos que no debía.

- `-C` `<commit>` / `--reuse-message=<commit>`

  Reutiliza los metadatos (mensaje, fecha, hora y autor) del commit especificado usando su hash en `<commit>`.

- `-c` `<commit>` / `--reedit-message=<commit>`

  Igual que `-C`, pero en este caso, el editor es invocado, permitiendo editar el mensaje del commit.

- `-F` `<archivo>` / `--file=<archivo>`

  Se especifica la ruta de un archivo en `<archivo>` y se usa su contenido como mensaje del commit.

- `--cleanup=<modo>`

  Permite decidir cómo se limpiara el mensaje del commit antes de realizarse especificando el tipo en `<modo>`, pudiendo ser `strip`, `whitespace`, `verbatim`, `scissors` o `default`.
  - `strip`

    Elimina las líneas vacías al principio y al final del documento, colapsa varias lineas vacías en una sola, en caso de haber, y también elimina los comentarios (filas comenzadas con `#`).

  - `whitespace`

    Similar a `strip`, pero conservando los comentarios.

  - `verbatim`

    Mantiene el mensaje intacto tal cual como se escribió.

  - `scissors`

    Funciona como `whitespace`, pero si el mensaje va a ser editado, se trunca el contenido desde una línea de recorte hacia abajo, con la línea incluida.

    La línea se ve así:

    ```
    # ------------------------ >8 ------------------------
    ```

  - `default`

    Igual que `strip` en caso de que el mensaje vaya a ser editado, sino, actúa como `whitespace`.

La parte de `[<ruta>]` permite commitear los archivos de la ruta especificada sin tener en cuenta los archivos que hayan en el index, pero estos no se pierden, sino que se mantienen en el index para un commit futuro.

## Comandos similares

- `git stash...`

  Guarda los cambios de manera temporal sin crear un commit, útil para limpiar el área de trabajo y permitir cambiar de ramas.

- `git revert...`

  Deshace los cambios del commit anterior, creando un commit nuevo en el proceso para preservar el historial.
