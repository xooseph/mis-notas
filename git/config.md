Configura un repositorio u opciones globales.

- `git config --global core.editor "code --wait"`
		Para abrir con un editor de texto específico (**code, zed, etc.**)
		**wait** -> la terminal espera a cerrar el editor

- `git config --global -e`
		Ve el archivo de configuración global

Depende del sistema que se está utilizando, cada que se agrega un saltó de línea, Windows agrega dos carácteres especiales **(Carriage Return) CR** y **(Line Feed) LF**, mientras que en Linux o Mac solo añade LF, para evitar conflicto, colocar `true` o `input` respectivamente:

- `git config --global core.autocrlf input`