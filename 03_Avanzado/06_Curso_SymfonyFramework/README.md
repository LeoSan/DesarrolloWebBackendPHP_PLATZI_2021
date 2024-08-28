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



# Curso de Symfony 6: Creación de API REST

1.
¿Cómo se llama la especificación para describir y documentar un API?
Swagger UI
Es una especificación propia.
Repasar

3.
¿Cómo se llama la herramienta que permite visualizar y probar un API basada en OpenAPI?
Swagger UI

4.
¿Qué instalamos en Symfony para que este tenga las funciones de un API?
composer require api-platform/api-pack

5.
¿Con qué comando creamos a la base de datos?
$ php bin/console doctrine:database:create

6.
¿Con qué comando creamos a las tablas en la base de datos?
$ php bin/console doctrine:migrations:migrate

7.
¿Cómo se llama el archivo donde creamos la conexión a la base de datos?
.env

8.
¿Qué componente debemos instalar para trabajar con los factories?
$ composer require zenstruck/factory --dev
$ composer require zenstruck/foundry
Repasar

10.
¿Qué componente debemos instalar para trabajar con los datos semillas?
$ composer require orm-fixtures --dev

11.
¿Cómo se llama el archivo donde configuramos a nuestros datos semillas?
AppFixtures.php

12.
¿Con qué comando creamos a nuestros datos semillas?
$ php bin/console doctrine:fixtures:load

13.
¿Cómo se llama nuestra documentación interactiva?
Swagger UI

14.
¿Qué clase debemos importar para que nuestra entidad sea un recurso API?
use ApiPlatform\Metadata\ApiResource;

15.
¿Qué anotación debemos agregar a nuestra entidad para que sea un recurso API?
#[ApiResource]

16.
¿Qué estado HTTP recibimos cuando se crea un registro?
201

17.
¿Qué estado HTTP recibimos cuando se elimina un registro?
204

18.
¿Qué parámetro debemos configurar para trabajar con la serialización de datos en API Platform?
normalizationContext

19.
¿Con qué clase debemos trabajar para configurar la validación de datos?
use Symfony\Component\Validator\Constraints as Assert;

20.
¿Con qué anotación impedimos que un campo esté en blanco?
#[Assert\NotBlank]

21.
¿Con qué parámetro definimos el número máximo de elementos por página en API Platform?
paginationItemsPerPage

22.
¿Qué clase debemos importar para poder configurar el filtrado?
use ApiPlatform\Metadata\ApiFilter;

23.
¿Cómo se identifican nuestros recursos de forma única y global?
Mediante IRI (Internationalized Resource Identifier).

24.
¿Qué herramienta podemos usar para probar y enviar peticiones a un API?
Postman

## Curso de Bases de Datos en Symfony

1.
¿Cuál es el comando de creación o actualización de entidades?
php bin/console make:entity y php bin/console edit:entity
Repasar


2.
¿Cuál es el comando para revisar a nuestras migraciones?
php bin/console doctrine:migrations:list


3.
¿Cuál es el tipo de campo para relacionar tablas?
Existen varios tipos
ManyRelations
Repasar

4.
¿Cuantas estructuras físicas podemos crear al momento de relacionar tablas?
1
4
Repasar


5.
¿Cuál es el comando para cargar datos falsos a la base de datos?
php bin/console doctrine:fixtures:load


6.
¿Cuál es el comando de creación de factories?
php bin/console make:factory

7.
¿Cuál es la función de la clase AppFixtures?
Esta clase no existe
Crear los moldes de datos de cada tabla
Repasar


8.
¿Cuál es el componente para habilitar las vistas en Symfony?
composer require symfony/twig-pack


9.
¿Cómo se llama la vista que funciona como plantilla?
layouts
_base.html.twig
Repasar


10.
¿Cuál es el Método para listar a todos los registros de una tabla?
findAll()

11.
¿Cómo podemos crear controladores más concisos?
Instalando el paquete de depuración e inspección
Creando únicamente los métodos CRUD
Repasar

12.
¿Qué quiere decir esta línea: product.metadata.code?
Desde product se está accediendo a la relación metadata, esta última cuenta con un campo llamado code


13.
¿Qué entendemos por refactorizar (Refactoring)?
Cambio interno para mejorar la lectura del código y sea más fácil el mantenimiento futuro


14.
¿Qué parámetro acepta el método createQuery?
DQL

15.
¿Cómo podemos ver el DQL generado al usar createQueryBuilder?
getSQL()
Repasar

16.
¿Cuál es la función de LEFT JOIN?
Devolver todas las filas de la tabla de la izquierda y las coincidencias de la tabla de la derecha


17.
¿Con qué método damos de alta a un parámetro en una consulta?
Escribiendo :parameter al usar el método andWhere

Repasar


18.
¿Qué clase maneja las peticiones o solicitudes web?
Request


19.
¿Qué usamos normalmente para consultar una tabla?
Una entidad
Código SQL en el controlador
Repasar


21.
¿Cómo podemos ver el listado de comandos?
php bin/console


