git merge
Descripción

El comando git merge se utiliza para fusionar los cambios de una rama con otra. Su función principal es integrar el trabajo realizado en distintas líneas de desarrollo dentro de un mismo historial de proyecto.

Cuando se ejecuta, Git compara los historiales de ambas ramas e intenta combinar automáticamente los cambios. Si los archivos modificados no presentan incompatibilidades, la fusión se realiza de forma automática. En cambio, si dos ramas modificaron las mismas líneas de un archivo, se producirá un conflicto que deberá resolverse manualmente.

Es común utilizar este comando cuando una funcionalidad desarrollada en una rama secundaria está lista para incorporarse a una rama principal o de desarrollo.

Sintaxis
git merge <rama>

Donde <rama> corresponde a la rama cuyos cambios se desean incorporar a la rama actual.

Usos más comunes
Fusionar una rama con la rama actual
git merge feature-login

Incorpora los cambios de la rama feature-login a la rama en la que el usuario se encuentra actualmente.

Fusionar cambios descargados del repositorio remoto
git merge origin/main

Integra en la rama actual los cambios obtenidos desde la rama remota main.

Finalizar el desarrollo de una funcionalidad
git checkout dev
git merge feature-git-merge

Permite incorporar a la rama dev el trabajo realizado previamente en una rama de funcionalidad.

Parámetros principales
--no-ff

Fuerza la creación de un commit de merge incluso cuando Git podría realizar la integración mediante fast-forward.

--ff-only

Permite realizar el merge únicamente si puede completarse mediante fast-forward. Si no es posible, la operación se cancela.

--squash

Combina todos los cambios de la rama especificada en un único conjunto de cambios, sin conservar los commits originales.

--abort

Cancela un proceso de merge en curso cuando se produjo un conflicto y se desea volver al estado anterior.

Ejemplo de uso
git checkout dev
git merge feature-login

En este ejemplo, los cambios realizados en la rama feature-login se incorporan a la rama dev.

Comandos relacionados
git rebase

Permite integrar cambios de otra rama reorganizando el historial de commits.

git branch

Se utiliza para crear y administrar ramas antes de fusionarlas.

git pull

Puede ejecutar internamente un merge al integrar cambios provenientes de un repositorio remoto.
# git merge

## Descripción

El comando `git merge` sirve para combinar los historiales y cambios de dos 
ramas diferentes en una sola. Es la herramienta estándar de Git para integrar 
el trabajo realizado en una rama de desarrollo, como una nueva funcionalidad, 
con la rama principal del proyecto.

Cuando se ejecuta, Git toma los cambios de la rama indicada y los fusiona 
con la rama en la que te encontrás actualmente.

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
git merge <nombre-de-la-rama>
```

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
  Fuerza la creación de un merge commit aunque sea posible hacer 
  fast-forward. Es útil para mantener un historial más claro.

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
