# Curso_avanzado_php

## IDEs

- Durante tu vida como desarrollador, escucharás el término de IDE que significa Entorno de desarrollo integrado. 
- El término de editor de código fuente. 
- La principal diferencia entre estos dos es que un IDE normalmente cuenta con más características como herramientas para administrar bases de datos, controlador de versiones (Git), debug o depuración y al tiempo incluye un editor de código fuente.
- Es importante que sepas que tu IDE será una herramienta que usarás día a día así que debes conocerla muy bien y sentirte cómodo con ella. 
- Explora sus atajos y ventajas frente a otras herramientas.

## Enlace Referencias 
- https://rimorsoft.com/ 


## Virtualización con Vagrant


> Nota: Existen dos vertientes principales: Vagrant y Docker. 
- Vagrant genera máquinas virtuales completas en las cuales podemos instalar PHP, bases de datos, Apache, entre otras. 
- La otra vertiente es Docker con la cual se generan pequeños contenedores dentro de una máquina virtual los cuales contienen la instalación de PHP o la base de datos, logrando que trabajen en conjunto.
- Podemos descargar Vagrant https://www.vagrantup.com/
- Utilizaremos la imagen de Laravel Homestead siguiendo los pasos que aquí se describen: https://laravel.com/docs/5.7/homestead. Las imágenes de Vagrant las llamaremos box o cajas, Homestead es una de ellas.

> Notas para Homestead
- Cuando inicializamos Homestead, lo que hacemos es crear un nuevo archivo de configuración “Homestead.yaml”.
- Al editar el archivo “Homestead.yaml”, tenemos información de la ip que no es el localhost por ser máquina virtual. Aquí igualmente ligamos nuestra carpeta de proyecto a la carpeta de la máquina virtual; también podemos añadir bases de datos y diferentes proyectos dentro de la misma máquina o box.
- Cuando usas el comando “vagrant up” se creará una máquina virtual vagrant si no existe; si existe se reiniciará la máquina existente. Se ejecutará también el aprovisionamiento que es configurar o instalar cualquier cosa que se necesite.

## Enlaces 

- https://www.vagrantup.com/
- https://www.docker.com/
- https://laravel.com/docs/5.7/homestead



> Notas  Problemas al iniciar  

``` 
- Si les genera error al ejecutar init.bat.
- bash: init.bat: command not found![](Captura.PNG

**Solucion:**
No ejecutes eso en git bash. Ejecútelo en la línea de comando de Windows. O mejor aún, simplemente haga doble clic init.baty lo ejecutará en relación con su directorio de inicio de Windows.
fuente: [(https://stackoverflow.com/questions/42775652/homestead-nor-homestead-yaml-is-showing-up-after-running-bash-init-bat)]
```

## Datos para configuración 

```
Para los que han tenido problemas de configuracion como yo prueben lo siguiente:

Tienen que tener su llave ssh creada y especificar bien la ruta en Homestead.yaml
Verificar la ruta de folder y site es SUPER IMPORTANTE en Homestead.yaml
Esta fue la configuracion que funciono para mi equipo:

---
ip: "192.168.10.10"
memory: 2048
cpus: 2
provider: virtualbox

authorize: /root/.ssh/id_rsa.pub

keys:
    - /root/.ssh/id_rsa

folders:
    - map: /opt/platzi/phpAvanzado
      to: /home/vagrant/code

sites:
    - map: homestead.test
      to: /home/vagrant/code/public
    - map: cursophp.test
      to: /home/vagrant/code/cursopractica/public

databases:
    - homestead
    - cursophp

``` 

## Configuración de virtual host

- El archivo host sirve para indicarle a nuestra computadora que cierta url está relacionada con cierta ip. Debes modificar este archivo si quieres que al escribir cierta url, el computador entienda una ip dada. En este caso usaremos la ip que tenemos en nuestro archivo “Homestead.yaml” y la url será cursophp.test.
- El comando “vagrant ssh” va a meterte dentro de la máquina virtual que creaste. Esto es bueno porque todo lo que usemos en un equipo de trabajo será estandarizado, todo basado en Linux y con las mismas versiones.
- Homestead ya cuenta con Composer instalado por default, así que podemos traer todas las dependencias de nuestro proyecto con “composer install” una vez que estemos en la carpeta de nuestro proyecto.
- Creamos una conexión ssh para la base de datos y creamos la tabla jobs. Con esto ya funcionará el proyecto del curso pasado, virtualizado.

## Closures 

- Se conocen como funciones anonimas  
- Permiten la creación de funciones que no tienen un nombre específico.
- Pueden ser asignadas a funciones, variables, o usadas como parámetros y valores de retorno
- Las variables pueden contener cualquier tipo de dato como enteros, cadenas y objetos, pero también pueden contener funciones.
- Para usar variables del scope superior en los closures, es necesario usar el “use” y entre paréntesis las variables. 

Ejemplo 

```
$filtro = function ($job) use($maxMount) {
            return $job["months"] > $maxMount;
        };
```


- Podemos usar el map de javascript pero de esta forma en php 
```
$jobs = [
	"edad"=>"12",
	"edad"=>"20",
	"edad"=>"30",
	"edad"=>"40",
	"edad"=>"19",
]; 

$edad_maximas =15; 
#Declaramos nuestra función anonima (use ($edades_maximas)) Como trabjar scope superiores 
$filterFunction = function ($job) use ($edades_maximas) {
	return $job['edad'] >=$edad_maximas;
}

# array_filter es nuestro equivalente a nuestro map en js 
$jobs = array_filter($jobs->toArray(), $filterFunction );


```


## Enlaces 

- https://www.php.net/manual/es/functions.anonymous.php 
- https://www.php.net/manual/es/class.closure.php
- https://github.com/hectorbenitez/curso-introduccion-php/ (Por si deseas decargar el proyecto)


## Type Hinting

