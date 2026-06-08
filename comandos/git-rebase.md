# **11. git rebase**

## Descripción

El comando `git rebase...` permite "mover" commits de una rama, cambiando el punto de inicio de una rama hasta el último commit de otra rama. Esto se logra creando una copia de los commits de una rama, y pegandolos más adelante en la historia, la principal función de esto es evitar mergeos innecesarios y mantener un historial más lineal.

Por ejemplo, supongamos que tenemos las ramas `main` y `dev`.

```
A --- B --- C --- D (main)
       \
        E --- F --- G (dev)
```

Suponiendo que has estado trabajando en la rama `dev` y desearas "alcanzar" el trabajo hecho en la rama `main`, podes ejecutar el siguiente comando: `git rebase main`.

Esto realiza algo similar a un "cortar y pegar" sobre la rama en que está el HEAD (en este caso, `dev`), "corta" todos los commits, y los "pega" haciendo coincidir el primer commit de `dev` con el último commit de `main`, quedando así:

```
A --- B --- C --- D --- E' --- F' --- G' (main)
```

En caso de ocurrir un conflicto mientras se hace el rebase, se detendrá el proceso en el primer commit que tenga problemas, permitiendo al usuario resolver los conflictos (como cualquier merge) y continuar con `git rebase --continue`, cancelarlo con `git rebase --abort` o saltarse los commits con conflictos con `git rebase --skip`.

## Sintaxis y parámetros

La principal sintaxis de este comando es la siguiente:

```
git rebase [parámetro] [<rama-a-mover>] <rama-destino>
```

`<rama-destino>` se trata de la rama a donde se moverán los commits de la rama declarada en `[<rama-a-mover>]`, cuyo campo es opcional, y en caso de no declarar ninguna rama en ese lugar, se moverá la rama donde se encuentre el HEAD en ese momento.

Existen varios parámetros válidos para cambiar el comportamiento, pero el principal y mas utilizado es `-i`|`--interactive`.

Este comando crea una lista de commits que van a ser rebasados, permitiendo al usuario reordenar commits, unirlos, eliminarlos, dividirlos o editar los mensajes, todo de forma interactiva.

### Resolviendo conflictos durante el rebase

Como se mencionó antes, el rebase se trata de una especie de merge, por lo que también pueden ocurrir conflictos a la hora de realizar un rebase, lo que implica tener que corregir los archivos de forma manual para integrarlos correctamente.

Por cada commit en el que Git detecte un conflicto, el usuario tendrá que utilizar el comando `git commit <opcion>` para continuar con el rebase. En este campo se utilizan parámetros únicos para indicarle a Git qué debe hacer a continuación:

- `--continue`

  Continúa con el proceso de rebase despues de resolver los conflictos pendientes.

- `--skip`

  Se salta el conflicto actual, continuando con el siguiente o terminando el proceso de rebase en caso de ser el último.

- `--abort`

  Cancela el proceso de rebase, deshaciendo los cambios y regresando el HEAD a la rama original, siendo la rama desde donde se hizo el `git rebase...`, o la rama insertada en el campo `<rama-destino>`.

- `--quit`

  También aborta el rebase, pero no regresa el HEAD a la rama original, y el index de cambios tambien se mantiene sin cambiar.

## Diferencias entre mergear y rebasar

La principal diferencia entre un `git merge...` y un `git rebase...` es su comportamiento en el historial del repositorio.

Un merge mantendrá en la historia la existencia de ambas ramas, siendo unidas en algún punto por un commit que une ambas ramas:

```
// 'M' es el commit donde se mergean las ramas
A --- B --- C ------ M --- (rama1)
       \            /
        D -------- E (rama2)
```

En cambio, un rebase unifica las ramas, perdiendo el historial de la rama desde la que se hace el rebase, tampoco se crea un commit de merge en el proceso.

```
A --- B --- C --- D (rama1)
       \
        E --- F --- G (rama2)

|
| // -> git rebase rama2 rama1
v

A --- B --- C --- D --- E' --- F' --- G' (rama1)
```

La `rama2` desaparece y pasa a formar parte de la `rama1`, como si la primera nunca se hubiese creado.

## Comandos similares

- `git merge...`

  Como se mencionó varias veces en el documento, `git merge...` y `git rebase...` cumplen la función de unir ramas, pero su resultado es diferente.

- `git cherry-pick...`

  Permite copiar uno o varios commits específicos de una rama en otra.

- `git pull --rebase`

  Es una combinación de los comandos `git fetch` y `git rebase origin/<rama>`, usado para actualizar una rama sin realizar un commit de merge innecesario.
