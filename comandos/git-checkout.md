git checkout
Descripción

El comando git checkout permite cambiar entre distintas ramas del repositorio o restaurar archivos a una versión determinada. Es uno de los comandos más utilizados en Git, ya que facilita moverse entre diferentes líneas de desarrollo sin afectar el historial del proyecto.

Cuando se utiliza para cambiar de rama, Git actualiza el directorio de trabajo para que refleje el contenido de la rama seleccionada. De esta manera, cada rama puede contener versiones distintas del proyecto y el usuario puede alternar entre ellas según la tarea que esté realizando.

También puede utilizarse para recuperar archivos desde un commit específico o descartar cambios locales que todavía no fueron confirmados mediante un commit.

Sintaxis
git checkout [<parámetros>] <destino>

Donde <destino> puede ser el nombre de una rama, un commit o un archivo.

Usos más comunes
Cambiar a una rama existente
git checkout <nombre-rama>

Permite cambiar la rama actual por otra ya existente.

Crear una rama y cambiarse a ella
git checkout -b <nombre-rama>

Crea una nueva rama a partir de la actual y automáticamente cambia a ella.

Restaurar un archivo
git checkout -- <archivo>

Descarta los cambios locales realizados sobre un archivo y recupera la última versión confirmada en el repositorio.

Recuperar un archivo desde un commit específico
git checkout <hash-commit> -- <archivo>

Restaura una versión específica del archivo utilizando un commit determinado.

Parámetros principales
-b

Crea una nueva rama y cambia automáticamente a ella.

-B

Crea una rama nueva o la reinicia si ya existe, posicionándose en ella inmediatamente.

--

Se utiliza para separar el nombre de una rama de una ruta de archivo, evitando ambigüedades.

--detach

Permite posicionarse directamente sobre un commit sin estar asociado a ninguna rama.

Ejemplo de uso
git checkout desarrollo

Git cambia la rama actual por la rama llamada desarrollo, actualizando el directorio de trabajo para reflejar su contenido.

Comandos relacionados
git switch

Comando más moderno utilizado específicamente para cambiar entre ramas.

git branch

Permite crear, listar, eliminar o renombrar ramas.

git restore

Se utiliza para restaurar archivos y reemplaza parte de las funciones históricas de git checkout.