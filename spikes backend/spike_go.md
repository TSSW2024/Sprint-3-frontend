# Que es Go

Go es un lenguaje de programación que se utiliza principalmente en el desarrollo backend de páginas web y aplicaciones. Entre sus características se encuentran:

- **Simplicidad:** la sintaxis de este lenguaje de programación es bastante entendible, es clara y simple.
- **Código abierto:** otro aspecto importante de Go es que al ser de código abierto muchos usuarios son capaces de crear distintas librerías y programas nuevos.
- **Facilidad de uso:** Go fue creado por Google para facilitar la vida al máximo de los desarrolladores, esto debido a su sintaxis, administración automática de memoria y eficiencia en la compilación.

Otro punto importante es que al estar familiarizados con C y C++, nos resultará más fácil aprender programación, ya que entre sus estructuras de control se encuentran los ya conocidos condicionales `if` y `switch`, además del bucle `for` y las funciones `break` y `continue`. La diferencia más grande es que los paréntesis en estas se eliminan, pero fuera de eso, esas estructuras de control se me hacen muy familiares.

Ok, ahora hablando de las variables también ocurre un cambio notable con respecto a C, más específicamente en su declaración y algunos cambios de nombres. Algunos nombres se mantienen o tienen pequeños cambios como las variables: `int`, `float64` o `float32`, `string` y `bool`. Los array, los struct y los punteros siguen siendo iguales a los de C. También hay algunas variables que cambian o que simplemente no tienen un equivalente en C++ como las variables:

- **Byte:** que vendría siendo el equivalente a la variable `char`.
- **Rune:** que no creo que tenga equivalente en C ya que representa los caracteres Unicode.
- **Map:** Estructura de datos que asocia claves únicas a valores.

Por último, como dije, la estructura en la que se escriben las variables es algo diferente a la de C++. Aquí un ejemplo:

```go
var número int = 20
```
Como ven en la sintaxis, se añade un `var` además de que el nombre se pone antes del tipo de variable, además de una obvia falta de `;`.

Ahora hablando de la biblioteca estándar, esta tiene diversas funciones que sirven para diferentes trabajos:

- `fmt.Println()`: Imprime en la consola.
- `fmt.Printf()`: Imprime en la consola con formato.
- `fmt.Sprintf()`: Formatea una cadena sin imprimir en la consola.
- `os.Exit()`: Sale del programa con un código de estado.
- `os.Args`: Argumentos de línea de comandos.
- `os.Open()`, `os.Create()`: Abre y crea archivos.
- `os.Stdout`, `os.Stdin`, `os.Stderr`: Entrada, salida y error estándar.
- `strconv.Itoa()`: Convierte un entero a una cadena.
- `strconv.Atoi()`: Convierte una cadena a un entero.
- `strconv.ParseFloat()`: Convierte una cadena a un número de punto flotante.
- `strings.Split()`: Divide una cadena en subcadenas.
- `strings.Join()`: Une una lista de cadenas en una sola.
- `strings.Contains()`: Verifica si una cadena contiene otra.
- `math.Sqrt()`: Raíz cuadrada.
- `math.Pow()`: Potenciación.
- `math.Sin()`, `math.Cos()`, `math.Tan()`: Funciones trigonométricas.
- `time.Now()`: Obtiene la hora actual.
- `time.Parse()`: Convierte una cadena en un objeto `time.Time`.
- `time.Sleep()`: Detiene la ejecución del programa por un período de tiempo.
- `io.Copy()`: Copia datos de una fuente a un destino.
- `io/ioutil.ReadFile()`: Lee el contenido de un archivo completo en memoria.
- `bufio.NewReader()`: Crea un nuevo lector para entrada.
- `bufio.NewScanner()`: Crea un escáner para leer datos línea por línea.
- `net/http`: Para crear servidores web y realizar solicitudes HTTP.
- `net/http/httputil`: Para manipulación avanzada de solicitudes y respuestas HTTP.
- `json.Marshal()`: Convierte un valor Go en JSON.
- `json.Unmarshal()`: Convierte JSON en un valor Go.

Estas son algunas de las funciones más usadas en la biblioteca estándar de Go.

Por último, daré un pequeño vistazo a las herramientas de desarrollo más básicas y fundamentales en Go:

- `go build`: Para compilar el código y generar ejecutables o paquetes de biblioteca.
- `go run`: Para compilar y ejecutar programas en una sola línea de comando.
- `go fmt`: Para formatear el código según las convenciones de estilo de Go.
- `go test`: Para ejecutar pruebas unitarias.
- `go get`: Para descargar y compilar paquetes de Go desde repositorios remotos.
[enlace a programa basico en Go](https://onlinegdb.com/xltbKdXyv)