# git checkout

## Descripción

El comando `git checkout` se utiliza principalmente para navegar entre 
diferentes versiones, ramas o commits en el repositorio. Al ejecutarlo, 
Git actualiza los archivos del directorio de trabajo para que coincidan 
con el estado exacto de la versión solicitada, moviendo el puntero HEAD 
hacia allí.

Es uno de los comandos más versátiles de Git, ya que permite tanto cambiar 
de rama como restaurar archivos a un estado anterior.

## Sintaxis

```
git checkout [<parámetros>] [<rama o commit>] [--] [<archivo>]
```

## Usos más comunes

**Cambiar a una rama existente:**
```
git checkout <nombre-de-la-rama>
```

**Crear una rama nueva y cambiarse a ella en un solo paso:**
```
git checkout -b <nombre-de-la-rama>
```

**Volver a un commit anterior:**
```
git checkout <hash-del-commit>
```
Esto pone el repositorio en un estado llamado "detached HEAD", donde podés 
ver el estado del proyecto en ese momento pero sin estar en ninguna rama.

**Restaurar un archivo a su último estado commiteado:**
```
git checkout -- <archivo>
```
Esto descarta los cambios locales de ese archivo y lo vuelve al estado del 
último commit.

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

## Nota

A partir de versiones más recientes de Git, se recomienda usar `git switch` 
para cambiar de rama y `git restore` para restaurar archivos, ya que dividen 
las responsabilidades de `git checkout` en comandos más claros y específicos.

## Comandos relacionados

- `git switch` — reemplaza a `git checkout` para cambiar de rama.
- `git restore` — reemplaza a `git checkout` para restaurar archivos.
- `git branch` — para listar o crear ramas.