Se declaran con `fn`.

Utilizan la convención [[snake case]].

Las funciones se pueden declarar antes o después de donde se llaman, es decir, a Rust solo le interesa que estén definidas en el ámbito que pueda ser visto por el invocador.

### Parámetros

Variables especiales que forman parte de la firma de una función.

Se le pueden colocar valores concretos a esas variables (argumentos).

```rust
fn main() {
    another_function(5);
}

fn another_function(x: i32) {
    println!("The value of x is: {x}");
}
```

Se debe declarar el tipo de cada parámetro, lo que hace que el compilador nunca necesita que se usen en otro lugar del código para averiguar a qué tipo se refiere.

### Sentencias y expresiones

**Sentencias** -> instrucciones que realizan alguna acción y no devuelven un valor

**Expresiones** -> evalúan a un valor resultante

>[!NOTE]
>Otros lenguajes no tienen distinciones con lo anterior.

Definir una función es una sentencia pero ejecutarla es una expresión.

Un ámbito creado con llaves es una expresión.

Las expresiones no llevan `;` al final.

Una sentencia al no evaluar nada, se expresan por `()`, el tipo *unitario*.

### Funciones con valores de retorno

Solo se especifica el tipo de valor de retorno después de `->`.

```rust
fn five() -> i32 {
    5
}
```
