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