git rebase
Descripción

El comando git rebase permite integrar cambios de una rama en otra reescribiendo el historial de commits. En lugar de crear un commit de fusión como hace git merge, toma los commits de una rama y los reaplica sobre la rama de destino, generando un historial más lineal y fácil de seguir.

Su principal ventaja es que evita la creación de commits de merge innecesarios, haciendo que el historial del proyecto sea más limpio. Sin embargo, al modificar el historial de commits, debe utilizarse con cuidado, especialmente en ramas compartidas con otros desarrolladores.

Durante el proceso de rebase pueden producirse conflictos, los cuales deben resolverse manualmente antes de continuar con la operación.

Sintaxis
git rebase <rama>

Donde <rama> corresponde a la rama cuyos cambios se utilizarán como nueva base para los commits de la rama actual.

Usos más comunes
Actualizar una rama con cambios de otra
git rebase main

Toma los commits de la rama actual y los reaplica sobre la versión más reciente de la rama main.

Actualizar una rama de funcionalidad
git checkout feature-login
git rebase dev

Permite que la rama feature-login incorpore los cambios más recientes de dev antes de integrarse nuevamente.

Reorganizar commits
git rebase -i HEAD~3

Inicia un rebase interactivo sobre los últimos tres commits, permitiendo editarlos, combinarlos o reordenarlos.

Parámetros principales
-i / --interactive

Permite editar, combinar, eliminar o reorganizar commits de forma interactiva.

--continue

Continúa el proceso de rebase después de resolver un conflicto.

--abort

Cancela el rebase y devuelve el repositorio al estado previo al inicio de la operación.

--skip

Omite el commit actual que está generando conflictos y continúa con el resto del proceso.

Ejemplo de uso
git checkout feature-login
git rebase dev

En este ejemplo, los commits de la rama feature-login son reaplicados sobre la versión más reciente de la rama dev, manteniendo un historial lineal.

Comandos relacionados
git merge

Integra cambios entre ramas mediante un commit de fusión, sin reescribir el historial.

git pull --rebase

Obtiene cambios del repositorio remoto y los integra utilizando rebase en lugar de merge.

git log

Permite visualizar el historial de commits y observar los cambios producidos por un rebase.