Las variables son inmutables por defecto.

La inmutabilidad hace que el programa sea seguro en el manejo de variables, además de que con los errores de compilación garantiza que no deben cambiar, por lo tanto, uno no tiene que *rastrear* esos detalles.

Además un variable inmutable hace que exista **concurrencia**, es decir los datos se pueden compartir entre hilos sin riesgo alguno.

Sin embargo, se puede hacer una variable mutable anteponiendo la [[palabra clave]] `mut`.