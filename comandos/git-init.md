# git init

## Descripción

El comando `git init` crea un nuevo repositorio de Git. Convierte cualquier 
directorio o proyecto existente en un entorno con control de versiones, 
creando una carpeta oculta llamada `.git` que almacena todo el historial de 
cambios, metadatos y configuraciones necesarias para que Git funcione.

## Sintaxis

```
git init [<directorio>]
```

Si se ejecuta sin argumentos, inicializa el repositorio en la carpeta actual. 
Si se le pasa un directorio, Git crea esa carpeta y la inicializa como 
repositorio directamente.

## Parámetros principales

- `--bare`  
  Crea un repositorio sin directorio de trabajo. Se usa principalmente en 
  servidores remotos donde no se necesita editar archivos directamente.

- `-b <nombre>` / `--initial-branch=<nombre>`  
  Permite elegir el nombre de la rama inicial en lugar de usar el 
  predeterminado (`main` o `master`).

## Ejemplo de uso

```
cd mi-proyecto
git init
```

Después de esto, la carpeta `mi-proyecto` ya tiene control de versiones y 
Git va a empezar a rastrear cualquier cambio que hagamos adentro.

## Comandos relacionados

- `git clone` — en lugar de crear un repo vacío, clona uno que ya existe.