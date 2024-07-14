VARIABLES
-------------------------------------------------------------------------------------------------------------------------

En Kotlin, la declaración de variables ofrece diversas opciones para manejar datos de manera flexible y segura 
Para empezar, puedes usar val para definir variables inmutables, ideales para valores que no cambiarán después de la inicialización, como el valor de π:

EJEMPLO:
val pi = 3.14

Por otro lado, var te permite crear variables mutables, cuyos valores pueden modificarse durante la ejecución, como en el caso de un nombre que puede cambiar:

EJEMPLO:
var nombre = "Juan"
nombre = "Pedro"

Kotlin permite especificar explícitamente el tipo de variable si es necesario, aunque el compilador puede inferirlo automáticamente en la mayoría de los casos:

EJEMPLO:
val edad: Int = 30
var salario: Double = 2500.50

Para manejar inicialización tardía o nulabilidad,puedes usar lateinit para variables que no se inicializan de inmediato o declararlas con el tipo nulo (String?) 
y asignarles un valor posteriormente:

EJEMPLO:
lateinit var nombre: String
var direccion: String? = null

Finalmente, para definir constantes que no cambian, puedes usar const val dentro de clases o como propiedades de nivel superior, 
asegurando que su valor sea constante durante la ejecución:

EJEMPLO:
const val PI = 3.1416

Estas características hacen que Kotlin sea versátil y eficiente para manejar diferentes tipos de datos y escenarios de programación, 
asegurando tanto la flexibilidad como la seguridad en la manipulación de variables y constantes.

-------------------------------------------------------------------------------------------------------------------------

CONSTANTES
-------------------------------------------------------------------------------------------------------------------------

 En Kotlin, las constantes también pueden manejar nulos de manera segura mediante las siguientes técnicas:

Constantes no nulas por defecto:
Al igual que las variables, las constantes en Kotlin son no nulas por defecto. 
Esto implica que una constante de tipo val no puede contener null a menos que se declare explícitamente como nullable.


val PI: Double = 3.14159 // No puede ser null
val nombre: String? = null // Puede ser null

Operadores seguros (?.):
El operador ?. también se puede utilizar con constantes para acceder a miembros de un objeto solo si la referencia no es nula.


val longitud: Int? = nombre?.length

Operador de elvis (?:):
El operador ?: permite proporcionar un valor por defecto en caso de que la constante sea null.


val nombreLength: Int = nombre?.length ?: 0

Llamadas seguras (let):
La función let se puede usar con constantes para ejecutar un bloque de código solo si el objeto no es nulo.


nombre?.let {
    println("El nombre es $it")
}

Lanzamiento explícito de excepciones (!!):
Al igual que con las variables, se puede forzar una excepción NullPointerException mediante el uso del operador !! para indicar que se asume la no nulabilidad de una constante.


val length: Int = nombre!!.length

Estas estrategias permiten manejar las constantes nulas de manera efectiva en Kotlin, 
asegurando la integridad y la seguridad del código al evitar excepciones NullPointerException y manejar valores por defecto de manera adecuada cuando sea necesario.

-------------------------------------------------------------------------------------------------------------------------

OPCIONALES
-------------------------------------------------------------------------------------------------------------------------

En Kotlin, puedes declarar variables que pueden contener valores nulos agregando ? al tipo de dato, 
lo que evita errores de NullPointerException.

Puedes usar el operador ?. para realizar operaciones seguras con valores nulos, como acceder a propiedades o llamar métodos sin preocuparte por que la variable sea nula.

EJEMPLO:
val longitudNombre = nombre?.length

El operador Elvis ?: te permite proporcionar un valor predeterminado si una expresión es nula.

EJEMPLO:
val longitudOpcion = nombre?.length ?: -1

Para convertir tipos que pueden ser nulos a tipos no nulos, se usa as?, que devuelve null si la conversión falla.

EJEMPLO:
val numero: Int? = edad as? Int

Evita usar !! siempre que sea posible, ya que fuerza una excepción NullPointerException. lo cual compromete la estabilidad y confiabilidad de la aplicación.

EJEMPLO:
val longitud = nombre!!.length

Kotlin también ofrece tipos de datos que no admiten valores nulos, lo que ayuda a prevenir errores de referencia nula en tiempo de compilación.

EJEMPLO:
val cantidad: Int = 10 // No puede ser nulo

Al definir funciones con parámetros que pueden ser nulos, especifica explícitamente que el parámetro puede ser nulo usando ?.

EJEMPLO:
fun longitudNombre(nombre: String?): Int {
    return nombre?.length ?: 0
}

Estas características hacen que Kotlin sea seguro y robusto para manejar nulabilidad, mejorando la claridad y seguridad del código.

-------------------------------------------------------------------------------------------------------------------------

NULOS
-------------------------------------------------------------------------------------------------------------------------

En Kotlin, "null" es manejado de manera explícita a través del sistema de tipos del lenguaje, 
lo que ayuda a prevenir errores comunes relacionados con referencias nulas (NullPointerException). Aquí tienes un resumen sobre cómo Kotlin aborda el manejo de nulos:

Tipos no nulos por defecto:
En Kotlin, los tipos de datos son no nulos por defecto. Esto significa que una variable de tipo String no puede contener null a menos que se declare explícitamente como nullable.

EJEMPLO:
val nombre: String = "Juan" // No puede ser null
val apellido: String? = null // Puede ser null

Operadores seguros (?.):
El operador ?. permite acceder a miembros de un objeto solo si la referencia no es nula, evitando así excepciones NullPointerException.

EJEMPLO:
val longitud: Int? = nombre?.length

Operador de elvis (?:):
El operador ?: proporciona un valor por defecto en caso de que una expresión sea null.

EJEMPLO:
val longitudNombre: Int = nombre?.length ?: 0

Llamadas seguras (let):
La función let permite ejecutar un bloque de código solo si el objeto no es nulo.

EJEMPLO:
apellido?.let {
    println("El apellido es $it")
}

Lanzamiento explícito de excepciones (!!):
Kotlin también permite forzar una excepción NullPointerException mediante el uso del operador !! para indicar que el programador asume la no nulabilidad de una expresión.

EJEMPLO:
val longitud: Int = nombre!!.length

Estas características ayudan a mejorar la robustez y la claridad del código al manejar las referencias nulas de manera explícita, 
reduciendo significativamente los errores comunes relacionados con nulos en tiempo de ejecución.

-------------------------------------------------------------------------------------------------------------------------
