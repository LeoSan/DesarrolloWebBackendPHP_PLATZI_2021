## Curso de Fundamentos de Symfony 6

**Notas** 
- En Syn podemos crear 4 tipos de proyectos
- Smple -> no usa front ya que es usado para api o microservicios 
- Demo -> es un sistema funcional se usa para ejemplo
- weeapp -> es el mas usado ya que puedes integrar front
- full -> Esta ya esta obsoleto
- usa plantillas twing


## Examen 

Curso de Fundamentos de Symfony 6

Resumen
1.
Beneficios de trabajar con Symfony:
Buenas prácticas, mantenimiento y comunidad profesional.

2.
¿Qué es un CLI?
Instrucciones organizadas que nos permiten automatizar funciones complejas o largas mediante un texto simple.

3.
¿Con qué comando instalamos un sitio web en Symfony?
symfony new project --webapp

4.
¿Cómo crecemos en el mundo de la programación?
Estudiando cursos como este para aprender a leer código construido por personas técnicamente avanzadas.

5.
Carpeta src/
Tiene dentro de sí todas nuestras clases PHP.

6.
¿Qué es una página?
Es el resultado de ruta + controlador.

8.
¿Qué gestor de plantillas usamos en Symfony?
Twig

9.
Poderosa herramienta que brinda información detallada sobre cualquier solicitud:
Symfony profiler
POSIBLE  -> composer require symfony/debug-pack


11.
¿Cómo instalamos al sistema de bases de datos?
composer require symfony/orm-pack

12.
¿Con qué comando creamos una entidad?
php bin/console make:entity

13.
¿Qué es una migración?
Es la estructura inicial de una tabla.

14.
¿Qué método del repositorio usamos para obtener todos los registros de una tabla?
findAll()

15.
¿Cómo instalamos al sistema de formularios?
composer require symfony/form

16.
¿Cómo validamos a un formulario desde el controlador?
$form->isValid()

17.
Función para leer archivos CSS generados por encore:
encore_entry_link_tags

18. ¿Cómo instalamos al sistema front en Symfony?
composer require symfony/webpack-encore
Con npm o yarn.
REPASAR CLASE 

20. 


## Curso de Symfony 6: Formularios

##Notas
- 

## Examen 

1.
Comando de instalación de un proyecto sencillo
symfony new project

2.
Comando de instalación del componente form
composer require symfony/form

3.
Método para crear un formulario desde el controlador
createFormBuilder()

4.
Método para conocer si un formulario fue enviado
isSubmitted()

5.
Comando para crear un formulario
php bin/console make:form

6.
Función para imprimir una colección de campos en la vista
form_widget()

7.
Cómo aplicamos un tema de formulario directamente en una vista
{% form_theme form 'example.html.twig' %}

8.
Cómo creamos un mensaje flash
Con el método addFlash()

9.
Con qué elementos identificamos a nuestras vistas parciales
Guion bajo ( _ )

10.
Cómo relacionamos a un formulario con una entidad
Lo hacemos en el método configureOptions() de la clase del formulario

11.
Con qué comando instalamos el componente de seguridad CSRF
composer require symfony/security-csrf

12.
Qué clase usamos para crear un select
La clase ChoiceType

13.
Con qué comando actualizamos a una entidad
Mediante el comando php bin/console make:controller
Esta configuración únicamente es posible al crear la entidad
Repasar

14.
Qué clase usamos para crear un select relacionado a una tabla
EntityType

15.
Qué métodos usamos para guardar
persist() y flush()

16.
Qué método es obligatorio al momento de actualizar
flush()

18.
Cómo desactivamos la validación HTML
Con la opción required y el valor false

19.
Método para validar un formulario desde un controlador
isValid()

20.
Con qué comando creamos a un controlador
php bin/console make:controller

21.
Qué importamos en una entidad para validar
use Symfony\Component\Validator\Constraints as Assert;
