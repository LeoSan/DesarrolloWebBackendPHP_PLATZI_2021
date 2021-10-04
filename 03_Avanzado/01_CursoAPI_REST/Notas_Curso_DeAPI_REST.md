# Curso de API REST

## HTTP
> son las siglas de Hypertext Transfer Protocol o protocolo de transferencia de hipertexto, 
- es el conjunto de reglas en las que se van a comunicar dos entidades, en este caso dos computadoras.
- Así como nosotros nos comunicamos en español gracias a poder mover las cuerdas vocales, producir y escuchar sonidos, las computadoras se pueden comunicar a través de HTTP gracias al modelo de TCP/IP.



## REST

- REST es un acrónimo de Representational State Transfer o transferencia de estado representacional, le agrega una capa muy delgada de complejidad y abstracción a HTTP. 
- Mientras que HTTP es transferencia de archivos, REST se basa en la transferencia de recursos.
- REST no es un protocolo ni un estándar, sino que se trata de un conjunto de principios de arquitectura. Los desarrolladores de las API pueden implementarlo de distintas maneras.
- Cuando se envía una solicitud a través de una API de RESTful, esta transfiere una representación del estado del recurso requerido a quien lo haya solicitado. La información se entrega por medio de HTTP en uno de estos formatos: JSON (Javascript Object Notation), HTML, XLT o texto sin formato. JSON es el más popular, ya que tanto las máquinas como las personas lo pueden comprender y no depende de ningún lenguaje.

##  API RESTful es una API diseñada con los conceptos de REST:

- Recurso: todo dentro de una API RESTful debe ser un recurso.
- URI: los recursos en REST siempre se manipulan a partir de la URI, identificadores universales de recursos.
- Acción: todas las peticiones a tu API RESTful deben estar asociadas a uno de los verbos de HTTP: GET para obtener un recurso, POST para escribir un recurso, PUT para modificar un recurso y DELETE para borrarlo.

## REST es muy útil cuando:

- Las interacciones son simples.
- Los recursos de tu hardware son limitados.
- No conviene cuando las interacciones son muy complejas.
 

## Para que una API se considere de RESTful, debe cumplir los siguientes criterios:
 

- Arquitectura cliente-servidor compuesta de clientes, servidores y recursos, con la gestión de solicitudes a través de HTTP.
- Comunicación entre el cliente y el servidor sin estado, así que no se almacena la información del cliente entre las solicitudes; cada una es independiente y está desconectada del resto.
- Datos que pueden almacenarse en caché y optimizan las interacciones entre el cliente y el servidor.
- Una interfaz uniforme entre los elementos, para que la información se transfiera de forma estandarizada. 

## Para ello deben cumplirse las siguientes condiciones:
 
- Los recursos solicitados deben ser identificables e independientes de las representaciones enviadas al cliente.
- El cliente debe poder manipular los recursos a través de la representación que recibe, ya que esta contiene suficiente información para permitirlo.
- Los mensajes autodescriptivos que se envíen al cliente deben contener la información necesaria para describir cómo debe procesarla.
- Debe contener hipermedios, lo cual significa que cuando el cliente acceda a cierto recurso, debe poder utilizar hipervínculos para buscar las demás acciones disponibles en ese momento.
- Un sistema en capas que organiza en jerarquías invisibles para el cliente cada uno de los servidores (los encargados de la seguridad, del equilibrio de carga, etc.) que participan en la recuperación de la información solicitada. 
- Código disponible según se solicite (opcional), es decir, la capacidad de enviar código ejecutable del servidor al cliente cuando se solicite, lo cual amplía las funciones del cliente.
 
> Si bien la API de REST debe cumplir todos estos parámetros, resulta más fácil de usar que un protocolo definido previamente, como SOAP (protocolo simple de acceso a objetos), el cual tiene requisitos específicos, como la mensajería XML y la seguridad y el cumplimiento de las operaciones integrados, que lo hacen más lento y pesado.
 
- Por el contrario, REST es un conjunto de pautas que pueden implementarse según sea necesario. 
- Por esa razón, las API de REST son más rápidas y ligeras, y resultan ideales para el Internet de las Cosas (IoT) y el desarrollo de aplicaciones para dispositivos móviles.


## Enlaces 
- https://www.redhat.com/es/topics/api/what-is-a-rest-api
- https://vimeo.com/20781278
- https://www.crummy.com/writing/speaking/2008-QCon/act3.html
- https://en.wikipedia.org/wiki/HATEOAS
- https://github.com/Lucneonct/ApiRestPlatzi/blob/master/index.js -> Código de Ejemplo
------------------------------------------------------------------

## 7 Buenas prácticas del diseño de APIs RESTful

- Siempre utiliza sustantivos para nombrar tus recursos.
- Añade los nombres en plural para las urls.
- Las modificaciones a recursos deben hacerse con su verbo HTTP correspondiente: POST, PUT o DELETE.
- Para devolver recursos asociados a otro recurso utiliza url que incorporen subrecursos: /Autos/1/Choferes.
- Navegabilidad vía vínculos.
- Cuando devuelvas colecciones deben ser filtrables, ordenables y paginables.
- Versiona tu API, añade el número de versión en la url: v1/Autos.