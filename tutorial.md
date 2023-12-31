---
title: Tutorial
description: Como jugar este maravilloso proyecto
---

## Ejecucion del juego

Una vez instalado el juego este se puede correr desde cualquier directorio de la siguiente manera:

* Primero hay que abrir el servidor, para esto hay que ejecutar en una terminal:

  ```bash
  $ ./wormsServer <puerto>
  ```
  
  *Nota: Reemplazar `<puerto>` por el numero puerto deseado.*

* Una vez tengamos el server corriendo en una terminal abrimos otra y ejecutamos lo siguiente:

  ```bash
  $ ./wormsClient
  ```

Este comando abrira la interfaz grafica y elgiendo la IP y el puerto a donde conectarse ya se puede disfrutar de este maravilloso juego.


## Como jugar

Una vez introducida la IP y el puerto veremos la siguiente pantalla:

![start_game_lobby](https://github.com/PandolfiJoaquin/pandolfijoaquin.github.io/assets/90098530/01c9e1a0-dae8-443d-bbac-d7056398b4b1)


### Crear una partida

Para jugar primero hay que crearla, por ende tocamos la opcion: `Create Game`. 

Dentro veremos la siguiente pantalla:

![create_game_lobby](https://github.com/PandolfiJoaquin/pandolfijoaquin.github.io/assets/90098530/b09e2c57-f2bd-4f50-b338-ed0c2acec6df)

En esta debemos elegir:
* La cantidad de jugadores (1-4)
* El nombre de la partida
* El mapa a elegir (Clickeandolo o eligiendo uno custom)

Cabe destacar que la partida no empezara hasta que no se unan todos los jugadores.


**IMPORTANTE**: El juego no permite dos partidas con el mismo nombre. Cuando se termina una partida, ese nombre puede ser reutilizado. (Una partida se da como finalizada cuando ambos usuarios cerraron el juego).

### Unirse a una partida

Para unirse a una partida navegamos hacia `Join Game`.

Dentro veremos:

![join-game-lobby](https://github.com/PandolfiJoaquin/pandolfijoaquin.github.io/assets/90098530/42b33df1-a737-4fb1-8261-797ee6cd9706)


En esta decidimos a que partida unirnos a traves del menu desplegable. En caso de crear partidas despuesde tener abierto el cliente se puede tocar el boton de refresh para buscar las ultimas partidas creadas.

### Ejemplo

Dejamos un pequeño ejemplo de como se puede crear una partida y unirse a ella usando un mapa oficial:

<iframe width="560" height="315" src="https://www.youtube.com/embed/Ip0UzGcT8h0?si=rtSa-3MzmBO9t6eY" title="Tutorial de como crear una partida" frameborder="10" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

## Configuraciones

Hay disponible un archivo de configuraciones donde se pueden modificar los valores por defecto de diferentes aspectos del juego. Simplemente modificando las variables pertinentes en `configuration.yaml` podes darle tu propio toque al juego para que quede lo mas divertido posible!

Al cambiar las configuraciones **hace** falta reinstalar el proyecto!

## Mapas

### Seleccion
El juego viene con mapas oficiales por default pero tambien soporta la opcion de agregar mapas custom. La diversion nunca se termina!

Para usar los mapas oficiales basta con clickear su foto y asi iniciar la partida. 

Los custom se pueden seleccionar con el menu desplegable y despues clickeando `choose custom map`

### Creacion/Modificacion

Para poder agregar o modificar mapas existentes se deben seguir los siguientes pasos:

Primero hay que entrar a la carpeta `maps`. Dentro de esta hay un archivo `map_names.yaml` que contiene los nombres de todos los mapas junto con sus archivos correspondientes. Ademas en esta carpeta estan todos los archivos `.txt` de los mapas. 

Para agregar un mapa primero se debe agregar un archivo `.txt` de la siguiente manera:

En cada linea del archivo debe haber una viga o un gusano. En caso de ser una viga se debe indicar: 
  
`beam esquinaIzquierdaX esquinaIzquierdaY angulo largo`

y en caso de ser un gusano:

`worm centroDeMasaX centroDeMasaY`

Finalmente dentro del archivo `map_names.yaml` se debe agregar el nombre del mapa junto con el archivo `.txt` que contiene los datos de este.

Se pueden ver ejemplos dentro de la carpeta que ayudaran a entender mas facilmente el proceso.

Una vez agregado el mapa **hace falta** correr el instalador del proyecto para poder elegirlos.

**ACLARACIONES IMPORTANTES**

- Los mapas deben tener *al menos* 4 gusanos para que se soporten hasta 4 jugadores simultaneos

- NO modificar los nombres de los mapas oficiales

- Al crear un mapa, tener en cuenta que a partir de 2 metros para arriba, la caida le saca vida al gusano. De inicializar un gusano a altas alturas, este empezara con menos vida.

## Controles

* `←`: Mueve el gusano a la izquierda
* `→`: Mueve el gusano a la derecha
* `Enter`: Salto para adelante
* `Backspace`: Salto para atras
* `Mouse`: Al moverlo se puede mover libremente la camara por el mundo
* `Armas`:
  * `Rueda Mouse`: Elije el arma que el gusano usara, basandose en el orden del HUD.
  * `Mouse`: Con este se puede elegir el angulo del disparo, con el click se dispara.
  * `Numeros [0,5]`: Modifica el tiempo de explosion de las granadas.
  * `Teclas`:
    * `e`: deselecciona las armas (puño limpio)
    * `r`: selecciona la Bazooka
    * `t`: selecciona la Granada verde
    * `y`: selecciona el Hacha
    * `u`: selecciona el RemoteOperated
    * `i`: selecciona el Mortero
    * `o`: selecciona la Granada roja
    * `p`: selecciona la Banana
* `Cheats`:
  *  `z`: Le suma vida al gusano actual (con un MaxHealth modificable desde el archivo de configuracion)
  *  `x`: Le otorga al gusano todas las armas
  *  `c`: Vuelve a todos los gusanos invencibles, al tocarlo de vuelta se desactiva el cheat
  *  `v`: Deja estatico el turno, sin importar el tiempo/ perdida de vida/ uso de herramienta
  *  `b`: Vuelve a permitir los cambios de turno

* `Musica`: Se puede mutear y desmutear la musica y los SFX (ademas de usando el YAML) con la tecla `m`.
