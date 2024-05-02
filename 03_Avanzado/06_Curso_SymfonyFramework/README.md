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
Es el resultado de cualquier método o acción del controlador PageController.
Es un concepto abstracto de la programación web.
REPASAR CLASE

8.
¿Qué gestor de plantillas usamos en Symfony?
Twig

9.
Poderosa herramienta que brinda información detallada sobre cualquier solicitud:
Función dd()
Página 404
POSIBLE  -> composer require symfony/debug-pack
Debug Symfony Start
REPASAR CLASE

10.
¿Cómo instalamos al sistema de bases de datos?
composer require symfony/orm-pack

11.
¿Con qué comando creamos una entidad?
php bin/console make:entity

12.
¿Qué es una migración?
Es la estructura inicial de una tabla.

13.
¿Qué método del repositorio usamos para obtener todos los registros de una tabla?
findAll()

14.
¿Cómo instalamos al sistema de formularios?
composer require symfony/form

15.
¿Cómo validamos a un formulario desde el controlador?
$form->isValid()

16.
Función para leer archivos CSS generados por encore:
encore_entry_link_tags

17. ¿Cómo instalamos al sistema front en Symfony?
composer require symfony/webpack-encore

19. 
