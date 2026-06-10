# git revert

## Descripción

El comando `git revert` deshace los cambios de un commit específico creando 
un commit nuevo, en lugar de borrarlo del historial. Es la herramienta ideal 
para corregir errores de forma segura en repositorios compartidos, ya que no 
altera ni reescribe los commits anteriores.

## ¿Cómo funciona?

Cuando ejecutás `git revert <hash-del-commit>`, Git analiza qué se modificó 
en ese commit y genera automáticamente un nuevo commit con la acción contraria. 
Por ejemplo, si el commit original agregó 3 líneas de código, el revert las 
elimina. Si eliminó un archivo, el revert lo restaura.

Esto lo hace especialmente útil en ramas compartidas donde reescribir el 
historial con `git reset` podría causar problemas a otros colaboradores.

## Sintaxis

```
git revert [<parámetros>] <hash-del-commit>
```

## Usos más comunes

**Revertir el último commit:**
```
git revert HEAD
```

**Revertir un commit específico:**
```
git revert <hash-del-commit>
```

**Revertir sin abrir el editor de mensaje:**
```
git revert --no-edit <hash-del-commit>
```

**Revertir sin crear el commit automáticamente:**
```
git revert --no-commit <hash-del-commit>
```
Útil cuando querés revertir varios commits y agruparlos en un solo commit 
al final.

## Parámetros principales

- `--no-edit`  
  Usa el mensaje de commit generado automáticamente sin abrir el editor.

- `--no-commit` / `-n`  
  Aplica los cambios inversos al staging area sin crear el commit, 
  permitiendo revisarlos antes.

- `--abort`  
  Cancela un revert en curso si hubo conflictos.

- `--continue`  
  Continúa el revert luego de resolver un conflicto manualmente.

## Diferencia con git reset

| | `git revert` | `git reset` |
|---|---|---|
| Reescribe historial | No | Sí |
| Crea commit nuevo | Sí | No |
| Seguro en ramas compartidas | ✅ Sí | ⚠️ No recomendado |

## Ejemplo de uso

```
git log --oneline
```
```
a1b2c3d feat: agregar validación al login
e4f5g6h feat: crear pantalla de inicio
```
```
git revert a1b2c3d
```
Esto crea un nuevo commit que deshace los cambios introducidos en `a1b2c3d`.

## Comandos relacionados

- `git reset` — deshace commits reescribiendo el historial, más adecuado 
  para uso local.
- `git log` — para ver el historial y obtener el hash del commit a revertir.