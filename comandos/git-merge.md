git merge
Descripción

El comando git merge se utiliza para fusionar los cambios de una rama con otra. Su función principal es integrar el trabajo realizado en distintas líneas de desarrollo dentro de un mismo historial de proyecto.

Cuando se ejecuta, Git compara los historiales de ambas ramas e intenta combinar automáticamente los cambios. Si los archivos modificados no presentan incompatibilidades, la fusión se realiza de forma automática. En cambio, si dos ramas modificaron las mismas líneas de un archivo, se producirá un conflicto que deberá resolverse manualmente.

Es común utilizar este comando cuando una funcionalidad desarrollada en una rama secundaria está lista para incorporarse a una rama principal o de desarrollo.

Sintaxis
git merge <rama>

Donde <rama> corresponde a la rama cuyos cambios se desean incorporar a la rama actual.

Usos más comunes
Fusionar una rama con la rama actual
git merge feature-login

Incorpora los cambios de la rama feature-login a la rama en la que el usuario se encuentra actualmente.

Fusionar cambios descargados del repositorio remoto
git merge origin/main

Integra en la rama actual los cambios obtenidos desde la rama remota main.

Finalizar el desarrollo de una funcionalidad
git checkout dev
git merge feature-git-merge

Permite incorporar a la rama dev el trabajo realizado previamente en una rama de funcionalidad.

Parámetros principales
--no-ff

Fuerza la creación de un commit de merge incluso cuando Git podría realizar la integración mediante fast-forward.

--ff-only

Permite realizar el merge únicamente si puede completarse mediante fast-forward. Si no es posible, la operación se cancela.

--squash

Combina todos los cambios de la rama especificada en un único conjunto de cambios, sin conservar los commits originales.

--abort

Cancela un proceso de merge en curso cuando se produjo un conflicto y se desea volver al estado anterior.

Ejemplo de uso
git checkout dev
git merge feature-login

En este ejemplo, los cambios realizados en la rama feature-login se incorporan a la rama dev.

Comandos relacionados
git rebase

Permite integrar cambios de otra rama reorganizando el historial de commits.

git branch

Se utiliza para crear y administrar ramas antes de fusionarlas.

git pull

Puede ejecutar internamente un merge al integrar cambios provenientes de un repositorio remoto.