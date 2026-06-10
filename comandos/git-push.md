# **6. git push**

## Descripción

El comando `git push` se utiliza para subir tus commits locales a un repositorio remoto como GitHub, GitLab o Bitbucket. En pocas palabras, sincroniza tu historial de trabajo local con el repositorio remoto para que tus cambios queden respaldados y accesibles para otros colaboradores.

Cuando realizás cambios y los guardás con `git commit`, estos existen solo en tu máquina. Al ejecutar `git push`, Git compara lo que tenés en tu rama local con la rama correspondiente en el servidor y envía los commits que faltan actualizando la rama remota.

## Sintaxis y parámetros

La manera más comun de "empujar" cambios a un repositorio remoto es con:

```
git push [<opción>] <remoto> <rama>
```

El parámetro `<remoto>` se refiere al repositorio remoto al cual se van a "empujar" los cambios, generalmente se utiliza `origin`, haciendo referencia al repositorio remoto de origen establecido previamente con el comando `git clone <url>`.

El parámetro `<rama>` se refiere a la rama del repositorio local de la cual se van a "empujar" los cambios para actualizar el repositorio remoto.

De esta forma, si se está trabajando en la rama `personal` y se desea mandar cambios realizados, primero debe realizarse un commit guardando todos los cambios de manera local, y luego mandar los commits de la rama `personal` local a la rama `personal` remota con `git push origin personal`, aquellos archivos nuevos o modificados que contengan los commits enviados, serán ahora visibles en el repositorio remoto.

Si es la primera vez que se envían cambios del repositorio local al repositorio remoto, es muy probable que al intentar enviar los cambios de esta manera salte un error indicando que no existe una rama con el nombre de la rama local en el repositorio remoto, por lo será necesario crear la rama en el repositorio remoto. Por eso, la primera vez es importante incluir el parámetro `-u`/`--set-upstream` para que se rastree la rama local en el remoto: `git push -u origin personal`

El parámetro `[<opción>]` permite modificar el comportamiento del comando insertando una opción válida. Las más comunes y utilizadas son:

- `-u` / `--set-upstream`  
  Establece la rama remota como upstream de la rama local. Solo se
  necesita la primera vez que se sube una rama nueva.

- `--force` / `-f`  
  Fuerza la subida aunque haya conflictos con el historial remoto.
  Hay que usarlo con cuidado ya que puede sobreescribir el trabajo
  de otros.

- `--force-with-lease`  
  Similar a `--force` pero más seguro, ya que verifica que nadie más
  haya subido cambios antes de forzar.

- `--tags`  
  Sube también las etiquetas (tags) locales al remoto.

- `--delete`  
  Elimina una rama en el repositorio remoto.

## Usos más comunes

**Subir una rama por primera vez:**

```
git push -u origin <nombre-de-la-rama>
```

**Subir cambios en una rama ya configurada:**

```
git push
```

**Eliminar una rama remota:**

```
git push origin --delete <nombre-de-la-rama>
```

## Errores comunes

Una de las limitantes más comunes a la hora de enviar cambios al repositorio remoto, es que Git no permite hacerlo si detecta que la rama que se intenta actualizar está **adelantado en el tiempo** en cuanto a commits, es decir, que el repositorio local no está al día con los últimos cambios realizados, posiblemente porque otro desarrollador llevó cambios a esa rama.

Lo más recomendable es buscar cambios hechos en el repositorio remoto ejecutando el comando `git fetch`, y en caso de haber cambios en la rama, traerlos con `git pull`, comando que se desarrollará en su propio documento.

También se puede forzar la actualización con el parámetro `-f` mencionado más arriba, con la debida precaución de no sobreescribir cambios importantes hechos.

## Comandos similares

- `git pull` — operación inversa, trae los cambios del remoto al local.
- `git commit` — paso previo necesario antes de hacer un push.
- `git fetch` — descarga información del remoto sin fusionar cambios.

