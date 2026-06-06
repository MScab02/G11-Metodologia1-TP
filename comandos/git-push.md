git push
Descripción

El comando git push se utiliza para enviar los commits realizados en un repositorio local hacia un repositorio remoto. De esta forma, los cambios realizados por un desarrollador pueden compartirse con otros integrantes del equipo o almacenarse de manera segura en plataformas como GitHub o GitLab.

Cuando se ejecuta este comando, Git compara el historial local con el remoto y transfiere únicamente los commits que todavía no existen en el servidor. Esto permite mantener sincronizados ambos repositorios.

Es habitual utilizar este comando después de realizar uno o más commits, ya que los commits permanecen únicamente en la computadora local hasta que son enviados al repositorio remoto mediante git push.

Sintaxis
git push [<repositorio>] [<rama>]

Donde:

<repositorio> suele ser el nombre del repositorio remoto, normalmente origin.
<rama> corresponde a la rama cuyos cambios se desean enviar.
Usos más comunes
Enviar una rama al repositorio remoto
git push origin main

Envía los commits de la rama main al repositorio remoto llamado origin.

Publicar una rama nueva
git push -u origin feature/nueva-funcionalidad

Además de enviar la rama, establece una relación de seguimiento entre la rama local y la remota.

Actualizar una rama remota
git push

Si la rama ya tiene configurado un repositorio remoto asociado, Git envía automáticamente los cambios pendientes.

Parámetros principales
-u / --set-upstream

Establece una relación de seguimiento entre la rama local y la remota, permitiendo utilizar simplemente git push y git pull en el futuro.

--force

Fuerza la actualización de la rama remota incluso si esto implica sobrescribir cambios existentes. Debe utilizarse con precaución.

--force-with-lease

Similar a --force, pero verifica previamente que nadie haya realizado cambios en el repositorio remoto, ofreciendo una alternativa más segura.

--tags

Envía también las etiquetas (tags) locales al repositorio remoto.

Ejemplo de uso
git push origin dev

Este comando envía todos los commits pendientes de la rama dev al repositorio remoto llamado origin.

Comandos relacionados
git pull

Obtiene cambios desde el repositorio remoto y los integra en la rama actual.

git fetch

Descarga información del repositorio remoto sin integrarla automáticamente.

git commit

Guarda cambios en el repositorio local antes de enviarlos al repositorio remoto.