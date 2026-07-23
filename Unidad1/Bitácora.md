# Bitácora Unidad 1: Audio con Strudel

## 1. Contexto e Inspiración: Sistemas Físicos Interactivos y Arte Generativo

Un Sistema Físico Interactivo (SFI) es un conjunto de componentes físicos y/o digitales que responden a estímulos del entorno, transformando una entrada (input) en una salida (output) a través de algún tipo de procesamiento. Se usan comúnmente en instalaciones artísticas, videojuegos, experiencias de realidad aumentada y más.
El diseño generativo es una metodología que utiliza reglas, algoritmos y procesos automatizados para generar resultados visuales o funcionales. Parte de un principio similar a los sistemas físicos interactivos donde el diseñador actúa más como programador de comportamientos que como autor de una única pieza estática. Los Sistemas Físicos Interactivos y el Arte Generativo comparten la estructura básica *input → procesamiento → output*, pero se aplican en contextos distintos: el primero busca generar experiencias sensibles a la interacción física, y el segundo permite automatizar la creación visual o artística mediante lógica y código. Ambos permiten transformar la manera en que creamos, experimentamos y entendemos el mundo físico y digital.
Al conectar esta base teórica con los referentes explorados en la clase, resulta evidente cómo estos conceptos cobran vida en escenarios reales. Plataformas y estudios como **Moment Factory**, **Sandbox VR** o **Excurio** son ejemplos a gran escala de cómo el entorno y el espectador actúan como *inputs* para alterar mundos digitales inmersivos. Por otro lado, proyectos como **Hermes** o las herramientas de **Daydream AI** ilustran perfectamente el potencial de la lógica generativa aplicada a la reacción sonora y visual en tiempo real. 
Sin embargo, el referente que mejor sintetiza el propósito de nuestro proyecto es **PlexusPlay**. Al analizar su trabajo durante nuestra sesión en el tablero de Excalidraw y el video, pude observar cómo un solo intérprete se convierte en el nodo central de un SFI: combinando música en vivo, visuales reactivos y *wearables*. Entender cómo él integra el performance humano con el procesamiento algorítmico me da una perspectiva mucho más clara del sistema interactivo en tiempo real que buscamos construir durante el curso, donde el sonido (que ahora exploraremos en Strudel) será una de las capas fundamentales.


## 2. Exploración Sonora en Strudel 

Para esta actividad, el objetivo fue crear un mini estudio sonoro utilizando programación en vivo (live coding) junto al sitio web de [Make Beats](https://learningmusic.ableton.com/make-beats/make-beats.html) . Exploré cómo combinar bases rítmicas con estructuras melódicas y armónicas, utilizando capas para construir la pieza.

### 2.1. Decisiones Sonoras

Mi intención principal era crear una atmósfera animada y épica, inspirada en la música de las escenas de pelea o de mucha acción en los animes. Por eso elegí un tempo rápido y enérgico de 140 BPM (`setcpm(140/4)`). 

Para construir esta energía, tomé como punto de partida algunos elementos del ejemplo que el profesor nos dejó en la página del curso y los mezclé con mis propias ideas. Quise generar un contraste interesante: por un lado, una base rítmica muy marcada y agresiva usando sonidos clásicos de percusión electrónica (la Roland TR-909), y por el otro, contrastarla con el sonido orgánico de un piano para la melodía y la armonía, lo cual le da ese toque dramático y épico que buscaba. ¡El resultado logró transmitir justo esa sensación de movimiento que quería!

### 2.2. Patrones Creados y Proceso
Mi proceso comenzó estructurando el tempo y explorando diferentes capas de percusión. Definí un tempo de `setcpm(140/4)` y probé varias secuencias básicas de percusión (bombo, caja, hi-hats, (también use la ocarina). 

Finalmente, consolidé el ritmo en una capa principal llamada `capaDAN`, donde utilicé la función `.beat()` para ubicar exactamente cada elemento de la batería (bombo, palmas, hi-hats y platillos) en subdivisiones de 16 pasos, logrando un ritmo estructurado:

```javascript
setcpm(140/4)

// Exploración inicial de capas rítmicas
let capa1 = s("[bd bd] sd [hh hh hh] oh").bank("RolandTr909")
let capa2 = s("bd [sd sd] hh oh").bank("RolandTr909")
let capa3 = s("hh*4")
let capa4 = stack(
  s("[bd bd] sd [hh hh hh] oh").bank("RolandTr909"),
  s("hh*4")
)

// Capa rítmica final consolidada
let capaDAN = stack(
  s("oh").beat("3,7,11,15",16),
  s("hh").beat("0,1,2,3,4,8,9,10,11",16),
  s("cp").beat("2,6,10,14",16),
  s("bd").beat("0,1,4,5,8,9,12,13",16) 
) 

$:capaDAN
```
Una vez tuve la base rítmica, agregué la capa armónica y melódica usando el sonido de piano. Para la armonía creé una progresión de acordes, a la cual le añadí un filtro paso bajo (.lpf) y un slider en el ataque para poder modificar la fuerza del sonido en vivo, adaptándolo a la energía del beat. Encima de esto, programé una melodía usando la función note() con silencios (~) para darle "respiro" a la secuencia.

```javascript
let melody = note("[a4 ~ e5 d5 c5 b4 ~ a4  e4 ~ b4 c5 d5 e5 ~ ~]")
  .sound("piano")
  .legato(1);

let harmony = note("<[f3,a3,c4,e4] [g3,b3,d4,a4] [e3,g3,b3,d4] [a3,c4,e4,b4]>")
  .sound("piano")
  .attack(slider(0.1, 0, 1)) // Ataque dinámico para controlar la fuerza
  .lpf(slider(1600, 300, 2000))
  .room(2);

$melody: melody$harmony: harmony
```

### 2.3. Errores Encontrados y Soluciones

Durante la programación de la base rítmica, específicamente en la `capaDAN`, tuve un inconveniente al utilizar la función `.beat()`. Al principio, el código se saltaba notas y el patrón rítmico no sonaba como lo había planeado.
Al revisar el código junto con el profesor, nos dimos cuenta de que el problema era un error de sintaxis: me había faltado colocar las comas (`,`) dentro del string que define las posiciones de los golpes en la subdivisión (por ejemplo, escribía `s("hh").beat("0 1 2 3...",16)` en lugar de `s("hh").beat("0,1,2,3...",16)`). Al corregir la sintaxis y añadir las comas correspondientes, la secuencia de 16 pasos se leyó correctamente y el ritmo se sincronizó a la perfección.

### 2.4. Evidencias del Resultado

Enlace al código: [Strudel](https://strudel.cc/#Ly8gUHJlYmFrZSBzY3JpcHQKLy8KLy8gVGhpcyBpcyBjb2RlIHRoYXQgaXMgbG9hZGVkIGJlZm9yZSB5b3VyIHBhdHRlcm4gaXMgcnVuLgovLyBZb3UgY2FuIHVzZSBpdCB0byBkZWZpbmUgY3VzdG9tIGZ1bmN0aW9ucyB0byB1c2UgaW4gYW55IHBhdHRlcm4uCi8vIAovLyBUaGlzIGlzIGFuIGluaXRpYWwgZXhhbXBsZSBzY3JpcHQuIFlvdSBjYW4gZWRpdCBpdCB0byBhZGQgCi8vIHlvdXIgb3duIGZ1bnRpb25zLgovLwovLyBUbyB1c2UgYSBzY3JpcHQgc2hhcmVkIGJ5IHNvbWUgb3RoZXIgdXNlciB5b3UgY2FuIHVzZQovLyB0aGUgaW1wb3J0LWJ1dHRvbiBvciBwYXN0ZSB0aGUgc2NyaXB0IGluIHRoaXMgZWRpdG9yLgoKY29uc3QgcmF0Y2hldCA9IHJlZ2lzdGVyKCdyYXRjaGV0JywgKHBhdCkgPT4gcGF0LnNvbWV0aW1lcyhwbHkoMikpKQoKc2V0Y3BtKDE0MC80KQoKbGV0IGNhcGFEQU4gPSBzdGFjaygKICBzKCJvaCIpLmJlYXQoIjMsNywxMSwxNSIsMTYpLAogIHMoImhoIikuYmVhdCgiMCwxLDIsMyw0LDgsOSwxMCwxMSIsMTYpLAogIHMoImNwIikuYmVhdCgiMiw2LDEwLDE0IiwxNiksCiAgcygiYmQiKS5iZWF0KCIwLDEsNCw1LDgsOSwxMiwxMyIsMTYpIAopIAoKJDpjYXBhREFOCgpsZXQgbWVsb2R5ID0gbm90ZSgiW2E0IH4gZTUgZDUgYzUgYjQgfiBhNCAgZTQgfiBiNCBjNSBkNSBlNSB%2BIH5dIikKICAuc291bmQoInBpYW5vIikKICAubGVnYXRvKDEpOwoKbGV0IGhhcm1vbnkgPSBub3RlKCI8W2YzLGEzLGM0LGU0XSBbZzMsYjMsZDQsYTRdIFtlMyxnMyxiMyxkNF0gW2EzLGM0LGU0LGI0XT4iKQogIC5zb3VuZCgicGlhbm8iKQogIC5hdHRhY2soc2xpZGVyKDAuMSwgMCwgMSkpIC8vIFVuIGF0YXF1ZSB1biBwb2NvIG3DoXMgcsOhcGlkbyBwYXJhIHF1ZSB0ZW5nYSBmdWVyemEgY29uIGVsIGJlYXQKICAubHBmKHNsaWRlcigxNjAwLCAzMDAsIDIwMDApKQogIC5yb29tKDIpOwoKJG1lbG9keTogbWVsb2R5CiRoYXJtb255OiBoYXJtb255)

## Resultado Exploración Sónora en Strudel

```javascript
setcpm(140/4)

let capa1 = s("[bd bd] sd [hh hh hh] oh").bank("RolandTr909")
let capa2 = s("bd [sd sd] hh oh").bank("RolandTr909")
let capa3 = s("hh*4")
let capa4 = stack(
s("[bd bd] sd [hh hh hh] oh").bank("RolandTr909"),
s("hh*4")
)

let capaDAN = stack(
  s("oh").beat("3,7,11,15",16),
  s("hh").beat("0,1,2,3,4,8,9,10,11",16),
  s("cp").beat("2,6,10,14",16),
  s("bd").beat("0,1,4,5,8,9,12,13",16) 
) 

$:capaDAN

let melody = note("[a4 ~ e5 d5 c5 b4 ~ a4  e4 ~ b4 c5 d5 e5 ~ ~]")
  .sound("piano")
  .legato(1);

let harmony = note("<[f3,a3,c4,e4] [g3,b3,d4,a4] [e3,g3,b3,d4] [a3,c4,e4,b4]>")
  .sound("piano")
  .attack(slider(0.1, 0, 1)) // Un ataque un poco más rápido para que tenga fuerza con el beat
  .lpf(slider(1600, 300, 2000))
  .room(2);

$melody: melody
$harmony: harmony
```
