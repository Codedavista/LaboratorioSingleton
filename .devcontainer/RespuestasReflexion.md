- ¿Cuál es el resultado de `(config1 == config2)` después de aplicar Singleton?
R = Es true, porque config1 y config2 guardan la misma referencia de memoria que devuelve AppConfig.getInstance().

- ¿Por qué el campo `instance` debe ser `static`?
R = Porque debe pertenecer a la clase AppConfig y no a un objeto. Además, como el constructor es privado, no se puede crear un objeto primero para pedirle la instancia. Lo que se necesita es hacer que el método estático AppConfig.getInstance() pueda acceder a instance directamente desde la clase.

- ¿Qué ventaja tiene garantizar que exista una única instancia de configuración?
R = Garantiza que haya consistencia en los datos de toda la aplicación. por ejemplo, si un módulo cambia el tema o el idioma, el cambio se refleja inmediatamente en todo el sistema, además de que ahorra memoria porque no instancia objetos duplicados.

- ¿Cuál es la principal desventaja de la inicialización ansiosa?
R = Que la instancia se crea en cuanto la clase se carga en memoria, incluso si nunca llega a utilizarse durante la ejecución del programa. Si el objeto fuera muy pesado de inicializar, se desperdiciarían recursos al arrancar la aplicación.

- ¿Qué problema puede aparecer si el Singleton guarda estado global y la aplicación crece mucho?
R = Que hay demasiado acomplamiento, o sea, que muchas clases dependerían directamente del Singleton, por lo que sería difícil saber que parte del código modificó el estado. También complica las pruebas unitarias porque el estado de una prueba afecta a la siguiente.

- Resultado de impresión en terminal:
Theme: Dark, Language: EN
Theme: Dark, Language: EN
Are these the same instance? true