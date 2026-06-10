# git clone

## Descripción

El comando `git clone` se utiliza para descargar una copia exacta de un 
proyecto remoto, alojado en plataformas como GitHub o GitLab, directamente 
en tu computadora. No solo descarga los archivos, sino que también trae todo 
el historial de versiones, las ramas y la configuración del proyecto.

Al ejecutar este comando, ocurren tres cosas principales:

- **Descarga completa:** Copia todos los archivos del proyecto junto con su 
  historial de versiones, ramas y configuraciones.
- **Entorno aislado:** Crea un directorio local completamente funcional que 
  actúa de forma independiente del proyecto original en la nube.
- **Conexión automática:** Configura automáticamente un enlace remoto llamado 
  `origin` para que puedas actualizar tu copia local o enviar tus propios 
  cambios más adelante.

## Sintaxis

```
git clone <url> [<directorio>]
```

Si no se especifica un directorio, Git crea una carpeta con el nombre del repositorio automáticamente.

## Parámetros principales

- `--branch <nombre>` / `-b <nombre>`  
  Clona el repositorio pero se posiciona directamente en la rama indicada en lugar de la rama principal.

- `--depth <número>`  
  Hace una clonación superficial, descargando solo los últimos commits indicados. Útil para repos con historial muy largo.

- `--single-branch`  
  Clona únicamente la rama especificada, sin descargar el resto.

## Ejemplo de uso

```
git clone https://github.com/usuario/mi-proyecto.git
```

Esto descarga el repositorio completo en una carpeta llamada `mi-proyecto` dentro del directorio actual.

## Comandos relacionados

- `git init` — en lugar de clonar un repo existente, crea uno nuevo vacío.
- `git pull` — una vez clonado el repo, se usa para traer los cambios nuevos del remoto.