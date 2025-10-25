# Documentación Completa de PHP 7.2

Esta documentación interactiva cubre todos los conceptos básicos de PHP 7.2 ejecutándose en Jupyter Notebook.

**Configuración actual:**
- PHP 7.2.34 Thread Safe
- Extensión ZMQ habilitada
- Entorno XAMPP configurado

---

## 1. Información del Sistema PHP

Comencemos verificando nuestra instalación de PHP y sus características:


```PHP

echo "=== INFORMACIÓN DEL SISTEMA PHP ===\n";
echo "Versión de PHP: " . PHP_VERSION . "\n";
echo "Sistema Operativo: " . PHP_OS . "\n";
echo "Thread Safety: " . (ZEND_THREAD_SAFE ? 'Habilitado' : 'Deshabilitado') . "\n";
echo "Extensión ZMQ: " . (extension_loaded('zmq') ? 'Cargada' : 'No disponible') . "\n";
echo "Memoria máxima: " . ini_get('memory_limit') . "\n";
echo "Zona horaria: " . date_default_timezone_get() . "\n";
echo "Fecha actual: " . date('Y-m-d H:i:s') . "\n";
```




    === INFORMACIÓN DEL SISTEMA PHP ===
    
    






    Versión de PHP: 7.2.34
    
    






    Sistema Operativo: WINNT
    
    






    Thread Safety: Habilitado
    
    






    Extensión ZMQ: Cargada
    
    






    Memoria máxima: 128M
    
    






    Zona horaria: UTC
    
    






    Fecha actual: 2025-10-25 23:45:46
    
    



## 2. Variables y Tipos de Datos

PHP es un lenguaje dinámicamente tipado. Las variables se declaran con el símbolo `$`.


```PHP

echo "=== TIPOS DE DATOS EN PHP ===\n";

// String
$nombre = "Juan Pérez";
$apellido = 'García';

// Integer
$edad = 25;
$año = 2024;

// Float
$altura = 1.75;
$peso = 70.5;

// Boolean
$esEstudiante = true;
$tieneTrabaajo = false;

// NULL
$telefono = null;

// Mostrando tipos y valores
echo "Nombre: $nombre (" . gettype($nombre) . ")\n";
echo "Edad: $edad (" . gettype($edad) . ")\n";
echo "Altura: $altura (" . gettype($altura) . ")\n";
echo "Es estudiante: " . ($esEstudiante ? 'Sí' : 'No') . " (" . gettype($esEstudiante) . ")\n";
echo "Teléfono: " . var_export($telefono, true) . " (" . gettype($telefono) . ")\n";

// Concatenación de strings
$nombreCompleto = $nombre . " " . $apellido;
echo "\nNombre completo: $nombreCompleto\n";
```




    === TIPOS DE DATOS EN PHP ===
    
    






    Nombre: Juan Pérez (string)
    
    






    Edad: 25 (integer)
    
    






    Altura: 1.75 (double)
    
    






    Es estudiante: Sí (boolean)
    
    






    Teléfono: NULL (NULL)
    
    






    
    Nombre completo: Juan Pérez García
    
    



## 3. Constantes

Las constantes son valores que no pueden cambiar durante la ejecución del script.


```PHP

echo "=== CONSTANTES ===\n";

// Definir constantes
define('NOMBRE_SITIO', 'Mi Sitio Web');
define('VERSION', '1.0.0');
define('PI', 3.14159);

// Constantes de clase (PHP 5.3+)
const SALUDO = 'Hola Mundo';

echo "Sitio: " . NOMBRE_SITIO . "\n";
echo "Versión: " . VERSION . "\n";
echo "Pi: " . PI . "\n";
echo "Saludo: " . SALUDO . "\n";

// Constantes mágicas
echo "\n=== CONSTANTES MÁGICAS ===\n";
echo "Línea actual: " . __LINE__ . "\n";
echo "Archivo actual: " . basename(__FILE__) . "\n";
echo "Directorio: " . __DIR__ . "\n";
echo "Versión PHP: " . PHP_VERSION . "\n";
```




    === CONSTANTES ===
    
    






    Sitio: Mi Sitio Web
    
    






    Versión: 1.0.0
    
    






    Pi: 3.14159
    
    






    Saludo: Hola Mundo
    
    






    
    === CONSTANTES MÁGICAS ===
    
    






    Línea actual: 14
    
    






    Archivo actual: 
    
    






    Directorio: C:\Users\eduar\Documents\luenguaje\php\documentacion
    
    






    Versión PHP: 7.2.34
    
    



## 4. Operadores

PHP soporta diversos tipos de operadores para realizar operaciones.


```PHP

echo "=== OPERADORES ARITMÉTICOS ===\n";
$a = 10;
$b = 3;

echo "a = $a, b = $b\n";
echo "Suma: $a + $b = " . ($a + $b) . "\n";
echo "Resta: $a - $b = " . ($a - $b) . "\n";
echo "Multiplicación: $a * $b = " . ($a * $b) . "\n";
echo "División: $a / $b = " . ($a / $b) . "\n";
echo "Módulo: $a % $b = " . ($a % $b) . "\n";
echo "Exponencial: $a ** 2 = " . ($a ** 2) . "\n";

echo "\n=== OPERADORES DE COMPARACIÓN ===\n";
echo "$a == $b: " . ($a == $b ? 'true' : 'false') . "\n";
echo "$a != $b: " . ($a != $b ? 'true' : 'false') . "\n";
echo "$a > $b: " . ($a > $b ? 'true' : 'false') . "\n";
echo "$a < $b: " . ($a < $b ? 'true' : 'false') . "\n";
echo "$a >= $b: " . ($a >= $b ? 'true' : 'false') . "\n";
echo "$a <= $b: " . ($a <= $b ? 'true' : 'false') . "\n";

echo "\n=== OPERADORES LÓGICOS ===\n";
$x = true;
$y = false;

echo "x = true, y = false\n";
echo "x AND y: " . ($x && $y ? 'true' : 'false') . "\n";
echo "x OR y: " . ($x || $y ? 'true' : 'false') . "\n";
echo "NOT x: " . (!$x ? 'true' : 'false') . "\n";
```




    === OPERADORES ARITMÉTICOS ===
    
    






    a = 10, b = 3
    
    






    Suma: 10 + 3 = 13
    
    






    Resta: 10 - 3 = 7
    
    






    Multiplicación: 10 * 3 = 30
    
    






    División: 10 / 3 = 3.3333333333333
    
    






    Módulo: 10 % 3 = 1
    
    






    Exponencial: 10 ** 2 = 100
    
    






    
    === OPERADORES DE COMPARACIÓN ===
    
    






    10 == 3: false
    
    






    10 != 3: true
    
    






    10 > 3: true
    
    






    10 < 3: false
    
    






    10 >= 3: true
    
    






    10 <= 3: false
    
    






    
    === OPERADORES LÓGICOS ===
    
    






    x = true, y = false
    
    






    x AND y: false
    
    






    x OR y: true
    
    






    NOT x: false
    
    



## 5. Estructuras de Control

### If/Else/ElseIf


```PHP

echo "=== ESTRUCTURAS IF/ELSE ===\n";

$nota = 85;

if ($nota >= 90) {
    $calificacion = "Excelente";
} elseif ($nota >= 80) {
    $calificacion = "Muy Bueno";
} elseif ($nota >= 70) {
    $calificacion = "Bueno";
} elseif ($nota >= 60) {
    $calificacion = "Regular";
} else {
    $calificacion = "Insuficiente";
}

echo "Nota: $nota - Calificación: $calificacion\n";

// Operador ternario
$edad = 20;
$status = ($edad >= 18) ? "Adulto" : "Menor";
echo "Edad: $edad - Status: $status\n";

// Operador null coalescing (PHP 7+)
$usuario = null;
$nombreUsuario = $usuario ?? "Invitado";
echo "Usuario: $nombreUsuario\n";
```




    === ESTRUCTURAS IF/ELSE ===
    
    






    Nota: 85 - Calificación: Muy Bueno
    
    






    Edad: 20 - Status: Adulto
    
    






    Usuario: Invitado
    
    



### Switch


```PHP

echo "=== ESTRUCTURA SWITCH ===\n";

$dia = date('N'); // 1 (lunes) a 7 (domingo)

switch ($dia) {
    case 1:
        $nombreDia = "Lunes";
        break;
    case 2:
        $nombreDia = "Martes";
        break;
    case 3:
        $nombreDia = "Miércoles";
        break;
    case 4:
        $nombreDia = "Jueves";
        break;
    case 5:
        $nombreDia = "Viernes";
        break;
    case 6:
    case 7:
        $nombreDia = ($dia == 6) ? "Sábado" : "Domingo";
        break;
    default:
        $nombreDia = "Día inválido";
}

echo "Hoy es $nombreDia (día $dia de la semana)\n";

// Switch con diferentes tipos
$valor = "2";
switch ($valor) {
    case 2:
        echo "Es el número 2\n";
        break;
    case "2":
        echo "Es la cadena '2'\n";
        break;
    default:
        echo "Es otra cosa\n";
}
```




    === ESTRUCTURA SWITCH ===
    
    






    Hoy es Sábado (día 6 de la semana)
    
    






    Es el número 2
    
    



## 6. Bucles (Loops)

PHP ofrece varios tipos de bucles para iterar.


```PHP

echo "=== BUCLE FOR ===\n";
for ($i = 1; $i <= 5; $i++) {
    echo "Iteración $i\n";
}

echo "\n=== BUCLE WHILE ===\n";
$contador = 1;
while ($contador <= 3) {
    echo "Contador: $contador\n";
    $contador++;
}

echo "\n=== BUCLE DO-WHILE ===\n";
$numero = 1;
do {
    echo "Número: $numero\n";
    $numero++;
} while ($numero <= 3);

echo "\n=== BUCLE FOREACH (con array) ===\n";
$colores = ["rojo", "verde", "azul", "amarillo"];

foreach ($colores as $indice => $color) {
    echo "Color [$indice]: $color\n";
}

echo "\n=== BUCLE FOREACH (array asociativo) ===\n";
$persona = [
    "nombre" => "Ana",
    "edad" => 28,
    "ciudad" => "Madrid",
    "profesion" => "Desarrolladora"
];

foreach ($persona as $clave => $valor) {
    echo "$clave: $valor\n";
}
```




    === BUCLE FOR ===
    
    






    Iteración 1
    
    






    Iteración 2
    
    






    Iteración 3
    
    






    Iteración 4
    
    






    Iteración 5
    
    






    
    === BUCLE WHILE ===
    
    






    Contador: 1
    
    






    Contador: 2
    
    






    Contador: 3
    
    






    
    === BUCLE DO-WHILE ===
    
    






    Número: 1
    
    






    Número: 2
    
    






    Número: 3
    
    






    
    === BUCLE FOREACH (con array) ===
    
    






    Color [0]: rojo
    
    






    Color [1]: verde
    
    






    Color [2]: azul
    
    






    Color [3]: amarillo
    
    






    
    === BUCLE FOREACH (array asociativo) ===
    
    






    nombre: Ana
    
    






    edad: 28
    
    






    ciudad: Madrid
    
    






    profesion: Desarrolladora
    
    



## 7. Arrays (Arreglos)

Los arrays son una de las estructuras de datos más importantes en PHP.


```PHP

echo "=== ARRAYS INDEXADOS ===\n";

// Diferentes formas de crear arrays
$frutas = array("manzana", "banana", "naranja");
$numeros = [1, 2, 3, 4, 5];
$mixto = ["texto", 42, true, 3.14];

echo "Frutas: " . implode(", ", $frutas) . "\n";
echo "Números: " . implode(", ", $numeros) . "\n";
echo "Primer número: " . $numeros[0] . "\n";
echo "Último número: " . $numeros[count($numeros) - 1] . "\n";

// Agregar elementos
$frutas[] = "uva";
array_push($frutas, "mango", "piña");
echo "Frutas después de agregar: " . implode(", ", $frutas) . "\n";

echo "\n=== ARRAYS ASOCIATIVOS ===\n";
$estudiante = [
    "id" => 1001,
    "nombre" => "Carlos Rodriguez",
    "edad" => 22,
    "carrera" => "Ingeniería en Sistemas",
    "promedio" => 8.5
];

echo "ID: " . $estudiante["id"] . "\n";
echo "Nombre: " . $estudiante["nombre"] . "\n";
echo "Edad: " . $estudiante["edad"] . " años\n";
echo "Carrera: " . $estudiante["carrera"] . "\n";
echo "Promedio: " . $estudiante["promedio"] . "\n";

// Agregar nuevos campos
$estudiante["email"] = "carlos@example.com";
$estudiante["telefono"] = "123-456-7890";

echo "\nDatos actualizados:\n";
foreach ($estudiante as $campo => $valor) {
    echo ucfirst($campo) . ": $valor\n";
}
```




    === ARRAYS INDEXADOS ===
    
    






    Frutas: manzana, banana, naranja
    
    






    Números: 1, 2, 3, 4, 5
    
    






    Primer número: 1
    
    






    Último número: 5
    
    






    Frutas después de agregar: manzana, banana, naranja, uva, mango, piña
    
    






    
    === ARRAYS ASOCIATIVOS ===
    
    






    ID: 1001
    
    






    Nombre: Carlos Rodriguez
    
    






    Edad: 22 años
    
    






    Carrera: Ingeniería en Sistemas
    
    






    Promedio: 8.5
    
    






    
    Datos actualizados:
    
    






    Id: 1001
    
    






    Nombre: Carlos Rodriguez
    
    






    Edad: 22
    
    






    Carrera: Ingeniería en Sistemas
    
    






    Promedio: 8.5
    
    






    Email: carlos@example.com
    
    






    Telefono: 123-456-7890
    
    



### Funciones de Arrays


```PHP

echo "=== FUNCIONES DE ARRAYS ===\n";

$numeros = [5, 2, 8, 1, 9, 3];
echo "Array original: " . implode(", ", $numeros) . "\n";

// Información del array
echo "Cantidad de elementos: " . count($numeros) . "\n";
echo "Suma total: " . array_sum($numeros) . "\n";
echo "Valor máximo: " . max($numeros) . "\n";
echo "Valor mínimo: " . min($numeros) . "\n";

// Ordenamiento
$numerosAsc = $numeros;
sort($numerosAsc);
echo "Ordenado ascendente: " . implode(", ", $numerosAsc) . "\n";

$numerosDesc = $numeros;
rsort($numerosDesc);
echo "Ordenado descendente: " . implode(", ", $numerosDesc) . "\n";

// Buscar elementos
$buscar = 8;
if (in_array($buscar, $numeros)) {
    $posicion = array_search($buscar, $numeros);
    echo "El número $buscar está en la posición $posicion\n";
}

// Filtrar elementos
$pares = array_filter($numeros, function($n) {
    return $n % 2 == 0;
});
echo "Números pares: " . implode(", ", $pares) . "\n";

// Transformar elementos
$cuadrados = array_map(function($n) {
    return $n * $n;
}, $numeros);
echo "Cuadrados: " . implode(", ", $cuadrados) . "\n";
```




    === FUNCIONES DE ARRAYS ===
    
    






    Array original: 5, 2, 8, 1, 9, 3
    
    






    Cantidad de elementos: 6
    
    






    Suma total: 28
    
    






    Valor máximo: 9
    
    






    Valor mínimo: 1
    
    






    Ordenado ascendente: 1, 2, 3, 5, 8, 9
    
    






    Ordenado descendente: 9, 8, 5, 3, 2, 1
    
    






    El número 8 está en la posición 2
    
    






    Números pares: 2, 8
    
    






    Cuadrados: 25, 4, 64, 1, 81, 9
    
    



## 8. Funciones

Las funciones permiten modularizar y reutilizar código.


```PHP

echo "=== FUNCIONES BÁSICAS ===\n";

// Función simple
function saludar($nombre) {
    return "Hola, $nombre!";
}

// Función con parámetros por defecto
function presentar($nombre, $apellido = "", $edad = null) {
    $resultado = "Mi nombre es $nombre";
    if ($apellido) {
        $resultado .= " $apellido";
    }
    if ($edad !== null) {
        $resultado .= " y tengo $edad años";
    }
    return $resultado;
}

// Función con tipo de datos (PHP 7+)
function calcularArea(float $largo, float $ancho): float {
    return $largo * $ancho;
}

// Función con parámetros variables
function sumar(...$numeros) {
    return array_sum($numeros);
}

// Probar las funciones
echo saludar("María") . "\n";
echo presentar("Juan") . "\n";
echo presentar("Ana", "García") . "\n";
echo presentar("Luis", "Martín", 25) . "\n";
echo "Área: " . calcularArea(5.5, 3.2) . " m²\n";
echo "Suma: " . sumar(1, 2, 3, 4, 5) . "\n";

echo "\n=== FUNCIONES ANÓNIMAS (CLOSURES) ===\n";

// Función anónima
$multiplicar = function($a, $b) {
    return $a * $b;
};

echo "5 × 3 = " . $multiplicar(5, 3) . "\n";

// Usar función anónima con array_map
$numeros = [1, 2, 3, 4, 5];
$dobles = array_map(function($n) { return $n * 2; }, $numeros);
echo "Dobles: " . implode(", ", $dobles) . "\n";
```




    === FUNCIONES BÁSICAS ===
    
    






    Hola, María!
    
    






    Mi nombre es Juan
    
    






    Mi nombre es Ana García
    
    






    Mi nombre es Luis Martín y tengo 25 años
    
    






    Área: 17.6 m²
    
    






    Suma: 15
    
    






    
    === FUNCIONES ANÓNIMAS (CLOSURES) ===
    
    






    5 × 3 = 15
    
    






    Dobles: 2, 4, 6, 8, 10
    
    



## 9. Manejo de Strings (Cadenas)

PHP tiene muchas funciones para trabajar con strings.


```PHP

echo "=== MANIPULACIÓN DE STRINGS ===\n";

$texto = "  Hola Mundo desde PHP 7.2  ";
echo "Original: '$texto'\n";
echo "Longitud: " . strlen($texto) . " caracteres\n";

// Limpieza de strings
$limpio = trim($texto);
echo "Sin espacios: '$limpio'\n";
echo "Minúsculas: " . strtolower($limpio) . "\n";
echo "Mayúsculas: " . strtoupper($limpio) . "\n";
echo "Primera mayúscula: " . ucfirst(strtolower($limpio)) . "\n";
echo "Cada palabra: " . ucwords(strtolower($limpio)) . "\n";

// Buscar en strings
$buscar = "PHP";
if (strpos($limpio, $buscar) !== false) {
    echo "Se encontró '$buscar' en posición: " . strpos($limpio, $buscar) . "\n";
}

// Reemplazar
$nuevo = str_replace("PHP 7.2", "PHP", $limpio);
echo "Reemplazado: $nuevo\n";

// Dividir strings
$partes = explode(" ", $limpio);
echo "Palabras: " . count($partes) . " -> " . implode(" | ", $partes) . "\n";

// Substring
echo "Primeros 10 caracteres: " . substr($limpio, 0, 10) . "\n";
echo "Últimos 5 caracteres: " . substr($limpio, -5) . "\n";

echo "\n=== FORMATEO DE STRINGS ===\n";
$nombre = "Carlos";
$edad = 25;
$altura = 1.75;

// sprintf
$formato = sprintf("Nombre: %s, Edad: %d años, Altura: %.2f m", $nombre, $edad, $altura);
echo $formato . "\n";

// Interpolación de variables en strings
echo "Mi nombre es $nombre y tengo $edad años\n";
echo "Mi altura es {$altura}m\n";
```




    === MANIPULACIÓN DE STRINGS ===
    
    






    Original: '  Hola Mundo desde PHP 7.2  '
    
    






    Longitud: 28 caracteres
    
    






    Sin espacios: 'Hola Mundo desde PHP 7.2'
    
    






    Minúsculas: hola mundo desde php 7.2
    
    






    Mayúsculas: HOLA MUNDO DESDE PHP 7.2
    
    






    Primera mayúscula: Hola mundo desde php 7.2
    
    






    Cada palabra: Hola Mundo Desde Php 7.2
    
    






    Se encontró 'PHP' en posición: 17
    
    






    Reemplazado: Hola Mundo desde PHP
    
    






    Palabras: 5 -> Hola | Mundo | desde | PHP | 7.2
    
    






    Primeros 10 caracteres: Hola Mundo
    
    






    Últimos 5 caracteres: P 7.2
    
    






    
    === FORMATEO DE STRINGS ===
    
    






    Nombre: Carlos, Edad: 25 años, Altura: 1.75 m
    
    






    Mi nombre es Carlos y tengo 25 años
    
    






    Mi altura es 1.75m
    
    



## 10. Programación Orientada a Objetos (POO)

PHP soporta programación orientada a objetos completa.


```PHP

echo "=== CLASES Y OBJETOS ===\n";

// Definir una clase
class Persona {
    // Propiedades
    private $nombre;
    private $edad;
    protected $email;
    public $activo;
    
    // Constructor
    public function __construct($nombre, $edad) {
        $this->nombre = $nombre;
        $this->edad = $edad;
        $this->activo = true;
        echo "Nueva persona creada: $nombre\n";
    }
    
    // Métodos públicos (getters)
    public function getNombre() {
        return $this->nombre;
    }
    
    public function getEdad() {
        return $this->edad;
    }
    
    // Setters
    public function setEmail($email) {
        $this->email = $email;
    }
    
    // Método personalizado
    public function saludar() {
        return "Hola, soy {$this->nombre} y tengo {$this->edad} años";
    }
    
    // Método mágico __toString
    public function __toString() {
        return $this->saludar();
    }
}

// Crear objetos
$persona1 = new Persona("María González", 30);
$persona2 = new Persona("Pedro Martínez", 25);

echo "Persona 1: " . $persona1->saludar() . "\n";
echo "Persona 2: " . $persona2 . "\n";

// Acceder a propiedades públicas
$persona1->activo = false;
echo "Estado de " . $persona1->getNombre() . ": " . ($persona1->activo ? 'Activo' : 'Inactivo') . "\n";
```




    === CLASES Y OBJETOS ===
    
    






    Nueva persona creada: María González
    
    






    Nueva persona creada: Pedro Martínez
    
    






    Persona 1: Hola, soy María González y tengo 30 años
    
    






    Persona 2: Hola, soy Pedro Martínez y tengo 25 años
    
    






    Estado de María González: Inactivo
    
    



## 11. Manejo de Fechas

PHP ofrece excelentes herramientas para trabajar con fechas y tiempo.


```PHP

echo "=== FECHAS Y TIEMPO ===\n";

// Fecha actual
$ahora = new DateTime();
echo "Fecha actual: " . $ahora->format('Y-m-d H:i:s') . "\n";
echo "Formato personalizado: " . $ahora->format('d/m/Y') . "\n";

// Crear fecha específica
$cumpleanos = new DateTime('1995-06-15');
echo "Cumpleaños: " . $cumpleanos->format('l, d F Y') . "\n";

// Calcular diferencia de fechas
$diferencia = $ahora->diff($cumpleanos);
echo "Edad: " . $diferencia->y . " años, " . $diferencia->m . " meses y " . $diferencia->d . " días\n";

// Modificar fechas
$futuro = clone $ahora;
$futuro->add(new DateInterval('P1Y2M3D')); // +1 año, 2 meses, 3 días
echo "Fecha futura: " . $futuro->format('Y-m-d') . "\n";

// Timestamp
echo "Timestamp actual: " . time() . "\n";
echo "Fecha desde timestamp: " . date('Y-m-d H:i:s', time()) . "\n";
```




    === FECHAS Y TIEMPO ===
    
    






    Fecha actual: 2025-10-25 23:45:46
    
    






    Formato personalizado: 25/10/2025
    
    






    Cumpleaños: Thursday, 15 June 1995
    
    






    Edad: 30 años, 4 meses y 10 días
    
    






    Fecha futura: 2026-12-28
    
    






    Timestamp actual: 1761435946
    
    






    Fecha desde timestamp: 2025-10-25 23:45:46
    
    



## 12. Manejo de Archivos

PHP permite leer y escribir archivos fácilmente.


```PHP

echo "=== MANEJO DE ARCHIVOS ===\n";

$nombreArchivo = 'ejemplo.txt';
$contenido = "Hola mundo desde PHP 7.2!\nEsta es una segunda línea.\nY esta es la tercera.";

// Escribir archivo
if (file_put_contents($nombreArchivo, $contenido)) {
    echo "Archivo '$nombreArchivo' creado exitosamente\n";
} else {
    echo "Error al crear el archivo\n";
}

// Verificar si existe
if (file_exists($nombreArchivo)) {
    echo "El archivo existe\n";
    echo "Tamaño: " . filesize($nombreArchivo) . " bytes\n";
}

// Leer archivo completo
$contenidoLeido = file_get_contents($nombreArchivo);
echo "Contenido completo:\n$contenidoLeido\n\n";

// Leer línea por línea
echo "Leyendo línea por línea:\n";
$lineas = file($nombreArchivo, FILE_IGNORE_NEW_LINES);
foreach ($lineas as $numero => $linea) {
    echo "Línea " . ($numero + 1) . ": $linea\n";
}

// Limpiar (eliminar archivo de prueba)
if (unlink($nombreArchivo)) {
    echo "\nArchivo eliminado correctamente\n";
}
```




    === MANEJO DE ARCHIVOS ===
    
    






    Archivo 'ejemplo.txt' creado exitosamente
    
    






    El archivo existe
    
    






    Tamaño: 75 bytes
    
    






    Contenido completo:
    Hola mundo desde PHP 7.2!
    Esta es una segunda línea.
    Y esta es la tercera.
    
    
    






    Leyendo línea por línea:
    
    






    Línea 1: Hola mundo desde PHP 7.2!
    
    






    Línea 2: Esta es una segunda línea.
    
    






    Línea 3: Y esta es la tercera.
    
    






    
    Archivo eliminado correctamente
    
    



## 13. Expresiones Regulares

PHP soporta expresiones regulares para búsqueda y manipulación avanzada de texto.


```PHP

echo "=== EXPRESIONES REGULARES ===\n";

$texto = "Mi email es usuario@ejemplo.com y mi teléfono es 123-456-7890";
echo "Texto original: $texto\n\n";

// Buscar email
$patronEmail = '/[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}/';
if (preg_match($patronEmail, $texto, $matches)) {
    echo "Email encontrado: " . $matches[0] . "\n";
}

// Buscar teléfono
$patronTelefono = '/\d{3}-\d{3}-\d{4}/';
if (preg_match($patronTelefono, $texto, $matches)) {
    echo "Teléfono encontrado: " . $matches[0] . "\n";
}

// Reemplazar usando regex
$textoOculto = preg_replace('/\d{3}-\d{3}-\d{4}/', 'XXX-XXX-XXXX', $texto);
echo "Texto con teléfono oculto: $textoOculto\n";

// Dividir usando regex
$frase = "palabra1,palabra2;palabra3 palabra4";
$palabras = preg_split('/[,; ]+/', $frase);
echo "\nPalabras separadas: " . implode(' | ', $palabras) . "\n";

// Validar formato
$emails = ['user@example.com', 'invalid-email', 'test@domain.co.uk'];
echo "\nValidación de emails:\n";
foreach ($emails as $email) {
    $valido = preg_match($patronEmail, $email) ? 'Válido' : 'Inválido';
    echo "$email: $valido\n";
}
```




    === EXPRESIONES REGULARES ===
    
    






    Texto original: Mi email es usuario@ejemplo.com y mi teléfono es 123-456-7890
    
    
    






    Email encontrado: usuario@ejemplo.com
    
    






    Teléfono encontrado: 123-456-7890
    
    






    Texto con teléfono oculto: Mi email es usuario@ejemplo.com y mi teléfono es XXX-XXX-XXXX
    
    






    
    Palabras separadas: palabra1 | palabra2 | palabra3 | palabra4
    
    






    
    Validación de emails:
    
    






    user@example.com: Válido
    
    






    invalid-email: Inválido
    
    






    test@domain.co.uk: Válido
    
    



## 14. JSON y APIs

PHP tiene excelente soporte para trabajar con JSON.


```PHP

echo "=== TRABAJANDO CON JSON ===\n";

// Crear datos PHP
$usuario = [
    'id' => 123,
    'nombre' => 'Ana García',
    'email' => 'ana@example.com',
    'activo' => true,
    'hobbies' => ['programar', 'leer', 'viajar'],
    'direccion' => [
        'calle' => 'Av. Principal 123',
        'ciudad' => 'Madrid',
        'pais' => 'España'
    ]
];

// Convertir a JSON
$json = json_encode($usuario, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
echo "JSON generado:\n$json\n\n";

// Convertir de JSON a PHP
$datosDecodificados = json_decode($json, true);
echo "Datos decodificados:\n";
echo "Nombre: " . $datosDecodificados['nombre'] . "\n";
echo "Ciudad: " . $datosDecodificados['direccion']['ciudad'] . "\n";
echo "Hobbies: " . implode(', ', $datosDecodificados['hobbies']) . "\n";

// Validar JSON
$jsonInvalido = '{"nombre": "Juan", "edad": }';
$resultado = json_decode($jsonInvalido);
if (json_last_error() !== JSON_ERROR_NONE) {
    echo "\nError en JSON: " . json_last_error_msg() . "\n";
}

// Crear respuesta API
$respuestaAPI = [
    'status' => 'success',
    'data' => $usuario,
    'timestamp' => date('c'),
    'version' => '1.0'
];

echo "\nRespuesta API:\n" . json_encode($respuestaAPI, JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE) . "\n";
```




    === TRABAJANDO CON JSON ===
    
    






    JSON generado:
    {
        "id": 123,
        "nombre": "Ana García",
        "email": "ana@example.com",
        "activo": true,
        "hobbies": [
            "programar",
            "leer",
            "viajar"
        ],
        "direccion": {
            "calle": "Av. Principal 123",
            "ciudad": "Madrid",
            "pais": "España"
        }
    }
    
    
    






    Datos decodificados:
    
    






    Nombre: Ana García
    
    






    Ciudad: Madrid
    
    






    Hobbies: programar, leer, viajar
    
    






    
    Error en JSON: Syntax error
    
    






    
    Respuesta API:
    {
        "status": "success",
        "data": {
            "id": 123,
            "nombre": "Ana García",
            "email": "ana@example.com",
            "activo": true,
            "hobbies": [
                "programar",
                "leer",
                "viajar"
            ],
            "direccion": {
                "calle": "Av. Principal 123",
                "ciudad": "Madrid",
                "pais": "España"
            }
        },
        "timestamp": "2025-10-25T23:45:46+00:00",
        "version": "1.0"
    }
    
    



## 15. Manejo de Errores

PHP 7 introduce mejoras significativas en el manejo de errores.


```PHP

echo "=== MANEJO DE ERRORES ===\n";

// Try-catch básico
try {
    $resultado = 10 / 0;
} catch (DivisionByZeroError $e) {
    echo "Error de división por cero: " . $e->getMessage() . "\n";
} catch (Exception $e) {
    echo "Error general: " . $e->getMessage() . "\n";
}

// Función personalizada con manejo de errores
function dividir($a, $b) {
    if ($b == 0) {
        throw new InvalidArgumentException("El divisor no puede ser cero");
    }
    return $a / $b;
}

// Usar la función con try-catch
try {
    echo "Resultado: " . dividir(10, 2) . "\n";
    echo "Resultado: " . dividir(10, 0) . "\n";
} catch (InvalidArgumentException $e) {
    echo "Error personalizado: " . $e->getMessage() . "\n";
}

// Finally (se ejecuta siempre)
try {
    echo "Intentando operación...\n";
    $archivo = fopen('archivo_inexistente.txt', 'r');
} catch (Exception $e) {
    echo "Error al abrir archivo\n";
} finally {
    echo "Bloque finally ejecutado\n";
}

// Múltiples excepciones (PHP 7.1+)
class MiExcepcionPersonalizada extends Exception {}

try {
    throw new MiExcepcionPersonalizada("Error personalizado");
} catch (InvalidArgumentException | MiExcepcionPersonalizada $e) {
    echo "Excepción capturada: " . $e->getMessage() . "\n";
}
```




    === MANEJO DE ERRORES ===
    
    






    Error general: PHP Warning:  Division by zero in C:\Users\eduar\AppData\Roaming\Composer\vendor\litipk\jupyter-php\src\Actions\ExecuteAction.php(115) : eval()'d code on line 4
    
    






    Resultado: 5
    
    






    Error personalizado: El divisor no puede ser cero
    
    






    Intentando operación...
    
    






    Error al abrir archivo
    
    






    Bloque finally ejecutado
    
    






    Excepción capturada: Error personalizado
    
    



## Conclusión

Esta documentación ha cubierto los conceptos fundamentales de PHP 7.2:

✅ **Configuración y verificación del sistema**  
✅ **Variables y tipos de datos**  
✅ **Constantes**  
✅ **Operadores**  
✅ **Estructuras de control**  
✅ **Bucles**  
✅ **Arrays y sus funciones**  
✅ **Funciones**  
✅ **Manejo de strings**  
✅ **Programación orientada a objetos**  
✅ **Manejo de fechas**  
✅ **Operaciones con archivos**  
✅ **Expresiones regulares**  
✅ **JSON y APIs**  
✅ **Manejo de errores**

**Entorno configurado:**
- PHP 7.2.34 Thread Safe ✓
- Extensión ZMQ habilitada ✓
- Jupyter Notebook funcional ✓



```PHP

```
