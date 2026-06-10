# git pull

## Descripción

El comando `git pull` se utiliza para descargar las últimas actualizaciones 
desde un repositorio remoto, como GitHub o GitLab, e integrarlas de forma 
automática en tu rama de trabajo actual.

En la práctica, `git pull` es la combinación de dos acciones ejecutadas 
en secuencia:

1. `git fetch` — descarga los nuevos cambios desde el servidor remoto.
2. `git merge` — fusiona esos cambios en tu rama local, actualizando 
   tu código inmediatamente.

## Sintaxis

```
git pull [<parámetros>] [<remoto>] [<rama>]
```

## ¿Cuándo usarlo?

- **Antes de empezar a trabajar:** Es una buena práctica asegurarse de 
  tener la versión más reciente del proyecto antes de realizar nuevos 
  cambios.
- **Antes de hacer un push:** Si intentás subir tus cambios con `git push` 
  y te da error, generalmente significa que alguien más subió modificaciones 
  antes. En ese caso hay que hacer un `git pull` primero para actualizar 
  el código local.

## Parámetros principales

- `--rebase`  
  En lugar de hacer un merge al traer los cambios, hace un rebase. 
  Útil para mantener un historial más limpio.

- `--no-commit`  
  Descarga y fusiona los cambios pero no crea el commit automáticamente, 
  permitiendo revisarlos antes.

- `--ff-only`  
  Solo permite el pull si se puede hacer fast-forward, sin crear un 
  merge commit.

- `-v` / `--verbose`  
  Muestra información detallada sobre lo que se está descargando.

## Ejemplo de uso

```
git pull origin main
```

Esto descarga los últimos cambios de la rama `main` del repositorio 
remoto `origin` y los fusiona con tu rama local actual.

## Comandos relacionados

- `git fetch` — descarga los cambios del remoto pero sin fusionarlos 
  automáticamente.
- `git push` — operación inversa, sube tus cambios locales al remoto.
- `git merge` — parte de lo que hace `git pull` internamente.