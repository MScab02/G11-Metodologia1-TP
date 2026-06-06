git pull
Descripción

El comando git pull se utiliza para obtener los cambios más recientes desde un repositorio remoto e integrarlos automáticamente en la rama local actual. Es uno de los comandos más utilizados en el trabajo colaborativo, ya que permite mantener actualizado el repositorio local con los cambios realizados por otros integrantes del equipo.

Internamente, git pull realiza dos operaciones consecutivas:

Ejecuta un git fetch, descargando la información más reciente del repositorio remoto.
Ejecuta un git merge, integrando esos cambios en la rama local actual.

Si los cambios remotos y locales afectan las mismas líneas de un archivo, pueden producirse conflictos que deberán resolverse manualmente antes de completar la operación.

Sintaxis
git pull [<repositorio>] [<rama>]

Donde:

<repositorio> suele ser el repositorio remoto llamado origin.
<rama> corresponde a la rama desde la cual se desean obtener los cambios.
Usos más comunes
Actualizar la rama actual
git pull

Obtiene e integra los cambios de la rama remota asociada a la rama local actual.

Obtener cambios de una rama específica
git pull origin main

Descarga e integra los cambios de la rama main del repositorio remoto origin.

Actualizar una rama de desarrollo
git pull origin dev

Permite sincronizar la rama local con la versión más reciente de la rama dev almacenada en el repositorio remoto.

Parámetros principales
--rebase

Integra los cambios utilizando un rebase en lugar de un merge, manteniendo un historial más lineal.

--ff-only

Realiza la operación únicamente si puede completarse mediante un fast-forward. Si se requiere un merge, la operación se cancela.

--no-commit

Realiza el merge de los cambios descargados pero evita crear automáticamente el commit de integración.

--all

Obtiene información de todos los repositorios remotos configurados.

Ejemplo de uso
git pull origin dev

Este comando descarga los cambios más recientes de la rama dev del repositorio remoto origin y los integra en la rama local actual.

Comandos relacionados
git fetch

Descarga la información más reciente del repositorio remoto sin integrarla automáticamente.

git merge

Permite fusionar cambios provenientes de otra rama o historial.

git push

Envía los commits locales al repositorio remoto.