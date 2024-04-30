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
Es un programa que nos permite hacer instalaciones complejas y largas de manera manual.
Es interfaz de línea de comandos.
REPASAR CLASE
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
REPASAR CLASE
7.
¿Qué gestor de plantillas usamos en Symfony?
Twig
8.
Poderosa herramienta que brinda información detallada sobre cualquier solicitud:
Función dd()
Página 404
REPASAR CLASE
9.
¿Cómo instalamos al sistema de bases de datos?
Agregando use Doctrine\ORM\EntityManagerInterface; en el controlador adecuado.
php bin/console doctrine:migrations:migrate

POSIBLE -> php bin/console doctrine:database:create 
REPASAR CLASE
10.
¿Con qué comando creamos una entidad?
php bin/console make:entity
11.
¿Qué es una migración?
Es la estructura inicial de una tabla.
12.
¿Qué método del repositorio usamos para obtener todos los registros de una tabla?
findAll()
13.
¿Cómo instalamos al sistema de formularios?
composer require symfony/form
14.
¿Cómo validamos a un formulario desde el controlador?
$form->isValid()
15.
Función para leer archivos CSS generados por encore:
Con 'bootstrap_5_layout.html.twig' en el archivo de configuración en Twig.
Mediante el bloque stylesheets en la vista base.
REPASAR CLASE
