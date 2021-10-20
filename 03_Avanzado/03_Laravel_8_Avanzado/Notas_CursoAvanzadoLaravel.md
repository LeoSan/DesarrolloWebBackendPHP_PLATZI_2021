# Curso Avanzado de Laravel  19/10/2021 

## Clase 8 - Manejo de relaciones en bases de datos con Laravel 

> Lo importante para esta clase es mantener las relaciones entre las tablas 
            
			- Generalmente Iniciamos En los Migrate definiendo quien es la clave foranea 
			- [Ejemplo](https://github.com/LeoSan/AppCursoLaravel8/blob/main/database/migrations/2021_05_15_012350_create_courses_table.php)
			´´´Php
							$table->foreign('user_id')->references('id')->on('users');// Campo PK y nombre de la tabla definida en el modelo 
							$table->foreign('category_id')->references('id')->on('categories');// Campo PK y nombre de la tabla definida en el modelo 

			´´´
			
			- Luego en los modelos usamos 
			- [Ejemplo](https://github.com/LeoSan/AppCursoLaravel8/blob/main/app/Models/Course.php)
			
			´´´Php 
				public function user(){
					return $this->belongsTo(User::class);
				}    
				
				public function posts(){
					return $this->hasMany(Post::class);
				}
			
			´´´
			
## Clase 9 - Relaciones Polimórficas en Eloquent

> Las relaciones polimorficas me permite que un modelo pertenezca a mas de un modelo. 

- [Ejemplo Polimorfismo](info/Relaciones_Polimorficas.png)
- [Ejemplo Polimorfismo Video 1 ](https://www.youtube.com/watch?v=wKOFUzqSh74&ab_channel=RimorsoftOnline)
- [Ejemplo Polimorfismo Video 2 ](https://www.youtube.com/watch?v=rx1DQBE01b0&ab_channel=LaravelDaily)
- [En Laravel El tema de Relaciones Polimórficas ](https://laravel.com/docs/7.x/eloquent-relationships#polymorphic-relationships)
- [El tema de attach ](https://www.amitmerchant.com/attach-detach-sync-laravel/)

´´´Php
	//Algo Nuevo: Esto equivale 
	$table->morphs('rateable');
	
	
	//Algo Nuevo: Esto equivale a esto 
	$table->string('rateable_type');
	$table->unsignedBigInteger('rateable_id');
	
 ´´´	

> Nota: cuando Usamos tablas pivote podemos extenderlo tipo Pivot pero al final es un modelo 

´´´Php
class Rating extends Model-> Pivot {


}
	//Asi creamos la relacion con morph 
    public function rateable(){
        return $this->morphTo();
    }

    public function qualifier(){
        return $this->morphTo();
    }

´´´

**Tema Complejo. **

> Es importante tener en cuenta que se establecerá una relación polimorfa muchos a muchos (MaM)

[Clase Sencilla de Polimorfismo](https://www.youtube.com/watch?v=rx1DQBE01b0&ab_channel=LaravelDaily)



- Primera parte - Relación a establecer
> Primero que nada hay que entender que es lo que vamos a relacionar a nivel de base de datos, esto es una entidad que 
pueda calificar (un usuario, un invitado, una sesión, etc) con una entidad que pueda ser calificada (producto, categoría, etc.), 
como muchos usuarios podrían calificar muchos productos y muchos productos podrían ser calificados por muchos usuarios 
vemos que se forma una relación MaM, según teoría de bases de datos relacionales, esta relación se puede alcanzar 
mediante tres tablas - una tabla usuarios, una tabla productos y una tabla intermedia o pivote ratings.

- Segunda parte - Migración de tabla Ratings
> Esta tabla tendrá 5 columnas importantes, el score, rateable_type, rateable_id, qualifier_type y qualifier_id, 
los últimos cuatro pueden inferirse por las instrucciones $table->morphs('rateable') y $table->morphs('qualifier'). 
Así que, ¿qué significan esas columnas?, Hay que ver el video del inicio del tema hay que comprender que  
**rateable_type** y **qualifier_type** hacen referencia al modelo que recibe calificación y al modelo que dictó dicha calificación, 
respectivamente - y **rateable_id/qualifier_id** hacen referencia a el registro especifico dentro de la tabla de cada 
type que recibe/dicta la calificación.


- Tercera parte - Modelo Rating
> El modelo Rating extenderá de Pivot y no de Model puesto que nuestra tabla es una de tipo intermedia o 
pivote, Indicamos el campo con un valor inermedio para cumplir con las reglas de normalización cada tabla tendra un ID unico 
 y se indica la tabla a la que nos relacionaremos. 
 Después es como definir cualquier relación de Laravel, 
 tenemos que indicar el nombre del método para acceder a la relación y retornar la relación polimorfa que no toma argumentos 
 porque como puede relacionarse a varios Modelos la función MorphTo se encarga de determinarlo.

- Cuarta parte - Previo al Trait Can Rate
> Aquí es donde el titulo avanzado del curso toma sentido jeje, en un sistema diferente a este (llamemosle un sistema normal) 
lo que se haría sería establecer la otra parte de la relación polimorfa en los modelos específicos, 
por ejemplo en el caso del modelo User describiríamos la relación de la siguiente forma:
´´´Php
public function ratings()
{
	return $this->morphMany( 'App\Models\Rating', 'qualifier' );
}
´´´
lo cual le indicaría a Laravel como establecer la relación polimorfa desde Usuario con Rating. 
Usamos la  ventaja de los Traits para delegar la responsabilidad de establecer la otra parte de 
la relación polimorfa a una clase en especifico y así poder darle la posibilidad a cualquier clase 
que queramos de poder calificar, 

- Quinta parte - Trait Can Rate
> El método ratings de la clase CanRate es lo que referí como la otra parte de la relación polimorfa ya que se encargará de 
relacionar el modelo que le pasen por parámetro dentro de la tabla ratings usando el **qualifier_id y rateable_id** como 
llaves foráneas para después retornar los ratings (con timestamps) donde el **rateable_type** sea el modelo objetivo y el 
qualifier_type sea el modelo que invoco la relación.

> Luego este método lo que hace es tomar dos parámetros, **modelo y calificación**, el primero hará referencia 
que modelo se va a calificar con el puntaje que se pasa en calificación, por lo que al momento de invocar la 
relación ratings del Trait CanRate podemos encadenar el método attach  para básicamente indicar que se escriba 
en la tabla pivote el id que tenga el modelo relacionado al score ya antes mencionados.



**Otro Manera de entenderlo**

## EJEMPLO1:
- Un USER le puede dar likes a muchos VIDEOS de YouTube.
- Y Un VIDEO de YouTube puede tener likes de muchos USERS.
- Esto es una relación muchos a muchos, así que se hace una tabla pivote entre ambas, que tenga el user_id y el video_id.
- Hasta aquí estamos bien.


## EJEMPLO2:
- Ahora supongamos que YouTube, además de videos, tenga imagenes. Entonces nace una nueva relación muchos a muchos entre USER e IMAGES. Crearías una tabla pivote que tenga el user_id y el image_id.
- Listo. Entonces quedaría así:
´´´Php
ejemplo1: user_id y video_id
ejemplo2: user_id y image_id
´´´ 
- Estas dos tablas son muy parecidas. 
- Entonces alguien quiso ahorrarse las dos tablas, y tener una sola que haga todo eso, y aquí es donde entra la relación polimórfica:
	- Una tabla que tiene: user_id, likeable_type y likeable_id.
	- El likable_type sería VIDEO, o IMAGE o etc
	- Y el likable_id sería el ID del likeable_type. (video_id ó image_id ó etc)


    

