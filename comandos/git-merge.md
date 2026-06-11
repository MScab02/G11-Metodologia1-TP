# git merge

## Descripción

El comando `git merge` sirve para combinar los historiales y cambios de dos
ramas diferentes en una sola. Es la herramienta estándar de Git para integrar
el trabajo realizado en una rama de desarrollo, como una nueva funcionalidad,
con la rama principal del proyecto.

Cuando se ejecuta, Git compara los historiales de ambas ramas e intenta combinar automáticamente los cambios. Si los archivos modificados no presentan incompatibilidades, la fusión se realiza de forma automática. En cambio, si dos ramas modificaron las mismas líneas de un archivo, se producirá un conflicto que deberá resolverse manualmente.

## Sintaxis

```
git merge [<parámetros>] <nombre-de-la-rama>
```

## Tipos de merge

**Fast-forward:**  
Ocurre cuando la rama principal no tuvo cambios desde que se creó la rama
a fusionar. Git simplemente mueve el puntero hacia adelante sin crear un
commit extra.

**Merge commit:**  
Cuando ambas ramas tuvieron cambios, Git crea un nuevo commit que une los
dos historiales. Este commit queda registrado en el historial.

**Conflicto:**  
Si dos ramas modificaron las mismas líneas de un archivo, Git no puede
resolver la fusión automáticamente y genera un conflicto que hay que
resolver manualmente.

## Usos más comunes

**Fusionar una rama con la rama actual:**

```
git merge <rama>
```

Donde `<rama>` corresponde a la rama cuyos cambios se desean incorporar a la rama actual.

**Fusionar forzando un merge commit aunque no sea necesario:**

```
git merge --no-ff <nombre-de-la-rama>
```

**Abortar un merge en caso de conflicto:**

```
git merge --abort
```

## Parámetros principales

- `--no-ff`  
  Fuerza la creación de un merge commit aunque sea posible hacer fast-forward. Es útil para mantener un historial más claro.

- `--ff-only`
  Permite realizar el merge únicamente si puede completarse mediante fast-forward. Si no es posible, la operación se cancela.

- `--squash`  
  Combina todos los commits de la rama a fusionar en uno solo antes
  de hacer el merge.

- `--abort`  
  Cancela el merge en curso y vuelve al estado anterior.

- `--commit` / `--no-commit`  
  Controla si se crea el commit de merge automáticamente o no.

## Ejemplo de uso

```
git checkout main
git merge feature/nueva-funcionalidad
```

Esto fusiona los cambios de la rama `feature/nueva-funcionalidad`
dentro de `main`.

## Comandos relacionados

- `git rebase` — otra forma de integrar cambios entre ramas, pero
  reescribiendo el historial en lugar de crear un merge commit.
- `git branch` — para ver o gestionar las ramas antes de fusionarlas.
- git pull — Puede ejecutar internamente un merge al integrar cambios provenientes de un repositorio remoto.
