Agrega cambios al área de staging.

Utilizar `.`  como argumento es mala práctica.

Agrega los cambios de todos los archivos con cierta terminación:

	- `git add *.js`

Agrega los archivos con cambios en el proyecto:

	- `git add -A`

Añade solo archivos modificados o eliminados, los creados no:

	- `git add -u`

Si se van a añadir varios archivos se separan con un espacio en blanco.

No se pasan los archivos, solo las modificaciones que se hicieron en ellos.

Si hay archivos o directorios que deben ser ignorados del flujo de trabajo de Git, estos deben ser agregados en el archivo `.gitignore`.

Devuelve los cambios en archivos a la zona de trabajo:

	- `git reset`