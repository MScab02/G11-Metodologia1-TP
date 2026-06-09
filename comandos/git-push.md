# **6. git push**

## Descripción

El comando `git push...` funciona con repositorios remotos de los proyectos asociados. Actualiza una o más ramas del repositorio remoto con el contenido del repositorio local que no se encuentre ya en el repositorio remoto.

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

- `-u` `--set-upstream`

  Explicado anteriormente, rastrea la rama local en el repositorio remoto, de forma que en el futuro poder empujar y traer cambios del repositorio remoto sin parámetros adicionales.

- `-f` `--force`

  Permite forzar la actualización de una rama remota, saltandose los errores que puedan estar impidiendo que los cambios se empujen.

  Esta acción puede borrar commits del repositorio remoto, asique debe usarse con cuidado.

## Errores comunes

Una de las limitantes más a la hora de enviar cambios al repositorio remoto, es que Git no permite hacerlo si detecta que la rama que se intenta actualizar está **adelantado en el tiempo** en cuanto a commits, es decir, que el repositorio local no está al día con los últimos cambios realizados, posiblemente porque otro desarrollador llevó cambios a esa rama.

Lo más recomendable es buscar cambios hechos en el repositorio remoto ejecutando el comando `git fetch`, y en caso de haber cambios en la rama, traerlos con `git pull`, comando que se desarrollará en su propio documento.

También se puede forzar la actualización con el parámetro `-f` mencionado más arriba, con la debida precaución de no sobreescribir cambios importantes hechos.

## Comandos similares

En Git, no existen comandos que realicen la misma acción que `git push`, pero vale mencionar a `git pull`, el cual vendría siendo su "antónimo".

`git pull`, a la inversa de `git push`, sirve para comunicarse con el repositorio remoto y traer los cambios de una rama de elección al repositorio local del usuario, de esta forma, se pueden actualizar los archivos locales con las últimas modificaciones realizadas, sumamente importante para conocer qué han hecho nuestros compañeros y poder trabajar mejor organizado.
