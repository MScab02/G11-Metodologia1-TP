# Conflictos en Git

## Descripción

Un conflicto en Git (o merge conflict) ocurre cuando intentás unir dos ramas
o actualizar tu código y Git encuentra modificaciones contradictorias en las
mismas líneas de un archivo. Como no puede decidir qué versión es la correcta,
pausa el proceso y te pide que elijas manualmente qué cambios conservar.

Los conflictos no son un error del programa, sino una medida de seguridad
para evitar que Git sobreescriba trabajo sin tu consentimiento.

## ¿Por qué ocurren?

Suceden principalmente en dos situaciones:

- **Al unir ramas:** Cuando intentás hacer `git merge` entre dos ramas que
  modificaron exactamente la misma porción de código.
- **Al actualizar el repositorio:** Al hacer `git pull` y descargar cambios
  que modificaron la misma línea en la que estabas trabajando localmente.

## ¿Cómo se ve un conflicto?

Cuando Git detecta un conflicto, marca el archivo afectado con la siguiente
estructura:

<<<<<<< HEAD
Este es el contenido de tu rama actual.
=======
Este es el contenido de la rama que estás fusionando.

> > > > > > > nombre-de-la-otra-rama

- Todo lo que está entre `<<<<<<< HEAD` y `=======` son tus cambios locales.
- Todo lo que está entre `=======` y `>>>>>>>` son los cambios de la otra rama.

## ¿Cómo resolverlo?

**Paso 1 — Identificar los archivos con conflictos:**

```

git status

```

Los archivos en conflicto aparecen marcados como `both modified`.

**Paso 2 — Abrir el archivo y elegir qué conservar:**
Editá el archivo manualmente, eliminando las marcas de conflicto y dejando
solo el contenido correcto. Podés quedarte con tus cambios, con los de la
otra rama, o combinar ambos.

**Paso 3 — Marcar el conflicto como resuelto:**

```

git add <archivo-resuelto>

```

**Paso 4 — Continuar el merge:**

```

git commit

```

## Cancelar el proceso

Si preferís abortar el merge y volver al estado anterior:

```

git merge --abort

```

## Buenas prácticas para evitar conflictos

- Hacer `git pull` frecuentemente para mantenerse actualizado.
- Trabajar en ramas separadas para cada funcionalidad.
- Comunicarse con el equipo sobre qué archivos está modificando cada uno.
- Hacer commits pequeños y frecuentes en lugar de acumular muchos cambios.

## Comandos relacionados

- `git merge` — comando que puede generar conflictos al fusionar ramas.
- `git pull` — puede generar conflictos al traer cambios del remoto.
- `git status` — para identificar qué archivos tienen conflictos.
- `git merge --abort` — para cancelar el proceso si es necesario.

```

```
