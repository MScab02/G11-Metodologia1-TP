# **9. git checkout**

El comando `git checkout` se utiliza principalmente para navegar entre 
diferentes versiones, ramas o commits en el repositorio. Al ejecutarlo, 
Git actualiza los archivos del directorio de trabajo para que coincidan 
con el estado exacto de la versión solicitada, moviendo el puntero HEAD 
hacia allí.

Es uno de los comandos más versátiles de Git, ya que permite tanto cambiar 
de rama como restaurar archivos a un estado anterior.

## Sintaxis y parámetros

```
git checkout [<parámetros>] [<rama o commit>] [--] [<archivo>]
```

Usar el comando sin especificar una rama o un commit solo devolverá información respecto a la rama actual.

## Parámetros principales

- `-b <nombre>`  
  Crea una rama nueva y se mueve a ella automáticamente.

- `-B <nombre>`  
  Igual que `-b` pero si la rama ya existe, la resetea al commit actual.

- `--detach`  
  Mueve HEAD a un commit específico sin estar en ninguna rama.

- `-f` / `--force`  
  Fuerza el cambio de rama aunque haya cambios sin commitear, 
  descartándolos.

## Usos más comunes

- `git checkout -b <nueva-rama> [<punto-de-inicio>]`

  Insertando el parámetro `-b`, es posible **crear una nueva rama** escribiendo el nombre luego del parámetro y **cambiar a ella automáticamente**.

  Por defecto, la nueva rama iniciará con los contenidos que hayan en la rama en la que se esté posicionado a la hora de ejecutar el comando, **como si se tratara de una copia**, pero es posible especificar el hash del commit que se quiera utilizar como punto de inicio luego del nombre de la rama.

- `git checkout (<rama>|<commit>)

  Permite cambiar entre ramas ingresando el nombre de una rama, o entre commits especificando el hash de un commit específico.
  
- `git checkout -- <archivo>`

  Descarta los cambios locales de ese archivo y lo vuelve al estado del último commit.


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

_Nota_
  > A partir de versiones más recientes de Git, se recomienda usar `git switch` 
  > para cambiar de rama y `git restore` para restaurar archivos, ya que dividen 
  > las responsabilidades de `git checkout` en comandos más claros y específicos.
