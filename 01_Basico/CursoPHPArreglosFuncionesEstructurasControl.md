# Curso de PHP: Arreglos, Funciones y Estructuras de Control

Resumen
1.
Necesito guardar una lista de productos con sus respectivos precios. ¿Cuál estructura me permite hacer esto en PHP?
Arreglos

2.
Dado el siguiente arreglo:

$personas = ["Pedro", "Carlos", "Juanito", "Damián"]; 
¿Cómo puedo obtener a Juanito?
$personas[2];

3.
Una buena forma de ver a los arreglos asociativos es como...
Listas que pueden contener información de cualquier cosa.

4.
¿Qué sucede cuando no usamos la palabra reservada `break;` dentro de un caso en la estructura switch/case?
Se seguirán ejecutando los demás casos hasta que termine o hasta que se encuentre con un `break;`.

5.
¿Es obligatorio siempre poner un caso default en la estructura switch/case?
Falso, el caso por defecto es opcional.

6.
¿Qué sucede si ponemos un `while(true)`?
El ciclo se repetirá de forma infinita, consumiendo recursos de mi computadora hasta que pare el programa manualmente.

7.
Este ciclo se conoce porque es un ciclo indefinido. Su principal característica es que el código se ejecuta por lo menos una vez, ya después la condición determinará si el ciclo se vuelve a ejecutar o no.
do... while

8.
Este ciclo es capaz de recorrer cada elemento de un arreglo sin necesidad de decirle cuántos elementos tiene:
foreach

9.
¿Cómo podemos visualizar a las funciones?
Como cajas mágicas a las cuales les damos ciertos datos y nos devuelven el resultado que estamos esperando.

*** 10.
¿De qué forma puedo combinar dos arrays en PHP?
$array_resultante = array_combine($array1, $array2);
REPASAR CLASE

***11.
¿Para qué me sirven los parámetros en las funciones de PHP?
Es la forma que tengo para definir variables iniciales dentro de mi función.
REPASAR CLASE


12.
¿Cómo programarías una función para multiplicar dos números, pero que el segundo número por defecto es 1?
<?php
function multiplicar($numero1, $numero2 = 1) {
    return $numero1 * $numero2;
}

13.
¿Es obligatorio usar las etiquetas de cierre de PHP cuando trabajamos con HTML?
Verdadero, así PHP puede reconocer qué porción del código pertenece a HTML y cuál pertenece a PHP.

14.
¿Es posible utilizar las estructuras de control de PHP cuando trabajamos con HTML?
Verdadero. Basta con poner las etiquetas de apertura y cierre de PHP para empezar a usar dichas estructuras.

15.
Cuando trabajamos con HTML dentro de PHP, ¿qué extensión debería tener mi archivo?
.php

16.
¿Para qué me sirve una variable contadora dentro de un ciclo?
Para llevar la cuenta de cuántas iteraciones ha tenido mi ciclo y poder definir condicionales con ella.

17.
Si necesito recorrer cada elemento de un arreglo, ¿cuál es el ciclo que me permite hacer dicho recorrido de la forma más fácil?
foreach

***18.
¿Puedo declarar dos variables contadoras dentro de un ciclo for?
Falso. El ciclo for solo admite una variable contadora, si quieres otra debes declararla manualmente dentro de su bloque de código.
REPASAR CLASE

19.
Si quiero saltarme una iteración de un ciclo para pasar a la siguiente de forma manual, ¿qué palabra reservada debería usar?
continue;

20.
Si quiero detener un ciclo manualmente sin importar si finalizó adecuadamente, ¿qué palabra reservada debería usar?
break;
