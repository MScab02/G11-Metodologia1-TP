# **2. git commit**

## Descripción

Este comando crea un "commit" con el contenido actual en el "staging area".

Un commit es una captura permanente del estado del proyecto, guardando los archivos deseados con el contenido hasta ese momento. Para cada commit se genera un identificador único (hash) y almacena metadatos importantes, como la fecha y hora en la que se creó, nombre y mail (si el usuario ingresó uno) del autor del commit y una breve descripción del contenido o cambio realizado redactado por el autor. Cada commit se convierte en la nueva cabeza (HEAD) de la rama actual en la que el commit fue creado.

La principal funcionalidad de los commits es como punto de control, resultando útiles tanto como para tener un registro histórico del proyecto con los cambios que se han realizado a través del tiempo y poder utilizarse como documentación, como para reestablecer estos datos anteriores y así volver a un estado anterior del proyecto.

## Sintaxis y parámetros

El comando para realizar commits se escribe de la siguiente manera:

```
git commit [<parámetro>] [--] [<ruta>...]
```
