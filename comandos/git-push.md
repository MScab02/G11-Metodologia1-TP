# git push

## Descripción

El comando `git push` se utiliza para subir tus commits locales a un 
repositorio remoto como GitHub, GitLab o Bitbucket. En pocas palabras, 
sincroniza tu historial de trabajo local con el servidor para que tus 
cambios queden respaldados y accesibles para otros colaboradores.

Cuando realizás cambios y los guardás con `git commit`, estos existen 
solo en tu máquina. Al ejecutar `git push`, Git compara lo que tenés en 
tu rama local con la rama correspondiente en el servidor y envía los 
commits que faltan, actualizando la rama remota.

## Sintaxis

```
git push <nombre-remoto> <nombre-de-la-rama>
```

## Ejemplo de uso

Si estás trabajando en la rama principal y tu repositorio remoto se llama 
`origin` (el nombre por defecto), el comando sería:

```
git push origin main
```

## Usos más comunes

**Subir una rama por primera vez:**
```
git push -u origin <nombre-de-la-rama>
```
El `-u` establece la rama remota como referencia predeterminada, así la 
próxima vez alcanza con escribir solo `git push`.

**Subir cambios en una rama ya configurada:**
```
git push
```

**Eliminar una rama remota:**
```
git push origin --delete <nombre-de-la-rama>
```

## Parámetros principales

- `-u` / `--set-upstream`  
  Establece la rama remota como upstream de la rama local. Solo se 
  necesita la primera vez que se sube una rama nueva.

- `--force` / `-f`  
  Fuerza la subida aunque haya conflictos con el historial remoto. 
  Hay que usarlo con cuidado ya que puede sobreescribir el trabajo 
  de otros.

- `--force-with-lease`  
  Similar a `--force` pero más seguro, ya que verifica que nadie más 
  haya subido cambios antes de forzar.

- `--tags`  
  Sube también las etiquetas (tags) locales al remoto.

- `--delete`  
  Elimina una rama en el repositorio remoto.

## Comandos relacionados

- `git pull` — operación inversa, trae los cambios del remoto al local.
- `git commit` — paso previo necesario antes de hacer un push.
- `git fetch` — descarga información del remoto sin fusionar cambios.