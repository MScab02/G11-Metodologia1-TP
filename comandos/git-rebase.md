# git rebase

## Descripción

El comando `git rebase` toma los commits de tu rama actual y los reaplica 
sobre el último commit de otra rama, creando un historial lineal. A 
diferencia de `git merge`, no crea un commit de fusión sino que reescribe 
el historial haciendo que parezca que desarrollaste tus cambios justo al 
final de la otra rama.

Esto es útil para mantener el historial de commits ordenado y fácil de leer, 
especialmente en proyectos colaborativos donde un historial limpio hace más 
fácil entender qué cambió y por qué.

## ¿Para qué sirve?

- **Historial limpio:** Mantiene el registro de commits en una línea recta, 
  sin ramificaciones ni commits de fusión innecesarios.
- **Evitar commits de fusión:** Muy usado para actualizar tu rama de trabajo 
  con los últimos cambios de `main` sin añadir ruido al historial.

## Sintaxis

```
git rebase [<parámetros>] <rama-base>
```

## Usos más comunes

**Reaplicar los commits de tu rama sobre otra:**
```
git rebase main
```
Esto toma todos los commits de tu rama actual y los reaplica sobre el 
último commit de `main`.

**Rebase interactivo:**
```
git rebase -i <rama-base>
```
Permite editar, reordenar, combinar o eliminar commits antes de reaplicarlos. 
Es muy útil para limpiar el historial antes de hacer un merge.

**Abortar un rebase en curso:**
```
git rebase --abort
```

**Continuar un rebase después de resolver un conflicto:**
```
git rebase --continue
```

## Parámetros principales

- `-i` / `--interactive`  
  Abre un editor para modificar los commits antes de reaplicarlos.

- `--abort`  
  Cancela el rebase y vuelve al estado anterior.

- `--continue`  
  Continúa el rebase luego de resolver un conflicto manualmente.

- `--skip`  
  Omite el commit actual y continúa con el siguiente.

## Diferencia con git merge

| | `git merge` | `git rebase` |
|---|---|---|
| Historial | Conserva todas las ramas | Lineal y limpio |
| Commit extra | Crea un merge commit | No crea commits extra |
| Reescribe historial | No | Sí |

## Ejemplo de uso

```
git checkout mi-rama
git rebase main
```

Esto reaplica los commits de `mi-rama` sobre el último commit de `main`, 
como si los hubieras desarrollado desde ahí.

## Comandos relacionados

- `git merge` — alternativa para integrar ramas conservando el historial 
  completo.
- `git cherry-pick` — permite traer commits específicos de otra rama sin 
  hacer un rebase completo.