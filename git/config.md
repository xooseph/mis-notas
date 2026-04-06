Configura un repositorio u opciones globales.

- `git config --global core.editor "code --wait"`
		Para abrir con un editor de texto específico (**code, zed, etc.**)
		**wait** -> la terminal espera a cerrar el editor

- `git config --global -e`
		Ve el archivo de configuración global

Depende del sistema que se está utilizando, cada que se agrega un saltó de línea, Windows agrega dos carácteres especiales **(Carriage Return) CR** y **(Line Feed) LF**, mientras que en Linux o Mac solo añade LF, para evitar conflicto, colocar `true` o `input` respectivamente:

- `git config --global core.autocrlf input`

- `git config --list`
		Lista configuración, también se puede buscar por un elemento en específico: 
			- `git config user.name`

## Llave SSH

Llave compartida entre la compu y GitHub que permite conectarse con el protocolo SSH.

- No se necesita validación extra
- Autorización para intercambiar info

> [!NOTE]
Es mejor autenticarse con **Personal Access Tokens** si se está utilizando una compu que no es personal.

![[Pasted image 20260405165044.png]]

Inicializo el agente de *ssh* (gestiona colecciones de llaves ssh):

- `eval "$(ssh-agent -s)"`

Agrego la llave:

- `ssh-add <ruta-de-la-llave>`

#### Conectar la llave a la cuenta de GitHub

Copio la llave:

- `cat <ruta-de-la-llave.pub>`

En GitHub coloco la llave:

![[Pasted image 20260405203059.png]]

Por último verifico la conexión:

- `ssh -T git@github.com`