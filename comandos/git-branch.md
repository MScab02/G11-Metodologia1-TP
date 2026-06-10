# **1. git add**

## Descripción

El comando **`git branch`** se utiliza para verificar la rama en la que estas, mostrar la lista de ramas locales y remotas, agregar ramas y eliminarlas. Tambien permite configurar relaciones de tracking y consultar información sobre ramas existentes.

## Sintaxis y parámetros

- `-d` y `--delete`

Los parámetros `d` y `--delete` borran ramas que no tienen cambios sin fusionar en `HEAD` con --track o `--set-upstream-to`.

- `--create-reflog`

"reflog" significando registro de referencias en español, crea una bitacora de referencias que registra los cambios del puntero hasheadas con expresiones basadas en sha1 como `<branch-name>@{yesterday}`. En general, este comando no es necesario activarlo en git's que no son bare-bone debido a que esta activado naturalmente por default.

- `-m` y `--move`

Mueve o renombra una rama con su configuración y reflog.

- `-c` y `--copy`

Copia una rama con su configuración y reflog.

- `-f` y `--force`

Reinicia `<branch-name>` hasta su `<start-point>`. Si se usa en combinacion con `-d` o `--delete` te permite borrar una rama ignorando el estado de union. en combinacion con `-m` o `--move` te permite renombrar la rama aun si ya existe una rama que tiene ese mismo nombre, `-c` o `--copy`.

- `-D`

Atajo para `--delete --force`.

- `-M`

Atajo para `--move --force`

- `-C`

Atajo para `--copy --force`

- `--color[=<when>]`

Colorea ramas para resaltar ramas activas, locales y remotas. El valor `[=<when>]` puede ser **always**, **auto** o **never**.

- `--no-color`

Elimina el color de las ramas de la misma forma que `--color=never`.

- `-i --ignore-case`

Es un parametro que te permite ignorar mayusculas filtrando ramas.

- `--omit-empty`

No imprime newline despues de referencias formateadas donde dicho formato se expande al string vacio.

- `--column[=<options>]` y `--no-column`

Muestra las ramas listadas en columnas, se puede configurar para que no se muestra de tal forma con **always** o **never** con `[=<options>]`, es equivalente a `--no-column` y reactivar con `--column`,

- `--sort=<key>`
  Ordena las ramas segun la clave especificada en `<key>`. Algunas claves comunes son refname, committerdate y authourdate y mas opciones que se pueden encontrar aqui https://git-scm.com/docs/git-for-each-ref .

- `-r` y `--remotes`
  Muestra exclusivamente las ramas remotas.

- `-a` y `--all`
  Muestra ramas remotas y locales

- `-l` y `--list`
  Lista las ramas que coinciden con un patron especificado. Si no se proporciona un patron, muestra todas las ramas locales.

- `--show-current`
  .

- `-v`, `-vv` y `--verbose`
  .

- `-q` y `--quiet`
  .

- `--abbrev=<n>`
  .

- `--no-abbrev`
  .

- `-t --track[=(direct|inherit)]`
  .

- `--no-track`
  .

- `--recurse-submodules`
  .

- `--set-upstream`
  .

- `-u <upstream>` y `--set-upstream-to=<upstream>`
  .

- `--unset-upstream`
  .

- `--edit-description`
  .

--contains [<commit>]
.

--no-contains [<commit>]
.

--merged [<commit>]
.

--no-merged [<commit>]
.

--points-at <object>
.

--format <format>
.

<branch-name>
.

<start-point>
.

<old-branch>
.
