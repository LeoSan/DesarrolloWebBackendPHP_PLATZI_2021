Resumen
1.
¿Puedo usar cookies sin notificarle al usuario?
No. Siempre hay que tener un aviso de cookies para que el usuario esté consciente de la información que estamos almacenando.

2.
¿Cómo podría obtener el valor de la cookie llamada "color"?
$_COOKIE["color"];

3.
¿Qué debo tener en cuenta cuando trabajo con sesiones?
Siempre debo escribir la función `session_start()`al inicio de mi código cuando necesite hacer uso de sesiones, incluso para cerrar sesión.

4.
¿Cómo puedo acceder al id de una sesión que ya fue definido previamente?
$_SESSION["id"];

5.
¿Con cuál función podemos finalizar una sesión?
session_destroy();

6.
¿Para qué nos sirven las excepciones?
Para "atrapar" cualquier error que pueda surgir en tiempo de ejecución y poder controlar qué hacer en ese caso.

7.
¿Cómo puedo crear mis propias excepciones personalizadas en PHP?
Extendiendo la clase base Exception de PHP.

8.¿Puedo atrapar distintas excepciones en un mismo bloque de código?
Verdadero. Puedo poner varios bloques catch en los cuales, por medio de la clase de la excepción, puedo indicar cuál atrapar.

9.
¿Hay diferencia en el resultado final del cálculo de una fecha si usamos programación estructurada o programación orientada a objetos?
No, ya que de ambas formas conseguimos el mismo resultado, simplemente cambia la forma de trabajar.

10.
¿Cuál función me permite añadir y quitar días a una fecha de forma dinámica?
date_modify

11.
¿Qué son los Namespaces?
Son una forma que tenemos de darle un "apellido" a nuestras clases y funciones, ya que permiten generar diferentes entornos en donde una clase puede vivir.

12.
¿Qué me permite hacer la sección "PSR-4" dentro de Composer?
Me permite definir una forma fácil de autoimportar mis clases de PHP siempre y cuando siga las convenciones establecidas por PSR-4.

13.
Si tengo una clase `Perro` y una clase `Gato`, y ambas tienen un método llamado `jugar()` que tiene el mismo comportamiento para ambas clases... ¿qué feature de PHP debería usar para declarar dicho método?
Polimorfismo
Métodos mágicos
REPASAR CLASE


15.
¿Qué son los traits?
Son una alternativa a la herencia en PHP. Permite definir métodos que pueden ser compartidos o reutilizados por varias clases.

16.
¿Cuál de las siguientes funciones daría un Fatal Error en caso de que no encuentre el archivo a importar?
require()

17. ¿Qué son las sesiones?
 Son pedacitos de información que se guardan en la memoria de la computadora del usuario para personalizar su experiencia en un sitio web.
Repasar


19. ¿Cuál estructura nos permite manejar excepciones en PHP?
try/catch

20.   ¿Por qué es importante modularizar el código?
Porque nos permite dividir el problema en pequeños pedacitos a su vez que hará un código más fácil de leer y mantener.

22. ¿Cuál función de PHP nos permite formatear cualquier fecha?
``` date(); ```


24. ¿Cómo podría definir una cookie que solo esté disponible en `https://dominio.com/profile`?
setcookie( name: "my_cookie", value: "I will approve this exam!", path: "midominio.com/profile/", );
Repasar

