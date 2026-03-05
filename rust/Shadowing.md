Es declarar una nueva variable con el mismo nombre, ocultando la variable anterior, manteniendo su valor hasta que se le haga una vez más *shadowing* o finalice el ámbito en el que se encuentra.

Se puede cambiar el tipo y el valor con *shadowing*.

Para ocultar una variable hay que declararla nuevamente con `let` y su mismo nombre de variable.

Se hacen transformaciones a un valor pero al final la variable tiene que ser inmutable con `let`.

Con *shadowing* creo una nueva variable mientras que con `mut` reutilizo la misma variable y no cambia su tipo.

Con *shadowing* se ahorra en pensar en nombres de variables, p.e.:

![[Pasted image 20260305133605.png]]
