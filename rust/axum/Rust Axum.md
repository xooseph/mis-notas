Macro #[tokio::main]

- Inicia el runtime asíncrono
- Transforma el `async fn main` en una función regular `main`
- Configura lo necesario de los componentes del runtime de *Tokio*

Necesito un `Router` para crear la app, que contiene rutas y funciones para realizar peticiones HTTP.

Un listener TCP para conectar a un puerto.

Inicializar servidor -> `axum::serve(listener);`

Centralizar los errores de la API en un enum.

La macro #[derive(Debug)] permite imprimir los errores para debuggear.

- **NotFound(404)** cuando un recurso no existe
- **InvalidInput(400)** un string con un mensaje personalizado
- **InternalError(500)**

## Implementación IntoResponse

Axum utiliza el trait de `IntoResponse` para retornar valores en la respuesta HTTP actual.

Para implementarlo cualquier controlador que retorne un tipo de ApiError conoce automáticamente cómo convertir un error en una respuesta HTTP adecuada.

`handler() -> Result<T, ApiError>`

Es similar a una interfaz este trait.

La función `into_response` tiene un match interno que dependiendo del error, regresará un código y un mensaje específicos.

`self` -> se refiere a la instancia específica del enum a la que esta función está siendo llamada.
