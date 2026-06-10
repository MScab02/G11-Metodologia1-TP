# git reset

## Descripción

El comando `git reset` permite modificar el historial de commits y 
restablecer el estado del proyecto. Su función principal es mover el 
puntero `HEAD` de la rama actual a un commit específico, dándote control 
total para deshacer cambios y reorganizar tu área de trabajo.

## ¿Cómo funciona?

El comando actúa sobre tres componentes principales de Git:

1. **HEAD** — el historial de commits de tu rama.
2. **Índice (Staging Area)** — los archivos preparados para el siguiente 
   commit con `git add`.
3. **Directorio de trabajo** — los archivos reales que ves y editás en 
   tu computadora.

Dependiendo del modificador que uses, `git reset` afectará a uno, dos o 
los tres componentes a la vez.

## Sintaxis

```
git reset [<modo>] [<commit>]
```

## Modos principales

**`--soft`**  
Mueve HEAD al commit indicado pero conserva los cambios en el staging 
area. Es el modo menos destructivo.
```
git reset --soft <hash-del-commit>
```

**`--mixed`** (modo por defecto)  
Mueve HEAD y limpia el staging area, pero conserva los cambios en el 
directorio de trabajo. Los archivos quedan modificados pero sin stagear.
```
git reset --mixed <hash-del-commit>
```

**`--hard`**  
Mueve HEAD, limpia el staging area y descarta todos los cambios del 
directorio de trabajo. Es el modo más destructivo, ya que los cambios 
no se pueden recuperar fácilmente.
```
git reset --hard <hash-del-commit>
```

## Comparación de modos

| Modo | HEAD | Staging Area | Directorio de trabajo |
|---|---|---|---|
| `--soft` | ✅ Mueve | ❌ No toca | ❌ No toca |
| `--mixed` | ✅ Mueve | ✅ Limpia | ❌ No toca |
| `--hard` | ✅ Mueve | ✅ Limpia | ✅ Descarta |

## Ejemplo de uso

```
git reset --soft HEAD~1
```
Deshace el último commit pero mantiene los cambios listos para volver 
a commitear.

## Comandos relacionados

- `git revert` — deshace cambios creando un commit nuevo, sin reescribir 
  el historial. Es más seguro para usar en ramas compartidas.
- `git restore` — restaura archivos del directorio de trabajo sin mover HEAD.