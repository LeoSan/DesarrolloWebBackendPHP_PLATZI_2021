¿PHP es el único lenguaje que mi computadora entiende?
No. PHP es uno de los múltiples lenguajes que mi computadora puede entender, aunque existen otros lenguajes con diferentes enfoques con los que también puedo programar.
2.
¿Cuál es la diferencia entre servidor físico y servidor web?
El servidor físico es una computadora que existe en el mundo real y que aloja mi página web, mientras que el servidor web es un programa que gestiona las solicitudes HTTP que llegan al servidor físico y se resuelven por medio de algún lenguaje de programación.
3.
¿Por qué deberías aprender a usar la terminal?
Porque me facilita el trabajo. Me ayuda a moverme más rápido a través de mi computadora, además de que puedo hacer pruebas rápidas en ella.
4.
¿Cuál de los siguientes es el código correcto para escribir un "Hola, Mundo" con PHP?
<?php

echo "Hola, Mundo"; 
5.
¿Cuál es la diferencia entre usar comillas simples o comillas dobles en PHP?
Si uso comillas dobles, entonces puedo poner variables dentro de mi string y PHP podrá interpretarlas. En cambio, si uso comillas simples, PHP no podrá interpretarlas y me escribirá directamente la variable.
6.
Quiero debuggear una variable, pero quiero tener toda la información posible de esa variable. ¿Cuál función de debugging debería usar?
var_dump()

7.
Quiero debuggear una variable, pero solo me interesa tener ciertos datos relevantes, así que quiero que la información se presente lo más limpia posible. ¿Cuál función de debugging debería usar?
print_r()

8.
En pocas palabras, ¿qué es una variable?
Es una palabra que me permite guardar cualquier cosa dentro de ella y cuando yo quiera puedo cambiar eso que guardé allí.
9.
En pocas palabras, ¿qué es una constante?
Es una palabra que me permite guardar cualquier cosa dentro de ella, pero una vez guardado ya no puedo cambiar eso que guardé.
10.
¿Qué tipo de dato debería usar si quiero guardar la edad de una persona?
int
11.
Una abuelita quiere repartir $5 dólares entre sus dos nietos. ¿Qué tipo de dato debería usar para saber cuánto le tocará a cada nieto?
float
12.
¿De qué tipo de operadores estamos hablando si tengo dos sentencias que están siendo evaluadas por un operador "AND" o un operador "OR"?
Lógicos
13.
¿Cuál de los siguientes enunciados describe mejor a la operación "OR"?
Mi condición será verdadera si POR LO MENOS UNA de las dos sentencias es VERDADERA. Si ambas son falsas, entonces toda mi condición será falsa.
14.
¿Cuál es el operador que usamos en PHP para expresar exponenciación?
**
15.
¿Cuál de los siguientes es un operador relacional?
&&
REPASAR CLASE
16.
¿Con cuál de las siguientes expresiones puedo sumarle 1 al valor actual de mi variable?
$a++
17.
¿Cuál sería el resultado de ejecutar esta expresión en PHP?

$michis_toman_agua = true;
$michis_ladran = false;

$resultado = $michis_toman_agua and $michis_ladran;

var_dump($resultado);
false
REPASAR CLASE
18.
¿Qué es la precedencia en un lenguaje de programación?
Es la forma en la que un lenguaje decide qué operación se debe ejecutar primero y qué operación se debe ejecutar después.
19.
Si quisiera obtener únicamente el número entero de un número que tiene decimales en PHP, ¿qué operación debería hacer?
<?php

$numero_decimal = 28.56;
$numero_entero = (int) $numero_decimal;

echo $numero_entero; 
20.
¿Es obligatoria la etiqueta de cierre (?>) de PHP?

Es obligatoria únicamente si combinamos PHP con HTML. Si únicamente trabajamos con PHP, entonces no es obligatoria.
