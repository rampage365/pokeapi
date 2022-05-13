# Pokedex

## En que consiste la aplicacion
Simular una pokedex consumiendo el API de la pagina https://pokeapi.co/
En este caso, espero que el siguiente proyecto llegue a parecerse a la pagina https://www.pokemon.com/el/pokedex/

## Stack Tecnológico 
### Front End Technologies
CSS
HTML
JS

### Back End Technologies
NODE.js

## Documentacion de la APP
Para acceder a las funciones del API, no es necesario un APIKEY, ya que es de libre acceso

### Endpoints API
Debido a que el fin del proyecto era simular lo mas que se pueda una pokedex, se recurrio a varios ENDPOINTS para simular dicha funcion

#### ENDPOINT #1
A travez de este primer ENDPOINT se obtiene una lista de pokemones en orden de aparicion en el universo animado de pokemon, no hay un orden que indique cual es la evolucion del pokemon, solo devuelbe el nombre del pokemon y una url a travez del cual podemos acceder a las caracteristicas del pokemon.

```http
  GET https://pokeapi.co/api/v2/pokemon?limit=${cantidadPokemones}&offset=${desdeIndicePokemones}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `limit`      | `int` | **Required**. Cantidad de pokemones que la API nos devolbera |
| `offset`      | `int` | **Required**. Desde que indice queremos obtener los pokemones (debido a que no hay orden, el api devolbera a los pokemones y sus evoluciones de manera independiente no ligada u organizada) |




#### ENDPOINT #1
A travez de este primer ENDPOINT se obtiene una lista de pokemones en orden de aparicion en el universo animado de pokemon, no hay un orden que indique cual es la evolucion del pokemon, solo devuelbe el nombre del pokemon y una url a travez del cual podemos acceder a las caracteristicas del pokemon.

```http
  GET https://pokeapi.co/api/v2/pokemon?limit=${cantidadPokemones}&offset=${desdeIndicePokemones}
```

| Parameter | Type     | Description                       |
| :-------- | :------- | :-------------------------------- |
| `limit`      | `int` | **Required**. Cantidad de pokemones que la API nos devolbera |
| `offset`      | `int` | **Required**. Desde que indice queremos obtener los pokemones (debido a que no hay orden, el api devolbera a los pokemones y sus evoluciones de manera independiente no ligada u organizada) |
