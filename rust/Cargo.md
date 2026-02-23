Cargo es el sistema de compilación y administrador de paquetes de Rust.

Al crear un nuevo proyecto con `cargo`, lo hace inicializándolo con `git` por defecto, si está dentro de un repo, hace la excepción.

Para la configuración del proyecto se utiliza un archivo [[TOML]].

Con `cargo build` se construye el proyecto y como la compilación predeterminada es de depuración, el binario está en la carpeta `target/debug`. También crea el archivo `Cargo.lock`, que sirve para rastrear versiones de dependencias, lo hace en automático.

Para las versiones de lanzamiento se coloca la flag `--release` para compilar, lo hará con optimizaciones, por lo tanto tardará más pero la ejecución será más rápida. Con este binario se hacen las pruebas de rendimiento. Se encuentra en la carpeta `target/release`.

`cargo run` hace la parte de `build` y después ejecuta el binario. Si no hay cambios en el código, no lo vuelve a construir, solo ejecuta.

`cargo check` solo comprueba rápidamente el código para asegurar que compila, ideal para verificar errores sin la necesidad de crear el ejecutable.

