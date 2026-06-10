# git status

## Descripción

El comando `git status` muestra el estado actual del directorio de trabajo 
y del área de preparación (staging area). Es un comando de solo lectura, 
lo que significa que no modifica nada, simplemente te permite ver en qué 
situación están tus archivos en un momento dado.

Con este comando podés saber tres cosas principales:

- Qué archivos tienen cambios listos para el próximo commit (están en el 
  staging area).
- Qué archivos fueron modificados pero todavía no fueron agregados al 
  staging area.
- Qué archivos nuevos no están siendo rastreados por Git todavía.

Es uno de los comandos más usados en el día a día, ya que antes de hacer 
un `git add` o un `git commit` conviene ejecutarlo para tener claro qué 
está pasando en el repositorio.

## Sintaxis

```
git status [<parámetros>]
```

## Parámetros principales

- `-s` / `--short`  
  Muestra la información de forma resumida, más compacta y fácil de leer 
  cuando hay muchos archivos.

- `-b` / `--branch`  
  Muestra también la rama actual y su relación con la rama remota.

- `-u` / `--untracked-files`  
  Controla cómo se muestran los archivos no rastreados. Puede ser `no`, 
  `normal` o `all`.

## Ejemplo de uso

```
git status
```

La salida típica te muestra algo así:

```
On branch main
Changes to be committed:
  modified: archivo1.txt

Changes not staged for commit:
  modified: archivo2.txt

Untracked files:
  archivo3.txt
```

## Comandos relacionados

- `git add` — una vez que viste el estado, se usa para mover archivos al 
  staging area.
- `git log` — muestra el historial de commits en lugar del estado actual.