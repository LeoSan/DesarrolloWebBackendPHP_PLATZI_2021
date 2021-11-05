#Curso de Introducción al Despliegue de Aplicaciones

## Clase 1: Presentación. 

- Como desplegar Tipo Front.  
- Como desplegarTipo Backend. 

## Clase 2: Historia de las aplicaciones

- En los años 70 las aplicaciones solo eran de escritorio
- Todo lo guardaban en ficheros locales 
- Aplicaciones monoliticas 

## Clase 3: Apps Monolíticas vs microservicios

> Aplicaciones Monolíticas: Todo va en un solo servidor conveniente por lo facil y escalable, pero como desventajas si fallaba algo todo dejaba de funcionar.  

> Aplicaciones microservicios: Es un componente o una aplicacion la cual se encarga de hacer solo una cosa.  En lugar de compartir una sola base de datos como en la aplicación Monolitica, cada microservicio tiene su propia base de datos. Tener una base de datos por servicio es esencial si desea beneficiarse de los microservicios. 

> Nota: Lo recomendable hoy en día es dividir nuestra aplicación ya no solo a nivel lógico, sino también a nivel físico. Un error muy común que se suele encontrar es que las aplicaciones suelen cargar archivos en el mismo disco duro del servidor, pero hoy en día existe una cosa maravillosa llamada Amazon S3

![Imagen](.info/Info.png)


# Clase 4: Stacks LAMP, MERN, JOTL, JAM

**LAMP**
- Linux (https://platzi.com/clases/linux/)
- Apache
- MySQL (https://platzi.com/clases/sql-mysql/)
- PHP (https://platzi.com/desarrollo-php/)

**JOTL**

- Java (https://platzi.com/desarrollo-java/)
- Oracle
- Tomcat
- Linux (https://platzi.com/clases/linux/)

**MERN**

- Mongo (https://platzi.com/clases/mongodb/)
- Express (https://platzi.com/clases/express-js/)
- React (https://platzi.com/desarrollo-react/)
- Node (https://platzi.com/backend-javascript/)

**MEAN**
- Mongo (https://platzi.com/clases/mongodb/)
- Express (https://platzi.com/clases/express-js/)
- Angular (https://platzi.com/desarrollo-react/)
- Node (https://platzi.com/backend-javascript/)

**JAM**

- JavaScript (https://platzi.com/escuela-javascript/)
- API
- Markdown
- MEVN

**MARN**
- Mongo (https://platzi.com/clases/mongodb/)
- Express (https://platzi.com/clases/express-js/)
- Angular (https://platzi.com/desarrollo-react/)
- Vue JS (https://platzi.com/vue/)
 

# Clase 5: LAMP


**Existen varias formas de desplegar, estas son las más comunes:**

- Hosting compartido: la fórmula más popular es comprar un servicio de hosting donde te proveen de una interfaz web llamada Cpanel donde puedes crear tu base de datos mysql, subir tus archivos php por ftp o administrador web y tener tu app en minutos.

- Hosting gratuito: Algunas empresas proveen hosting gratuito a cambio de que se integre publicidad en tus scripts php o de acceder a la información de tu sitio, sin embargo estas tienden a tener interfaces web menos amigables para subir archivos de la aplicación y la base de datos.

- Usar un VPS: utilizando plataformas como Digital Ocean, se puede crear un droplet (forma en que llaman a los VPS en esta empresa), para tener acceso SSH y poder instalar php,mysql, apache y lo que se necesite para instalar la aplicación web, puede tomar más tiempo en configurar todo, y el vps se debe administrar por la persona, a cambio, se gana acceso total al servidor para modificar php, mysql, y realizar tareas de gestión, o escalamiento de la aplicación.


**Estas son las formas más comunes para desplegar una aplicación JOTL.**

- Usar una plataforma como servicio: Se puede utilizar una PaaS - Platform As A Service, como es el caso de heroku, que se encarga del despliegue de la aplicación y se puede hacer un despliegue más rápido, pero se pierde el control sobre el servidor.

- Usar una Infraestructura como servicio: IaaS o Infrastructure As a Service, son empresas como AWS de Amazon, Cloud Platform de Google, Azure de microsoft o incluso IBM cloud, estas ofrecen un control mayor sobre la infraestructura, desde los servidores VPS, red, Backups, disponibilidad, escalabilidad, seguridad entre otras ventajas, sin embargo requieren de un conocimiento en manejo de infraestructuras para poder configurar todas estas opciones.

# Clase 6: Despliegue en Github pages


# Clase 7: Despliegue en Surge 

> Podemos usar surge para el despliegue de paginas estaticas generan dominios aleatorios 
- https://surge.sh/

**Pasos**
- Paso 1: Crear una carpeta en escritorio 
- Paso 2: Crear un archivos html/proyecto
- Paso 3: Abrir terminal de comandos
- Paso 4: Ubicarse en la carpeta creada
- Paso 5: ir a https://surge.sh/
- Paso 6: ejecutar el comando `npm install --global surge`
- Paso 7: escribir el siguiente comando `surge`
- Paso 8: te pide email y contraseña -> confirmar y listo. 


## Clase 8: Despliegue en Netlify


> Podemos desplegar en nerlify, lo bueno es que podemos desplegar nuestros build generados por react, tambien podemos asociar nuestro repositorio de git a netlify 

https://www.netlify.com/



Nota: 
`
--A tomar en cuenta--

Netlify es mi favorito a la hora de desplegar aplicaciones a producción.
Uno de los problemas con los que normalmente te puedes encontrar es el routing del servidor. Por ejemplo:
Si tienes una aplicación SPA (single page application) hecha con React y manejas rutas con React-Router, tienes que tomar en cuenta que al ingresar a una de las rutas de tu aplicación directamente el servidor va a responder con un error 404.

En este caso lo que tienes que hacer es configurar los redirects para tu aplicación. Netlify provee 2 formas de confirgurar las rutas, una es mediante un archivo _redirects y la otra que es mucho mas práctica es mediante un archivo netlify.toml que se coloca en la raiz de tu proyecto.

https://docs.netlify.com/routing/redirects/#syntax-for-the-netlify-configuration-file

Deber redireccionar todas las rutas a tu archivo index.html para que tu aplicación se cargue y una vez cargada se encargará del rounting en el lado cliente.
te dejo un ejemplo de configuración del archivo netlify.toml a continuación:

[[redirects]]
  from = "/"
  to = "/index.html"
  status = 200

[[redirects]]
  from = "/users"
  to = "/index.html"
  status = 200

[[redirects]]
  from = "/add"
  to = "/index.html"
  status = 200

[[redirects]]
  from = "/*"
  to = "/index.html"
  status = 400
`

## Clase 9: Despliegue en Vercel
 
 >Te permite desplegar paginas estaticas y combinar con github  
 
 https://vercel.com/ 
 
 Clase -> https://platzi.com/clases/2011-despliegue-apps/31609-despliegue-en-vercel/
 
 ## Clase 10: Desplegando una base de datos NoSql en Mongo Atlas
 
  Mongo Altlas -> https://platzi.com/clases/2011-despliegue-apps/31610-desplegando-una-base-de-datos-nosql-en-mongo-atlas/
  
## Clase 10: Desplegando una base de datos relacional en ElephantSQL

> Podemos generar y administradir de BD postgresql

https://www.elephantsql.com/ 

Clase -> https://platzi.com/clases/2011-despliegue-apps/31611-desplegando-una-base-de-datos-relacional-en-elepha/


## Clase 11: Qué es Heroku
> Heroku  nos permite desplegar nuestro backend, podemos desplegar en php, react, java, pytho, Heroku es un PaaS Platform As A Service y te permite desplegar tus aplicaciones backend con los lenguajes soportados por Heroku, ellos se encargan de la administración del servidor,


https://www.heroku.com/

> Permitir que cualquier ip se conecte a Mongo DB Atlas -> https://platzi.com/clases/2011-despliegue-apps/31613-desplegando-api-en-heroku/

>También existen otras cosas llamadas BaaS (Backend As A Service) donde tú no te preocupas por programar backend, sino que ya está programado y tu solo lo configuras, pueden ver más de esto en el Curso de Firebase para la web

> 
13
Postman es muy útil para hacer peticiones a API’s y ver las respuestas que nos devuelven, otras alternativas que podemos usar son: cURL’s desde la terminal, el método fetch() de JavaScript o incluso aplicaciones online que permiten hacer este tipo de peticiones a API’s:D!
  

