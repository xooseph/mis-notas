Siempre son inmutables y se tiene que especifica su tipo. Se utiliza la [[palabra clave]] `const`.

Se pueden declarar en cualquier ámbito, incluyendo el global.

Se establecen en una expresión de constante y no por el resultado de una operación, que se hace en tiempo de ejecución (las de compilación si son válidas, p.e. 
`const THREE_HOURS_IN_SECONDS: u32 = 60 * 60 * 3;`)

La convención es nombrarla de la forma [[kebab case]] pero en mayúsculas.