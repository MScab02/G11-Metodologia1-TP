# git branch

## Descripción

El comando `git branch` sirve para administrar las ramas del repositorio.
Una rama es una línea de desarrollo independiente, lo que permite trabajar 
en nuevas funcionalidades o hacer pruebas sin afectar el código principal.

Con este comando podés listar las ramas existentes, crear nuevas, 
eliminarlas o cambiarles el nombre.

## Sintaxis

```
git branch [<parámetros>] [<nombre>]
```

## Usos más comunes

**Listar ramas locales:**
```
git branch
```
Muestra todas las ramas locales. La que tiene un asterisco (`*`) es en la 
que te encontrás actualmente.

**Crear una rama nueva:**
```
git branch <nombre-de-la-rama>
```
Crea un nuevo puntero al commit actual, pero no cambia a esa rama 
automáticamente.

**Eliminar una rama:**
```
git branch -d <nombre-de-la-rama>
```
Borra la rama de forma segura, solo si sus cambios ya fueron integrados. 
Para forzar la eliminación sin importar eso, se usa `-D` en mayúscula.

**Renombrar una rama:**
```
git branch -m <nombre-actual> <nombre-nuevo>
```

## Parámetros principales

- `-a` / `--all`  
  Lista tanto las ramas locales como las remotas.

- `-r` / `--remotes`  
  Lista solo las ramas remotas.

- `-v` / `--verbose`  
  Muestra el último commit de cada rama junto a su nombre.

- `-m` / `--move`  
  Renombra una rama.

- `-d` / `--delete`  
  Elimina una rama de forma segura.

- `-D`  
  Fuerza la eliminación de una rama aunque no haya sido mergeada.

## Comandos relacionados

- `git checkout` / `git switch` — para cambiar a una rama existente.
- `git merge` — para fusionar los cambios de una rama con otra.