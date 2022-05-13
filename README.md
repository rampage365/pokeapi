# Pokedex

## En que consiste la aplicacion
Simular una pokedex consumiendo el API de la pagina https://pokeapi.co/

En este caso, espero que el siguiente proyecto llegue a parecerse a la pagina https://www.pokemon.com/el/pokedex/

## Stack Tecnológico 
### Front End Technologies
CSS,
HTML y
JS

### Back End Technologies
NODE.js

## Documentacion de la APP
Para acceder a las funciones del API, no es necesario un APIKEY, ya que es de libre acceso.

### Endpoints API
Debido a que el fin del proyecto era simular lo mas que se pueda una pokedex, se recurrio a varios ENDPOINTS para simular dicha funcion.

Tambien debido a que el API devuelbe informacion no ligada, desordenada o o devuelbe un nuevo ENDPOINT para consultar sobre las caracteristicas o evolucion de los pokemones.

#### ENDPOINT #1
A travez de este primer ENDPOINT se obtiene una lista de pokemones en orden de aparicion en el universo animado de pokemon.

```http
  GET https://pokeapi.co/api/v2/pokemon?limit=${cantidadPokemones}&offset=${desdeIndicePokemones}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `limit`      | `int` | **Required**. Cantidad de pokemones que la API nos devolbera |
| `offset`      | `int` | **Required**. El indice a partir del cual queremos obtener los pokemones |

 En la informacion devuelta no hay un orden que indique cual es la evolucion del pokemon, lo trata de manera independiente como si fuera otro POKEMON distinto, solo devuelbe el nombre del pokemon y una url a travez del cual podemos acceder a las caracteristicas del pokemon, teniendo que utilizar dicha URL para obtener informacion adicional de dicho pokemon a travez de otro ENDPOINT el cual es el #2.




#### ENDPOINT #2
A travez de este segundo ENDPOINT se obtienen las caracateristicas del pokemon, como peso, altura, imagen representativa, etc.

Pero no la evolucion de dicho pokemon

```http
  GET https://pokeapi.co/api/v2/pokemon/{nombre_o_Indice}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `nombre_o_Indice`      | `string` | **Required**. Puedes ingresar un numero(ID) o el nombre del pokemon del cual quieres obtener informacion |

#### ENDPOINT #3
A travez de este tercer y ultimo ENDPOINT se obtiene el ID de los pokemones respetando sus Evoluciones (ya no los trata de manera independiente), dando un toal de 476 pokemones con hasta 2 evoluciones.

Pero no devuelbe las caracterisiticas de los Pokemones, por lo cual es necesario usar la logica para obtener la informacion que deseemos a travez de todos los ENDPOINTS presentados

```http
  GET https://pokeapi.co/api/v2/evolution-chain/${id}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `id`      | `string` | **Required**. Puedes ingresar un numero(ID) o el nombre del pokemon del cual quieres obtener informacion |




## Aplicacion en Construccion
### Avance 1
Por el momento se ha logrado completa la logica para obtener la informacion de los pokemones con sus respectivas caracteristicas y evoluciones.

Se puede apreciar ello consultando la consola de la pagina y ejecutando la funcion.

```
consultaPokemones()
```
Esta funcion hace uso del ENDPOINT 3 y nos muestra las evoluciones relacionada a los pokemones


### Avance 2
Esta funcion hace uso del ENDPOINT 1 y 2 trae el nombre y ID de los pokemones con sus respectivas caracteristicas

```
listaPokemones()
```

Todas las funciones utilizan variables globales que les permiten consultar los primeros 20 pokemones, mas adelante sera reemplazado para que el usuario maneje a voluntad a travez de un entorno amigable que cantidad de pokemones desea ver y si quiere saber mas de un determinado pokemon presentara sus caracteristicas extendidas.
