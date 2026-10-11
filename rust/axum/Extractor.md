Una función handler -> función async que toma cualquier número de **extractores** como argumentos.

Un extractor es un tipo que implementa *FromRequest*.

JSON es un extractor que consume la petición del cuerpo y lo deserializa como JSON en algún tipo de destino.

## Extractores comúnes

- JSON
- TypedHeader
- Path
- Extension
- Query

*Request* en si mismo es un extractor.

Tener cuidado de combinar con otros extractores porque consumirá todas las extensiones, así que hay que ponerlo al final.

Solo se puede extraer una vez el body, ya que la transmisión es asíncrona.

Evitar extraer el cuerpo en los controladores o asegurarse de que el middleware lo reinserte usando `RequestParts::body_mut`.

Los extractores definidos en *axum* recharazán la solicitud si no coincide.

|-> **Extractor opcional** -> envolverlo con `Option`- con `Result` es igual pero da la razón el error.

No es posible acceder directamente a los errores. Esto da más flexibilidad y permite cambiar implementaciones internas sin romper la API pública.

> [!NOTE]
> **Query** -> customizar y modificar un recurso
> **Path** -> identifica un recurso

