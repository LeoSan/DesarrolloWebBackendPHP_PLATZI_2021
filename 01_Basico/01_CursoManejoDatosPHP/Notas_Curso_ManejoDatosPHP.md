# Curso de Manejo de Datos en PHP

## Comillas

> Comillas simples
- Para manejar datos strings con comillas simples. 
- Si queremos utilizar una comilla simple dentro de nuestro string utilizamos \ (backslash) para escaparla y no nos de error.

> Comillas dobles
- Si queremos acceder a una variable utilizamos comillas dobles. 
- También podemos acceder a una variable con comillas simples, pero tiene que estar fuera de la comillas simples.


> Datos complejos (Comillas dobles)

- Para acceder a datos complejos como un objeto o un array con varios niveles necesitamos utilizar {} (llaves) que encierren a la variable con los parámetros que indicamos.

- Se puede dar el caso de cuando es un objeto, y este solo tiene un nivel en su parámetro accedemos sin utilizar {} (llaves) y para indicar el key ponemos →, ej: $hora→segundos

> Variables variables
- necesitamos utilizar las variables variables, lo hocemos añadiendo $ antes de las {} (llaves) para que búsque la variable variable.

- La variable variable debe tener exactamente el mismo nombre que el dato que tiene la variable principal, deben coincidir tanto en lo que dice como si está en mayúscula o no.

- También para hacer más legible el código podemos encerrar esta llamada a una variable dentro de otra {} (llaves). Ej: {${getLove()}}