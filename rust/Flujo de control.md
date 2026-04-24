Ejecución de código dependiendo de las condiciones.

### if

```rust
fn main() {
    let number = 3;

    if number < 5 {
        println!("condition was true");
    } else {
        println!("condition was false");
    }
}
```

Los bloques de cada expresión `if` se le llaman *brazos*.

Las condiciones tienen que ser de tipo `bool`.

>[!NOTE]
>Rust no convierte de forma automáticamente los tipos no booleanos a booleanos. 

Se pueden tener múltiples condiciones con `else if`:

```rust
fn main() {
    let number = 6;

    if number % 4 == 0 {
        println!("number is divisible by 4");
    } else if number % 3 == 0 {
        println!("number is divisible by 3");
    } else if number % 2 == 0 {
        println!("number is divisible by 2");
    } else {
        println!("number is not divisible by 4, 3, or 2");
    }
}
```

>[!IMPORTANT]
>Si el código contiene muchas expresiones `if`, lo ideal sería utilizar un `match`.

Al ser una expresión, un `if` puede ir del lado derecho de la declaración de una variable con `let` y asignarle el valor resultante:

```rust
fn main() {
    let condition = true;
    let number = if condition { 5 } else { 6 };

    println!("The value of number is: {number}");
}
```

Los resultados de las expresiones tienen que ser del mismo tipo, ya que Rust debe saber en tiempo de compilación el tipo que tiene la variable, de lo contrario no hay garantías en el código y rastrear el error lo haría más complejo para cada caso hipotético.

>[!NOTE]
>Es más idiomático usar `if` como expresión que utilizar `let mut` para reasignaciones.


### Bucles

#### loop

Repite de forma infinita hasta que explícitamente se le diga que se detenga.

```rust
fn main() {
    loop {
        println!("again!");
    }
}
```

Con la palabra clave `break` se sale del bucle y con `continue` omite el resto del código de la iteración actual y pasa a la siguiente iteración.

>[!NOTE]
>Al momento de retornar un valor con palabras clave como `break` y `continue` es opcional colocar `;` al final, pero en expresiones es obligatorio **NO** ponerlo.

Con ayuda de etiquetas se pueden nombrar bucles para identificarlos y poder salirse de un bucle específico `break 'nombre_bucle`, de lo contrario se saldrá del bucle más interior con solo `break`:

```rust
fn main() {
    let mut count = 0;
    'counting_up: loop {
        println!("count = {count}");
        let mut remaining = 10;

        loop {
            println!("remaining = {remaining}");
            if remaining == 9 {
                break;
            }
            if count == 2 {
                break 'counting_up;
            }
            remaining -= 1;
        }

        count += 1;
    }
    println!("End count = {count}");
}
```

#### while

Itera hasta que la condición deja de ser `true`, en ese momento sale del bucle porque implicítamente llama a `break`.

```rust
fn main() {
    let mut number = 3;

    while number != 0 {
        println!("{number}!");

        number -= 1;
    }

    println!("LIFTOFF!!!");
}
```

#### for

Otra alternativa que aumenta la seguridad en el código es utilizando un bucle `for`:

```rust
fn main() {
    let a = [10, 20, 30, 40, 50];

    for element in a {
        println!("the value is: {element}");
    }
}
```

Se puede lograr lo anterior con un `while`, sin embargo, ¿qué pasaría si mi arreglo cambia su longitud y yo no actualicé la condición? Esto provoca errores o pérdida de datos. Además de que el compilador agrega código en tiempo de ejecución para validar esa condición. Un ejemplo con `while` pero que **NO** es recomendado y es equivalente al del anterior es:

```rust
fn main() {
    let a = [10, 20, 30, 40, 50];
    let mut index = 0;

    while index < 5 {
        println!("the value is: {}", a[index]);

        index += 1;
    }
}
```

>[!IMPORTANT]
>Siempre que se pueda, utilizar un bucle `for` antes que un `while`.

Incluso se puede y se recomienda usar un bucle `for` si el número de iteraciones es conocida.

```rust
fn main() {
	// 1..4 es un Range, donde los valores serían 1, 2 y 3, excluye el 4
    for number in 1..4 {
        println!("{number}!");
    }
    
    // incluye el 4
    for number in 1..=4 {
        println!("{number}!");
    }
    
    // inverso
    for number in (1..4).rev() {
        println!("{number}!");
    }
    
    println!("LIFTOFF!!!");
}
```

>[!NOTE]
>- Usar`for` cuando itere sobre una colección o rango conocido. 
>- Usar `while` cuando la condición de salida depende de un estado.
>- Usar `loop` cuando necesite retornar un valor del bucle o la condición de salida es compleja.

