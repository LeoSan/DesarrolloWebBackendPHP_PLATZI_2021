# Curso de Manejo de Datos en PHP

## Comillas

> Comillas simples
- Para manejar datos strings con comillas simples. 
- Si queremos utilizar una comilla simple dentro de nuestro string utilizamos \ (backslash) para escaparla y no nos de error.

> Comillas dobles
- Si queremos acceder a una variable utilizamos comillas dobles. 
- También podemos acceder a una variable con comillas simples, pero tiene que estar fuera de la comillas simples.


> Datos complejos (Comillas dobles)

- Para acceder a datos complejos como un objeto o un array con varios niveles necesitamos utilizar {} (llaves) que encierren a la variable con los parámetros que indicamos.

- Se puede dar el caso de cuando es un objeto, y este solo tiene un nivel en su parámetro accedemos sin utilizar {} (llaves) y para indicar el key ponemos →, ej: $hora→segundos

> Variables variables
- necesitamos utilizar las variables variables, lo hocemos añadiendo $ antes de las {} (llaves) para que búsque la variable variable.

- La variable variable debe tener exactamente el mismo nombre que el dato que tiene la variable principal, deben coincidir tanto en lo que dice como si está en mayúscula o no.

- También para hacer más legible el código podemos encerrar esta llamada a una variable dentro de otra {} (llaves). Ej: {${getLove()}}

## Extracción de datos


- De un String

Podemos extraer un dato de un String por medio de [] o {} accediendo a su indice:

```
$data = 'Estudio PHP';

echo $data{3};
```
- De un String o párrafo muy largo
```
$lorem = "lorem ipsum ...";

$extrac = subsrt($lorem, iInicial, iFinal);

echo "$extrac ... [ver más]
```
- De String a Array

Con explode() podemos separar los elementos contenidos en un String o array
```
$data = 'javascript, php, laravel';

$tags = explode(', ',$data);

echo "<pre>";

var_dump($tags);
```
- De Array a String

Contrario a explode() usamos implode()
```
$courses = ['javascript', 'php', 'laravel'];

echo implode(', ',$courses);
```
- Limpieza de espacios innecesarios (inicio y final)

Se logra con trim($variable)
```
$course = "   Curso de PHP   ";
// ltrim($course) o rtrim($course).
$course = trim($course);
echo "<prev>";
echo "Quiero aprender $course, y otro curso.";
```

## Formato de datos

Posiblemente nos encontremos en situaciones dónde queremos guardar los datos en la DB con un formato, pero a la hora de presentarlos necesitaremos que se vean diferentes, para esto vamos a alterar, reemplazar o modificar los datos.

```
<?php

// Alterar a minúscula
$text1 = "PHP es UN LENGUAJE";
echo strtolower($text1);

// Alterar a mayúscula
$text2 = "PHP es UN LENGUAJE";
echo strtoupper($text2);

// Alterar a mayúscula solo el primer carácter
$text3 = "PHP es UN LENGUAJE";
$textLower = strtolower($text3);
echo ucfirst($textLower);

// Alterar a minúscula solo el primer carácter
$text4 = "PHP es UN LENGUAJE";
$textUpper = strtoupper($text4);
echo lcfirst($textUpper);

// Reemplazar
$textLower2 = strtolower($text1);
$slug = str_replace(' ','-', $textLower2);
echo $slug;

$slug2 = str_replace('php','ruby', $textLower2);
echo $slug2;

// Modificación
$code = 39;
// colocar hacia STR_PAD_BOTH, STR_PAD_LEFT & STR_PAD_RIGHT
echo str_pad($code, 8, '#', STR_PAD_BOTH);

// Es una mala práctiva guardar código html en nuestra DB
$textHTML = "<h3>PHP es UN LENGUAJE</h3>";
echo $textHTML;
// Para quitarlas utilizamos strip_tags()
echo strip_tags($textHTML);

//Elementos monobyte y multubyte  Ejemplo 
$textHTML = "PHP es UN LENGUAJE de programación año 2020";
echo strtoupper($textHTML); // monobyte 
echo mb_strtoupper($textHTML); // multibyte 

```

## Expresiones regulares


- / → Es un contenedor. Este inicia y finaliza.
- ^ → Dentro del contenedor tenemos esta expresión que nos indica un inicio.
- $ → Cuando finalicemos utilizamos esta exprseión.
- ‘-’ (rayita 😃 ) → Nos sirve para especificar rangos.
- [ ] → Este es para especificar un patrón.
- {} → Este nos sirve para establecer condición.

**Enlaces**
- https://regex101.com/ 

```
$psswrd = '123456';
//echo preg_match('/^$/', $psswrd); // Es nuestra estructura base 
//echo preg_match('/^[0-9]{6,9}$/', $psswrd);
var_dump((bool) preg_match('/^[0-9]{6,9}$/', $psswrd));

```


Lo primero que hacemos es requerir phpunit para el desarrollo

composer require --dev phpunit/phpunit
Luego de eso, modificamos el archivo composer.json y le agregamos un nombre, despcripcion y configuramos el autoload

{
    "name": "matias-ed/validate",
    "description": "proyecto de validacion",
    "autoload": {
        "psr-4": {
            "App\\": "src/"
        }
    },
    "require-dev": {
        "phpunit/phpunit": "^9.5"
    }
}

## Iniciando nuestro proyecto

- Paso 1: Lo primero que hacemos es requerir phpunit para el desarrollo

`composer require --dev phpunit/phpunit`

- Paso 2: Luego de eso, modificamos el archivo composer.json y le agregamos un nombre, despcripcion y configuramos el autoload
```
{
    "name": "matias-ed/validate",
    "description": "proyecto de validacion",
    "autoload": {
        "psr-4": {
            "App\\": "src/"
        }
    },
    "require-dev": {
        "phpunit/phpunit": "^9.5"
    }
}
```

- Paso 3: Creamos el archivo phpunit.xml donde especificamos en que carpeta se encuentran nuestros tests

```
<?xml version="1.0" encoding="UTF-8"?>
<phpunit bootstrap="vendor/autoload.php" colors="true">
    <testsuite name="Test directory">
        <directory>tests</directory> 
    </testsuite>
</phpunit>
```
- Paso 4:  Creamos la carpeta tests y dentro de ella creamos el archivo ValidateTest.php
Nota: Es buena practica que los archivos de testing terminen en Test

```
    <?php

    use PHPUnit\Framework\TestCase;
    use App\Validate;

    class ValidateTest extends TestCase
    //TestCase es una clase de PHPUnit
    {
        public function test_email()
        {
            $email = Validate::email("matdj31@gmail.com");
            //aqui llamamos al metodo email de la clase Validate que aun no hemos creado

            $this->assertTrue($email);
            //Es un metodo de TestCase
        }
    }
```

- Paso 5: Por ultimo creamos nuestra carpeta src/ y adentro creamos nuestra clase Validate
```
    namespace App;

    class Validate
    {
        public static function email($value)
        {
            return (bool) filter_var($value, FILTER_VALIDATE_EMAIL);
        }
    }
    //filter_var es una funcion propia de php que me permite filtrar a mis variables
    //FILTER_VALIDATE_EMAIL es una constante propia de PHP

```

## Revisando nuestro proyecto

## Argumentos
Un argumento es lo que colocamos adentro de los paréntesis, este puede ser un valor de forma directa o un parámetro.

Las referencias apunta u observa el comportamiento de otro elemento.

### Tipos Argumentos de PHP
- Por Valores -> Nosotros colocamos directamente una vraible esperando que eso se cumpla. 
- Por Referencia -> Nosotros usamos el simbolode (&$Valor) para decirle al interprete que cambien el valor tanto externos como interno de la variable
- Predeterminado -> Asignamos de manera fija un elemento o un valor, podemos tener la opcion de alterar ese valor colocandole un parametro

```
<?php

// valores
function saludo($name)
{
    echo "Hola, $name";
}

saludo('Angél');

// refrencias
$co = 'PHP';
# si queremos que el resultado de la función modifique
# la variable externa, tenemos que poner path(&$co)
function path($co)
{
    $co = 'Laravel';
    echo $co;
}

path($co);
echo $co;

// predeterminado
function saludos($name = 'Pikachu')
{
    echo "Hola, $name";
}

saludos();
```
## Return 

La palabra reservada return siempre va ha estar dentro de una función, nos ayuda retornar.

Es una mala práctica no retornar nada de una función y hacer que esta se imprima cuando la llamemos.

```
<?php
function saludo()
{
    return "Hola...";
}

echo saludo();

#no es recomendado hacer esto
function saludos()
{
    return "Hola...";
    return "Hola 2...";
}

# Retornar mas de un elemento siempre es con arrays 
function  mutltuplesElementos(){

    return ['Vista', 'Vista2',  'Vista3'];
}

var_dump( mutltuplesElementos() );

```


## Closure
Una función anónima se usa en una variable que requiere lógica.

Al pasarle a una función el parámetro Closure le indica que va ha recibir una función anónimas. Si no colocamos el closure la función va a servir igual, pero puede que se puedan dar muchos tipos de error a futuro, así que es una buena práctica ponerlo.


 ```
<?php

$greet = function ($name)
{
    return "Hola, $name";
};

echo $greet('Kato'); 
 ```


Al pasarle a una función el parámetro Closure le indica que va ha recibir una función anónimas. Si no colocamos el closure la función va a servir igual, pero puede que se puedan dar muchos tipos de error a futuro, así que es una buena práctica ponerlo.

```
<?php

$greet = function ($name)
{
    return "Hola, $name";
};

echo $greet('Kato');

function greet2(Closure $lang, $name)
{
    return $lang($name);
}

$es = function ($name)
{
    return "Hola, $name";
};

$en = function ($name)
{
    return "Hello $name";
};

echo greet2($es, 'fea (its a joke, EDN)');
echo greet2($en, 'Leo');



## Mas Esjemplos 

<?php

function operacionMatematica(Closure $operation, $num1, $num2)
{
    return $operation($num1, $num2);
}

$suma = function ($num1, $num2)
{
    return $num1 + $num2;
};

$resta = function ($num1, $num2)
{
    return $num1 - $num2;
};

$multiplicacion = function ($num1, $num2)
{
    return $num1 * $num2;
};

$division = function ($num1, $num2)
{
    if( $num2!=0 ){
        return $num1 / $num2;
    }
    return "operación no permitida, divisor no puede ser igual a cero";
};

//escribir en el primer parámetro el nombre de la función anónima
echo operacionMatematica($suma, 65, 15);
```
## Array simple

Los datos de los Arrays son datos complejos por que nos permiten guardar varios datos dentro de una sola variable. Declaramos un array de la siguiente forma:

Recuerda que un array simple es aquel al cual no le hemos definido ninguna llave. Estamos hablando de los valores directamente.


```
<?php

$courses = ['JS', 'Sass', 'PHP', 'Ruby'];

echo "<prev>";
var_dump($courses);

echo "<prev>";
echo "Me gusta {$courses[3]} y {$courses[2]}.";

$courses2 = [
    'JS', 
    'Sass',
    8 =>'PHP',
    'Ruby'
];

echo "<prev>";
var_dump($courses2);

```

## Array complejo
Los datos de los Arrays son datos complejos por que nos permiten guardar varios datos dentro de una sola variable. Declaramos un array de la siguiente forma:


- array_walk(‘key’, $array); → Nos ayuda a aplicar una función que le pasemos a cada miembro del array, es - muy parecido a .maps() o .each() en JS o Ruby.
- array_key_exists(‘key’, $array); → Para saber si un key existe.
- in_array(‘valor’, $array); → Nos ayuda a buscar si existe un valor en el Array.
- array_keys($array); → Nos imprime todos los keys en pantalla.
- array_values($array); → Nos imprime todos los valores en pantalla.

```
<?php

$courses = [
    'frontend' => 'JS', 
    'framework' => 'laravel',
    'backend' => 'php'
];

foreach ($courses as $key => $var) {
    echo "<h4> $key: $var <br><h4>";
}

function upper($course, $key)
{
    echo ucfirst($course) . "=> $key <br>";
}

array_walk($courses, 'upper');

```


## Funciones PHP para arrays

- sort($courses) → Ordena de forma alfabética.
- rsort($courses) → Ordena de forma alfabética pero en descendente.
- ksort($courses) → Ordena por la key.
- krsort($courses) → Ordena por la key pero en descendente.
- array_slice() → Nos deja quitar elementos del array.
- array_chunk() → Nos deja tomar diferentes pedazos de datos y los convierte en Arrays individuales.
- array_shift() → Nos retorna el primer valor y lo elimina del array.
- array_pop() → Nos retorna el último valor y lo elimina del array.
- array_unshift() → Agrega nuevos valores al array.
- array_push() → Inserta uno o más valores al final de un array.
- array_flip() → Nos deja intercambiar los keys por los valores y viceversa.

## Comparación

Comparación entre arreglos son mecanismos que nos ayudan en salir en esos apuros entre comparación de arreglos, con la función array_diff() nos muestra las diferencias entre dos Arrays, los valores que son diferentes son los que va a imprimir. Es importante estar pendiente que orden la pones. Si necesitamos hacerlo con los arrays complejos tenemos la función array_diff_assoc().


```
<?php

$courses = [
    'php',
    'javascript',
];

$wishes = [
    'php',
    'laravel',
    'javascript',
    'react.js'
];

var_dump(array_diff($wishes,$courses));

```

## Unión

Podemos unir diferentes Arrays mediante la siguientes formas:
```
<?php

$frontend = [
    'html',
    'javascript',
    'react.js'
];

$backend = [
    'php',
    'laravel'    
];

$frontend2 = [
    'structure' => 'html',
    'frontend' => 'javascript',
    'framework' => 'react.js'
];

$backend2 = [
    'backend' => 'php',
    'framework bk' => 'laravel'    
];
// Podemos unir dos arryas así, pero terminaría borrando algunos valores. Sí
// queremos evitarlo debemos poner keys
var_dump($frontend + $backend);
var_dump($frontend2 + $backend2);

// Podemos usar una función también, pero solo con aquellos que tengan keys númericos
var_dump(array_merge($frontend, $backend));

// Si nuestros keys son letras debemos usar la siguiente función
var_dump(array_merge_recursive($frontend2, $backend2));

// Y si queremos combinar dos arrays,así creamos arrays complejos y lo hacemos con la función array_combine
$cursos = ['JS', 'php', 'laravel'];
$categorias = ['front', 'back', 'framework'];

var_dump(array_combine($cursos, $categorias));

```


Bikatti