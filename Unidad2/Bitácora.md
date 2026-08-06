# Bitácora Unidad 2: Visuales Generativas y Parametrizables

## Contexto e Investigación: ¿Qué es el diseño generativo?

Durante esta primera actividad comprendí que el diseño generativo propone un cambio importante en la manera de pensar el diseño. Antes veía el diseño como la creación de una pieza final, pero ahora entiendo que el verdadero trabajo consiste en construir un sistema capaz de producir muchas posibles versiones de esa pieza.
En otras palabras, ya no se diseña únicamente un resultado, sino el conjunto de reglas, relaciones y comportamientos que harán posible que aparezcan diferentes resultados. Esta idea me pareció bastante interesante porque, en cierto sentido, estamos diseñando al "creador" y no solamente la creación.
Otro concepto que considero fundamental es la mentalidad generativa. Más allá de aprender una herramienta o un algoritmo, implica desarrollar un pensamiento procedural: analizar un problema como un conjunto de procesos, relaciones y transformaciones. Esto cambia completamente la forma de abordar un proyecto, ya que el objetivo deja de ser controlar cada detalle para concentrarse en construir un sistema con una intención clara.

### 1. Reflexión sobre el Diseño Generativo

Después de revisar el material, entendí el diseño generativo como una forma distinta de pensar el proceso creativo. Para mí, no consiste en perseguir únicamente un resultado final, sino en construir una experiencia con un propósito.
Más que preguntarse "¿qué quiero hacer?", la pregunta pasa a ser "¿por qué quiero hacerlo?" y "¿qué sistema puede comunicar esa intención?". Esa diferencia me pareció muy valiosa porque obliga a pensar primero en el significado antes que en la apariencia.
Esta manera de trabajar también cambia el papel del diseñador. En lugar de definir cada elemento manualmente, el diseñador establece las reglas, los parámetros y las relaciones que permitirán que el sistema genere diferentes posibilidades sin perder su identidad.

### 2. Arte Generativo vs Diseño Generativo

Una analogía que me ayudó a entender la diferencia fue pensar que el arte generativo se enfoca en la obra, mientras que el diseño generativo se enfoca en construir el sistema que será capaz de producir esas obras.
El arte generativo busca principalmente la exploración estética o expresiva y permite que el propio sistema participe en la creación de la pieza. El diseño generativo, en cambio, utiliza ese mismo tipo de sistemas para responder a una intención comunicativa o funcional, buscando que el resultado tenga un propósito claro dentro de un contexto determinado.

### 3. Ideas que considero más importantes

La idea que más me quedó de esta actividad es que toda propuesta debe partir de una intención. Una obra puede ser visualmente impresionante, pero cuando además existe un motivo claro detrás de ella, adquiere mucho más valor.
Por esta razón también considero muy importante aprender a diseñar sistemas en lugar de objetos. Si el propósito está bien definido, las reglas del sistema podrán generar múltiples resultados diferentes sin perder la esencia de la propuesta.

### 4. IA, Código y Creatividad

Me gustó la postura presentada durante la clase sobre la inteligencia artificial. Considero que hoy en día es una herramienta prácticamente indispensable para cualquier diseñador y que, con el tiempo, será tan común como cualquier otro software de trabajo.
Sin embargo, también comparto la idea de que la IA no reemplaza la creatividad. Puede acelerar procesos, generar referencias o producir material visual, pero la intención, las decisiones y el significado siguen dependiendo del diseñador. Al final, la creatividad continúa siendo el elemento más valioso del proceso.

### 5. Relación con mi formación en UX/UI

Como mi objetivo profesional está orientado al diseño UX/UI, encuentro una relación muy fuerte entre estos conceptos y el diseño de experiencias digitales.
Así como el diseño generativo propone pensar primero en el propósito y después en la forma, el diseño centrado en el usuario también comienza entendiendo las necesidades, emociones y comportamientos de las personas antes de construir una interfaz.
Creo que incorporar parte de esta mentalidad generativa puede ayudar a crear experiencias mucho más significativas y humanas. Una interfaz no debería ser únicamente funcional; también debería transmitir intención, personalidad y generar una conexión con quien la utiliza.

### 6. Dudas y Aprendizajes

Uno de los aspectos que más curiosidad me generó fue entender cómo se producen esos sistemas visuales que reaccionan en tiempo real a la música. Al principio no comprendía cómo era posible lograr efectos tan complejos, especialmente aquellos creados con inteligencia artificial.
Después de la explicación entendí que muchas veces no se trata únicamente de IA, sino de combinar herramientas como TouchDesigner, programación, datos en tiempo real y recursos generados con inteligencia artificial para construir sistemas interactivos completos.

### 7. Proyección Personal

Si tuviera que desarrollar un sistema generativo en este momento, definitivamente estaría relacionado con la música.
Me gustaría crear visuales que reaccionen en tiempo real al ritmo, la intensidad y las frecuencias de una canción, inspirándome en algunos de los ejemplos vistos durante la clase, pero incorporando un estilo propio. La música siempre ha sido una de mis mayores fuentes de inspiración, por lo que me parece el punto de partida ideal para seguir explorando el diseño generativo durante esta unidad.


## Primer acercamiento a TouchDesigner

### Conceptos aprendidos

Durante esta actividad tuve mi primer acercamiento a TouchDesigner y entendí por qué es una de las herramientas más utilizadas para crear experiencias interactivas. Más que un programa para hacer efectos visuales, lo veo como una plataforma que permite construir sistemas mediante pensamiento procedural, donde lo importante no es solo el resultado final, sino la forma en la que los datos viajan y se transforman dentro del proyecto.

Uno de los conceptos que más me llamó la atención fue el modelo de datos. Me pareció muy interesante descubrir que existen diferentes familias de operadores (TOP, CHOP, SOP, DAT, entre otros) y que algunas funcionan como los "creadores" del contenido, mientras que otras lo modifican o lo utilizan para producir nuevos resultados. También me sorprendió que prácticamente cualquier fuente de información pueda convertirse en una experiencia interactiva; incluso un ejemplo tan simple como un banano puede terminar siendo el punto de partida para una instalación creativa.

### Reflexión personal

Personalmente siento que trabajar con nodos ofrece muchas ventajas frente a programar todo desde código. Me parece una forma mucho más visual y organizada de construir un sistema, ya que puedo seguir fácilmente el recorrido de la información: de dónde vienen los datos, cómo se procesan y cuál es el resultado que producen. Esa representación gráfica hace que experimentar sea más natural y menos intimidante, especialmente cuando los proyectos comienzan a crecer.

También creo que TouchDesigner puede abrir muchas posibilidades dentro del UX/UI. Probablemente no todas las interfaces necesiten una experiencia creada con esta herramienta, pero justamente ahí está lo interesante: perder el miedo a experimentar. Dependiendo del contexto, podría utilizarse para instalaciones, exhibiciones, experiencias inmersivas o proyectos donde la interacción vaya mucho más allá de una interfaz tradicional. Considero que explorar este tipo de herramientas es una oportunidad para descubrir nuevas formas de diseñar experiencias que sorprendan a los usuarios.


## Construcción de un sistema visual generativo en TouchDesigner

### Exploración del sistema visual

Durante esta actividad construí un sistema visual generativo utilizando TouchDesigner, donde el objetivo principal no era crear una imagen única, sino entender cómo una serie de reglas y parámetros pueden producir diferentes comportamientos visuales.

Al experimentar con los controles del sistema y añadir algunos LFOs para modificar los valores automáticamente, logré crear un efecto que me recordaba a un agujero negro: una especie de campo que se expandía y contraía constantemente, generando una sensación de atracción y movimiento. Después continué explorando la parte visual modificando los colores y creando una inversión cromática cuando el sistema alcanzaba ciertos momentos de su comportamiento, haciendo que la experiencia cambiara sin perder la identidad inicial.

Lo interesante de este proceso fue entender que el resultado no estaba completamente definido desde el inicio. En lugar de diseñar directamente la forma final, estaba diseñando las condiciones que permitían que la forma apareciera.

### Parámetros y experimentación

El elemento que más llamó mi atención fueron los LFOs, ya que permitieron transformar parámetros estáticos en comportamientos dinámicos. Esto me llevó a pensar más en las relaciones matemáticas detrás del movimiento y en cómo pequeñas variaciones dentro de una fórmula pueden cambiar completamente la percepción del resultado.

Aunque al principio las expresiones matemáticas fueron una de las partes más complejas, también fueron una de las más interesantes porque mostraban cómo una operación aparentemente simple podía convertirse en una transformación visual mucho más compleja.

### Relación con el diseño generativo

Esta actividad fue una aplicación directa de la mentalidad generativa vista anteriormente. La intención inicial era generar una experiencia visual dinámica, pero para lograrlo no fue necesario construir cada detalle manualmente. Fue necesario definir entidades, relaciones y reglas que permitieran al sistema evolucionar.

En este caso, la entidad principal eran los campos generados por ruido, mientras que las relaciones estaban dadas por la deformación, el movimiento, el color y la interacción entre parámetros. Los resultados visuales eran simplemente una consecuencia del sistema creado.

Esto me ayudó a entender que el diseñador generativo no necesariamente crea una obra terminada, sino que crea un conjunto de posibilidades. La creatividad está en decidir qué reglas existen, qué elementos permanecen constantes y qué aspectos pueden cambiar.

### Reflexión personal

Una de las mayores dificultades fue pasar de imaginar una idea visual en mi cabeza a encontrar la forma de construirla mediante parámetros y fórmulas. Muchas veces uno tiene una imagen mental del resultado, pero convertir esa intención en reglas concretas requiere otro tipo de pensamiento más lógico y experimental.

Como siguiente paso, me gustaría explorar mucho más la relación entre sonido y visuales generativas. Considero que combinar los campos de ruido con audio podría generar experiencias mucho más inmersivas, donde la música controle directamente el comportamiento del sistema y permita crear visuales únicos para cada momento.
