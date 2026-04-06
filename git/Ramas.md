Son apuntadores móviles a confirmaciones (commits) específicos.

### ¿Por qué utilizarlas?

- Trabajar de forma segura y organizada
- Aislar cambios de *main*
- Experimentar sin comprometer el código principal
- Trabajar en diferentes funcionalidades simultáneamente
- Facilita el trabajo en equipo

## Crear ramas

Crea un nuevo flujo de trabajo a partir de la rama en la que se encuentra:

- `git switch -c <rama>`

Elimina la rama, no debo estar en ese flujo de trabajo para borrarla:

- `git branch -D <rama>`

**¿Cada cuándo se crean ramas**
	Cuando se realice un cambio de código, como lo es para agregar, arreglar, eliminar o modificar.
### Nombramiento de ramas

- Debe ser descriptivo
- Permite identificar tickets/issues/tareas asociadas
- Seguir el estándar definido por el equipo

## Navegar entre ramas

Cambia el área de trabajo a otra rama:

- `git switch <rama>`

## Unir ramas

Ideal para agregar features, fixes, etc., que están en una rama a la rama en la que se encuentra:

- `git merge <rama-a-agregar>`

## Estrategias de merge

- **Fast-forward merge** (default por git)
	Ocurre cuando la rama de los nuevos cambios está actualizada con la última versión de la rama main, y solo cambia el apuntador del *HEAD* del último cambio.

- **Merge commit**
	Ocurre cuando la rama de los nuevos cambios no está actualizada con main. Agrega un commit con todos los cambios nuevos.

- **Squash merge**
	Combinación de las dos estrategias anteriores.
	
	Nuevo commit con todos los cambios de la rama a fusionar y probablemente el apuntador de la rama padre se mueve hacia ese commit.

	`git merge <rama-a-fusionar> --squash`

**¿Qué estrategia usar?**
	Depende del flujo de trabajo :)
