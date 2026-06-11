# git pull

## Descripción

El comando `git pull` se utiliza para obtener los cambios más recientes desde un repositorio remoto, como GitHub o GitLab, e integrarlas de forma automática en tu rama de trabajo actual.
Es uno de los comandos más utilizados en el trabajo colaborativo, ya que permite mantener actualizado el repositorio local con los cambios realizados por otros integrantes del equipo.

En la práctica, `git pull` es la combinación de dos acciones ejecutadas
en secuencia:

1. Ejecuta un git fetch, descargando la información más reciente del repositorio remoto.
2. Ejecuta un git merge, integrando esos cambios en la rama local actual.

## Sintaxis

```
git pull [<parámetros>] [<remoto>] [<rama>]
```

`<remoto>` suele ser el repositorio remoto llamado origin.
`<rama>` corresponde a la rama desde la cual se desean obtener los cambios.

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

- `--all`

  Obtiene información de todos los repositorios remotos configurados.

## Usos más comunes

- Actualizar la rama actual

  ```
  git pull
  ```

  Obtiene e integra los cambios de la rama remota asociada a la rama local actual.

- Obtener cambios de una rama específica

  ```
  git pull origin main
  ```

  Descarga e integra los cambios de la rama main del repositorio remoto origin.

- Actualizar una rama de desarrollo

  ```
  git pull origin dev
  ```

  Permite sincronizar la rama local con la versión más reciente de la rama dev almacenada en el repositorio remoto.

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
