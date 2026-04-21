Rust es un lenguaje estáticamente tipado, lo que se debe conocer su tipo de todas las variables en tiempo de compilación. Por lo general, el compilador infiere su tipo en función de su valor y cómo se usa.

### Tipos escalares

Representa un solo valor. En Rust existen 4.

#### Enteros

Número sin componente fraccionario.

![[Pasted image 20260420223145.png]]

Se pueden escribir literales enteros.

![[Pasted image 20260420224002.png]]
Se utiliza (de forma opcional) `_` como separador de los dígitos 1000 -> 1_000.

`i32` -> tipo predeterminado

`isize` o `usize` -> para indexar algún tipo de colección


> [!IMPORTANT]
> **Desbordamiento de enteros**
> 
>Hay dos comportamientos al momento que supere el valor permitido dentro de una variable de cierto tipo:
>
>- Cuando se compila en modo depuración, Rust comprueba en tiempo de ejecución si existe desbordamiento y lanzará un error.
>- Cuando está compilando en modo `--release`. Rust no incluye las comprobaciones anteriores, por lo que realiza una envoltura de complemento a dos, p.e. para una variable de tipo `u8` el valor 256 se convierte a 0 y 257 a 1. El programa no se desborda pero la variable tiene un valor no deseado.

#### Puntos flotantes

Números con puntos decimales. Hay `f32` y `f64`, este último es el predeterminado, ya que tiene mayor precisión. Ambos son con signo.

`f32` -> de precisión simple

`f64` -> de doble precisión

La división entera se trunca hacia cero al entero más cercano.

#### Booleano

- Dos valores: `true` y `false`

- 1 byte de tamaño

- El tipo se especifica con `bool`

- Se utilizan en condicionales

#### Carácter

`char` el tipo alfabético más primitivo de Rust

Tiene un tamaño de 4 bytes

Representa un valor UNICODE (mucho más que el ASCII): letras acentuadas, caracteres chinos, japoneses y coreanos, emojis y espacios de ancho cero.

Se utilizan comillas simples para especificar literales.

### Compuestos

Pueden agrupar múltiples valores en un solo tipo.

#### Tuplas

Tienen una longitud fija una vez declaradas.

```rust
let tup: (i32, f64, u8) = (500, 6.4, 1);
```

Hay dos formas de obtener los valores de la tupla, desestructurando su valor y convirtiéndola en variables separadas o accediendo directamente a un elemento de esa tupla con `.`:

```rust
let (x, y, z) = tup;

let integer = tup.0;
```

La tupla sin ningún valor se conoce como **unit**:

```rust
let new_tup: () = ();
```

Representa un valor vacío o un tipo de retorno vacío.

#### Arreglos

Cada elemento tiene el mismo tipo de variable y su longitud es fija.

```rust
let a: [i32; 5] = [1, 2, 3, 4, 5];
```

Se asignan en el **stack**.

Son útiles cuando se sabe que el número de elementos nunca cambiará.

Una forma más concisa de escribir el mismo elemento n-veces sería:

```rust
let a = [3; 4];
```

que es equivalente a:

```rust
let a = [3, 3, 3, 3];
```

Se accede a los elementos mediante la indexación:

```rust
let first = a[0];
```

Rust comprobará en tiempo de ejecución que el elemento al que se quiere acceder por medio del índice sea menor al arreglo, de lo contrario entrará en pánico.


> [!NOTE]
> Esto evita que acceda a memoria inválida, lo que en otros lenguajes de bajo nivel no hacen.