# **9. git checkout**

## Descripción:

El comando `git checkout...` tiene **dos funciones principales**:

1. **Cambiar entre las ramas** que se encuentren de manera local, en el commit al que se apunte actualmente en esa rama, que por lo general, suele ser el último, usando...

```
git checkout <rama>
```

...sustituyendo `<rama>` por el nombre exacto de la rama a la que se quiere saltar.

2. **Saltar a otra versión de un archivo**, especificando el hash del commit y el archivo:

```
git checkout <commit> <archivo>
```

## Sintaxis y parámetros

Mencionado anteriormente, la forma más común de usar el comando es `git checkout <rama>` para cambiar entre las ramas locales, pero esto se puede ver impedido por cambios no commiteados todavía, ya que pueden perderse, de forma que **no será permitido cambiar a otra rama hasta que los cambios realizados sean guardados con un commit**.

Usar el comando sin especificar una rama o un commit solo devolverá información respecto a la rama actual.

Dentro del comando general, existen varios parámetros que utilizan su propia sintaxis para realizar diferentes acciones, algunos de los más comúnes son:

- `git checkout -b <nueva-rama> [<punto-de-inicio>]`

  Insertando el parámetro `-b`, es posible **crear una nueva rama** escribiendo el nombre luego del parámetro y **cambiar a ella automáticamente**.

  Por defecto, la nueva rama iniciará con los contenidos que hayan en la rama en la que se esté posicionado a la hora de ejecutar el comando, **como si se tratara de una copia**, pero es posible especificar el hash del commit que se quiera utilizar como punto de inicio luego del nombre de la rama.

- `git checkout -f <rama>`

  Fuerza el cambio de rama, incluso si hay cambios que no se hayan guardado con un commit.

- `git checkout (-m/--merge) <rama>`

  Permite realizar un merge temporal de los archivos modificados con la rama especificada, los cambios en la rama actual se mergean en la rama destino.

  Funciona como cualquier merge: en caso de no poder combinarse de forma automática, se deberán solucionar los conflictos de forma manual.

- `git checkout <rama/commit> [--] <ruta>`

  Reemplaza los archivos especificados en la ruta por la versión de esos archivos que se encuentran en la rama o commit especificados, añadiendolos al staging area.

- `git checkout (-q/--quiet) <rama>`

  Cambia de rama sin mensajes informativos en consola.

## Concepto de `HEAD` y `DETACHED HEAD`

Cuando se cambia entre ramas y commits, se utiliza un puntero dentro del repositorio que indica donde la posición donde el usuario se encuentra dentro del repositorio, este puntero que indica tu posición se denomina `HEAD`.
Este `HEAD` normalmente apunta a una rama, y esta rama apunta a un commit: `HEAD -> main -> commit A`. A la hora de hacer un commit nuevo, Git sabrá que debe agregarlo a la rama main porque posicionalmente el `HEAD` se encuentra en la rama main, que sería lo mismo que decir que "estamos parados" en la rama main.

Cuando el `HEAD` deja de apuntar a una rama y pasa a apuntar a un commit (`HEAD -> commit`) en particular, la "cabeza" se desancla, y se entra en el estado denominado como `DETACHED HEAD`. Al realizar un commit de esta forma, como no forma parte de ninguna rama, este commit queda "huérfano" y eventualmente será eliminado por Git, a menos que se cree una rama nueva para mantenerlo.

## Comandos similares

- `git switch...`

  Se trata de un comando introducido mucho despues de `git checkout...`, que podría considerarse como su sucesor moderno. Su intención es ser de una sintaxis más clara, reduciendo errores y evitando confusiones a la hora de cambiar de rama o restaurar archivos.

- `git restore...`

  Se utiliza para restaurar archivos y descartar cambios, sirviendo como una alternativa con sintaxis más clara de `git checkout <rama/commit> [--] <ruta>`.

- `git branch`

  Se puede utilizar para crear ramas nuevas, al igual que `git checkout -b <nueva-rama>`.
