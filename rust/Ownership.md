	Es el conjunto de reglas que define cómo un programa de Rust debe administrar la memoria.

El compilador verifica ese conjunto de reglas.

Si alguna de las reglas se viola, el programa no se compilará.

El *ownership* no ralentiza el programa mientras se ejecuta.

>[!IMPORTANT]
>**Analogía:** Tengo un libro, que es MÍO, si se lo PRESTO a alguien, sigue siendo MÍO, cuando me lo devuelve, se dice que regreso a mi POSESIÓN.

### El Stack y el Heap

Ambas son partes de la memoria disponible para el código para usar en tiempo de ejecución.

El *stack* almacena valores en el orden en el que los recibe y los elimina en el orden opuesto. Se conoce como *LIFO* -> *Last In, First Out*.

En el *stack*, agregar -> empujar en el *stack*, eliminar -> sacar del *stack*.

>[!IMPORTANT]
>Todos los datos almacenados en el **stack** deben tener un tamaño conocido y fijo. Los datos con un tamaño desconocido o un tamaño que pueden cambiar van en el **heap**.

El *heap* es menos organizado.

**Asignar en el heap o asignar:** Colocar datos en el *heap* -> solicita una cantidad de espacio -> el administrador encuentra un lugar vacío (suficientemente grande) en el *heap* -> lo marca en uso -> regresa un puntero (dirección)

El puntero es de tamaño conocido y fijo, así que se puede almacenar en el *stack*, pero los datos reales deben seguir el puntero, que sigue en el *heap*.

>[!NOTE]
>Empujar en el stack es más rápido que asignar en el heap, porque nunca tiene que buscar un espacio para almacenar los nuevos datos, siempre está en la parte superior de la pila.
>
>Acceder a los datos en el heap es más lento porque debe seguir al puntero.
>

El principal propósito del *ownership* es administrar los datos en el *heap*.

### Reglas del ownership

1. Cada valor en Rust tiene un *propietario*
2. Solo puede haber un propietario a la vez
3. Cuando el propietario sale del alcance, el valor se descartará

### Ámbito de la variable

**Contexto de ejecución:** rango del programa en el que un elemento es válido.

```rust
fn say_hi () {

// hi no es válido aquí, aún no está declarado

let hi = "bye"; // hi es válido desde aquí

} // este ámbito termina aquí, hi ya no es válido
```

