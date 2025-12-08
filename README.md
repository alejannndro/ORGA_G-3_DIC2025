Universidad San Carlos de Guatemala

Facultad de Ingeniería

Ingeniería en Ciencias y Sistemas

Organización Computacional

Escuela de vacaciones diciembre 2025

Ing. Carlos Alberto Arias López

Aux. Dilan Conaher Suy Miranda

**Práctica 1:**
**Visualizador de 7 Segmentos**

Integrantes:

- Jose Brayan Arnoldo Murcia López - 3374570262004
- Abner Emanuel Garcia Sandoval - 2791049521905
- Mario Miguel López Sagastume - 3388185962011
- Alejandro José Salazar Ramirez - 3506308361904
- Julio René Morales Posadas - 2977547932008

Guatemala, 09 de diciembre del 2025

# Introducción

En esta práctica se diseñó y construyó un sistema digital combinacional utilizando funciones booleanas simplificadas mediante mapas de Karnaugh. El objetivo principal fue mostrar una palabra de cuatro letras empleando dos displays de 7 segmentos: uno de cátodo común y otro de ánodo común. El display de cátodo mostraba la letra normal, mientras que el de ánodo la representaba en forma de espejo, simulando el funcionamiento de un semáforo digital. El circuito fue primero simulado en Proteus y posteriormente implementado de forma física en protoboard.

# Objetivos
## General
El estudiante diseña e implementa funciones booleanas simplificadas mediante mapas de Karnaugh y álgebra booleana, aplicando términos mínimos y máximos para optimizar circuitos combinacionales en sistemas de visualización digital.

## Específicos

1. El estudiante fabrica y utiliza compuertas lógicas básicas (AND, OR, NOT, NAND, NOR) sobre placas y protoboards, integrando elementos discretos con compuertas TTL para la creación de sistemas híbridos de lógica digital.
2. El estudiante aplica técnicas de simplificación booleana para reducir el uso de compuertas y cableado en la implementación final.

# Funciones Booleanas
Las funciones booleanas son expresiones matemáticas empleadas para describir el comportamiento lógico de un sistema digital. Estas funciones utilizan variables que solo pueden tomar dos valores posibles: 0 (falso) y 1 (verdadero). En el diseño de circuitos combinacionales, las funciones booleanas permiten definir la salida del sistema en función de sus entradas.

 En esta práctica, las funciones booleanas fueron fundamentales para representar cada una de las letras que debían mostrarse en los displays de 7 segmentos. A partir de estas funciones se construyeron tablas de verdad, se aplicaron simplificaciones mediante mapas de Karnaugh y posteriormente se implementaron físicamente utilizando compuertas lógicas.

## ¿Qué es una función booleana?

Una función booleana es una expresión formada por variables binarias y operadores lógico, como:

- AND (*)
- OR (+)
- NOT (¬)

Por ejemplo:

F = A * B + ¬C

> Esta función indica que la salida F será 1 cuando se cumpla A AND B, o cuando C tenga un valor de 0.

Las funciones booleanas permiten:

- Describir el comportamiento de un circuito.
- Determinar qué compuerta lógicas se necesitan.
- Reducir el circuito mediante simplificación.
- Facilitar el diseño en simuladores y su implementación física.

## Tablas de verdad

Una tabla de verdad muestra todas las combinaciones posibles de entradas y la salida correspondiente para cada una.

Ejemplo con dos variables A y B, siendo F = A + B:

| A | B | F = A+B |
|:---:|:---:|:---:|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 1 |

Las tablas de verdad fueron utilizadas en la práctica para determinar qué segmentos del display debían encenderse para formar cada letra.

Tabla de verdad usada para la función de minterminos:

| DECIMAL | LETRA | w | x | y | z |
| :-----: | :---: |:-:|:-:|:-:|:-:|
| 0 | b | 0 | 0 | 0 | 0 |
| 1 | o | 0 | 0 | 0 | 1 |
| 2 | b | 0 | 0 | 1 | 0 |
| 3 | o | 0 | 0 | 1 | 1 |
| 4 | | 0 | 1 | 0 | 0 |
| 5 | | 0 | 1 | 0 | 1 |
| 6 | | 0 | 1 | 1 | 0 |
| 7 | | 0 | 1 | 1 | 1 |
| 8 | | 1 | 0 | 0 | 0 |
| 9 | | 1 | 0 | 0 | 1 |
| 10 | | 1 | 0 | 1 | 0 |
| 11 | | 1 | 0 | 1 | 1 |
| 12 | | 1 | 1 | 0 | 0 |
| 13 | | 1 | 1 | 0 | 1 |
| 14 | | 1 | 1 | 1 | 0 |
| 15 | | 1 | 1 | 1 | 1 |

Dicha tabla serviría para el display de 7 segmentos de cátodo común, por lo cual se buscaban los unos por lo tanto tendríamos los resultados de la siguiente manera:

| a | b | c | d | e | f | g | . |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 |
| 0 | 0 | 1 | 1 | 1 | 0 | 1 | 0 |
| 0 | 0 | 1 | 1 | 1 | 1 | 1 | 0 |
| 0 | 0 | 1 | 1 | 1 | 0 | 1 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |
| 0 | 0 | 0 | 0 | 0 | 0 | 0 | 0 |

Tabla de verdad usada para la función de maxterminos es la misma que la de minterminos, pero lo que cambia es que serviría para el display de 7 segmentos de ánodo común, por lo cual se buscaban los ceros por lo tanto tendríamos los resultados de la siguiente manera:

| a | b | c | d | e | f | g | . |
|:-:|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| 1 | 0 | 0 | 0 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 0 | 1 | 0 | 1 |
| 1 | 0 | 0 | 0 | 0 | 1 | 0 | 1 |
| 1 | 1 | 0 | 0 | 0 | 1 | 0 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |
| 1 | 1 | 1 | 1 | 1 | 1 | 1 | 1 |

## Minterminos y Maxterminos

- Un **mintermino** produce una salida 1 para una sola combinación específica de entrada.
- Un **maxtermino** produce una salida 0 para una sola combinación específica.

Los minterminos se usan para representar funciones en forma suma de productos (SOP). Los maxterminos se usan en forma producto de sumas (POS).

En la práctica:

- El display cátodo fue diseñado usando minterminos.
- El display ánodo fue diseñado usando maxterminos (porque funciona con lógica inversa).

## Simplificación mediante mapas de Karnaugh

Los mapas de Karnaugh permiten reducir una función booleana agrupando minterminos o maxterminos adyacentes.

Ventajas:

- Menos compuertas lógicas.
- Circuitos más simples.
- Menos cables y menor probabilidad de error.

En la práctica se simplificaron las funciones correspondientes a cada segmento del display, lo que redujo el uso de compuertas AND, OR y NOT. En base a las tablas de verdad se encuentran las siguientes funciones sin simplificar para el caso del cátodo común (uso de minterminos) y para el ánodo común (uso de maxterminos).

## Cátodo común

- Segmentos c, d, e y g (no cambian en la tabla, por ende, son el mismo) su función sin simplificar es: F = w’x’y’z’ + w’x’y’z + w’x’yz’ + w’x’yz. Ahora, dicha función se puede simplificar ya sea por algebra booleana o mapas de Karnaugh.
- Segmento f (único que cambia en la tabla de verdad), su función sin simplificar es F = w’x’y’z’ + w’x’yz’.

Mapa de Karnaugh para segmentos c, d, e y g (son los mismos valores en las tablas de verdad, por ende, tienen el mismo mapa de Karnaugh):

||yz|||||
|:-:|:-:|:-:|:-:|:-:|:-:|
|wx||**00**|**01**|**11**|**10**|
||**00**|1|1|1|1|
||**01**|0|0|0|0|
||**11**|0|0|0|0|
||**10**|0|0|0|0|

Como se ve en el mapa, tanto w’ como x’ no cambian, pero y y z si cambian, por lo cual no se toman en cuenta en la función, la cual luego de ver el mapa queda una versión simplificada de F = w’x’.

El único que cambia es el del segmento f, su mapa de Karnaugh es:

||yz|||||
|:-:|:-:|:-:|:-:|:-:|:-:|
|wx||**00**|**01**|**11**|**10**|
||**00**|1|0|0|1|
||**01**|0|0|0|0|
||**11**|0|0|0|0|
||**10**|0|0|0|0|

Como se ve en el mapa, tanto w’ como x’ y z’ no cambian, pero si cambia y, por lo cual no se toma en cuenta en la función, la cual luego de ver el mapa queda una versión simplificada de F = w’x’z’.

## Ánodo común

- Segmentos c, d, e y g (no cambian en la tabla, por ende, son el mismo) su función sin simplificar es: F = (w+x+y+z)*(w+x+y+z’)*(w+x+y’+z)*(w+x+y’+z’). Ahora, dicha función se puede simplificar ya sea por algebra booleana o mapas de Karnaugh.
- Segmento f (único que cambia en la tabla de verdad), su función sin simplificar es F = (w+x+y+z)*(w+x+y’+z).
- 
Mapa de Karnaugh para segmentos c, d, e y g (son los mismos valores en las tablas de verdad, por ende, tienen el mismo mapa de Karnaugh):

||yz|||||
|:-:|:-:|:-:|:-:|:-:|:-:|
|wx||**00**|**01**|**11**|**10**|
||**00**|0|0|0|0|
||**01**|1|1|1|1|
||**11**|1|1|1|1|
||**10**|1|1|1|1|

En este caso lo que se tiene es que por medio de Karnaugh se puede simplificar, pero para mostrar otra forma se puede usar álgebra booleana o algebra de bool como es su sinónimo:

F = (w + x + y + z) ∗ (w + x + y + z’) ∗ (w + x + y’ + z) ∗ (w + x + y’ + z’)

Se trabaja por dos paréntesis:

F = (w + x + y + z) ∗ (w + x + y + z’) ∗ (w + x + y’ + z) ∗ (w + x + y’ + z’)

Se usa ley distributiva para el primer par de paréntesis:
(w + x + y + z) ∗ (w + x + y + z’) →

(𝑤 ∗ 𝑤 + 𝑤 ∗ 𝑥 + 𝑤 ∗ 𝑦 + 𝑤 ∗ 𝑧′) + (𝑥 ∗ 𝑤 + 𝑥 ∗ 𝑥 + 𝑥 ∗ 𝑦 + 𝑥 ∗ 𝑧′) + (𝑦 ∗ 𝑤 + 𝑦 ∗ 𝑥 + 𝑦 ∗ 𝑦 + 𝑦 ∗ 𝑧′) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦 + 𝑧 ∗ 𝑧′)

Sabiendo que a * a = a, a * a’ = 0 y a + 0 = a en álgebra booleana, se simplifican algunas cosas:

(𝑤 + 𝑤 ∗ 𝑥 + 𝑤 ∗ 𝑦 + 𝑤 ∗ 𝑧′) + (𝑥 ∗ 𝑤 + 𝑥 + 𝑥 ∗ 𝑦 + 𝑥 ∗ 𝑧′) + (𝑦 ∗ 𝑤 + 𝑦 ∗ 𝑥 + 𝑦 + 𝑦 ∗ 𝑧′) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦)

Ahora, si se agarra por factores comunes, se pueden hacer ciertas cosas, pero aprovechando una ley muy importante la cual es la ley de dominación al cual dice que a + 1 = 1, donde 1 es todo y sin importar con que este, siempre que haya una o varias cosas + 1 eso siempre será 1; también a * 1 = a en álgebra booleana por lo cual se tiene:

(𝑤 ∗ (1 + 𝑥 + 𝑦 + 𝑧′)) + (𝑥(𝑤 + 1 + 𝑦 + 𝑧′)) + (𝑦(𝑤 + 𝑥 + 1 + 𝑧′)) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦) →

(𝑤 ∗ (1)) + (𝑥 ∗ (1)) + (𝑦 ∗ (1)) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦) →

(𝑤) + (𝑥) + (𝑦) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦)

Los paréntesis pueden quitarse ya que solo quedan sumas:

𝑤 + 𝑥 + 𝑦 + 𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦

Reordenando términos y agrupando por factores comunes, se pueden aplicar las leyes de antes:

𝑤 + 𝑧 ∗ 𝑤 + 𝑥 + 𝑧 ∗ 𝑥 + 𝑦 + 𝑧 ∗ 𝑦 →

𝑤 ∗ (1 + 𝑧) + 𝑥 ∗ (1 + 𝑧) + 𝑦 ∗ (1 + 𝑧) →

𝑤 ∗ (1) + 𝑥 ∗ (1) + 𝑦 ∗ (1) →

𝑤 + 𝑥 + 𝑦

Pero estos antes eran dos paréntesis, y lo que queda debe multiplicarse a los otros dos paréntesis, entonces se agrupan y reescriben:

F = (w + x + y) ∗ (w + x + y’ + z) ∗ (w + x + y’ + z’)

Trabajando el lado azul de la misma manera:

(w + x + y′ + z) ∗ (w + x + y′ + z’) →

(𝑤 ∗ 𝑤 + 𝑤 ∗ 𝑥 + 𝑤 ∗ 𝑦′ + 𝑤 ∗ 𝑧′) + (𝑥 ∗ 𝑤 + 𝑥 ∗ 𝑥 + 𝑥 ∗ 𝑦′ + 𝑥 ∗ 𝑧′) + (𝑦′ ∗ 𝑤 + 𝑦′ ∗ 𝑥 + 𝑦′ ∗ 𝑦′ + 𝑦′ ∗ 𝑧′) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦′ + 𝑧 ∗ 𝑧′)

Usando las leyes de a * a = a, a + 1 = 1, a * 1 = a, a * a’ = 0 y a + 0 = a, se simplifica lo siguiente:

(𝑤 + 𝑤 ∗ 𝑥 + 𝑤 ∗ 𝑦′ + 𝑤 ∗ 𝑧′) + (𝑥 ∗ 𝑤 + 𝑥 + 𝑥 ∗ 𝑦′ + 𝑥 ∗ 𝑧′) + (𝑦′ ∗ 𝑤 + 𝑦′ ∗ 𝑥 + 𝑦′ + 𝑦′ ∗ 𝑧′) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦′) →

(𝑤 ∗ (1 + 𝑥 + 𝑦′ + 𝑧′)) + (𝑥 ∗ (𝑤 + 1 + 𝑦′ + 𝑧′)) + (𝑦′ ∗ (𝑤 + 𝑥 + 1 + 𝑧′)) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦′) →

(𝑤 ∗ (1)) + (𝑥 ∗ (1)) + (𝑦′ ∗ (1)) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦′) →

(𝑤) + (𝑥) + (𝑦′) + (𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦′)

De igual manera se separan los paréntesis ya que solo quedan sumas, posterior se aplican el restode leyes o reordenaciones antes usadas:

𝑤 + 𝑥 + 𝑦′ + 𝑧 ∗ 𝑤 + 𝑧 ∗ 𝑥 + 𝑧 ∗ 𝑦′ →

𝑤 + 𝑧 ∗ 𝑤 + 𝑥 + 𝑧 ∗ 𝑥 + 𝑦′ + 𝑧 ∗ 𝑦′ →

𝑤 ∗ (1 + 𝑧) + 𝑥 ∗ (1 + 𝑧) + 𝑦′ ∗ (1 + 𝑧) →

𝑤 ∗ (1) + 𝑥 ∗ (1) + 𝑦′ ∗ (1) →

𝑤 + 𝑥 + 𝑦′

Al simplificar esos dos paréntesis azules solo queda multiplicar dicho resultado por los rojos:

F = (w + x + y) ∗ (w + x + y′)

Volviendo a aplicar todas las leyes, reordenamientos se obtiene una versión aún más simplificada:

(w ∗ w + w ∗ x + w ∗ y′) + (x ∗ w + x ∗ x + x ∗ y′) + (y ∗ w + y ∗ x + y ∗ y′)

Cambiando el color a negro todo, se continúan las operaciones:

(w + w ∗ x + w ∗ y′) + (x ∗ w + x + x ∗ y′) + (y ∗ w + y ∗ x) →

(w ∗ (1 + x + y′)) + (x ∗ (w + 1 + y′)) + (y ∗ w + y ∗ x) →

(w ∗ (1)) + (x ∗ (1)) + (y ∗ w + y ∗ x) →

(w) + (x) + (y ∗ w + y ∗ x) →

(w) + (x) + (y ∗ w + y ∗ x) →

w + x + y ∗ w + w ∗ x →

w + y ∗ w + x + w ∗ x →

w ∗ (1 + y) + x ∗ (1 + w) →

w ∗ (1) + x ∗ (1) →

w + 𝑥 →

F = (w + x)

Con el mapa de Karnaugh se veía que ni w’ ni x’ cambiaban, y como son maxterminos la función invierte el complemento entonces se veía que F = w + x, solo que se corrobora con el álgebra de bool.

Para el segmento b su mapa de Karnaugh es el siguiente:

||yz|||||
|:-:|:-:|:-:|:-:|:-:|:-:|
|wx||**00**|**01**|**11**|**10**|
||**00**|0|1|1|0|
||**01**|1|1|1|1|
||**11**|1|1|1|1|
||**10**|1|1|1|1|

Usando a favor el mapa se ve que, tanto w’, x’ y z’ no cambian, al ser maxterminos son productos de sumas (POS) entonces los ceros se vuelven unos y queda la función como: F = (w + x + z).

# Diagramas de diseño

# Materiales utilizados y presupuesto
|Nombre|Precio(Q)|Cantidad|Total(Q)|
|:-:|:-:|:-:|:-:|
|Fuente de alimentación para protoboard|25.00|1|25.00|
|Display de 7 segmentos ánodo común|5.00|1|5.00|
|Display de 7 segmentos cátodo común|5.00|1|5.00|
|DIP Switch de 4 botones|5.00|1|5.00|
|Resistencias de diversos valores|1.50|10|15.00|
|Compuerta lógica OR (para el display ánodo)|8.00|1|8.00|
|Compuerta lógica NOT|9.00|1|9.00|
|Compuerta lógica AND (para el display cátodo)|7.00|1|7.00|
|Cables de red recortados y adaptados|3.00|1|3.00|
|Protoboard|70.00|2|140.00|
|**Total (Q)**|||222.00|

Con el diseño listo, materiales el montaje quedó de la siguiente manera:

![circuito](/img/circuito.jpg)

Las resistencias identificadas:

![circuito con resistencias identificadas](/img/circuitoR.jpg)

El resto de componentes identificados:

![circuito con componentes identificados](/img/circuitoC.jpg)

# Roles de trabajo

- **José Murcia:** Formación de las letras en los displays mediante tablas de verdad.
- **Mario López:** Simplificación de mapas de Karnaugh, uso de GitHub y documentación completa en Markdown.
- **Mario López / Julio Morales:** Construcción del circuito en Proteus.
- **Emanuel García / José Murcia / Mario López:** Obtención de materiales para la práctica.
- **Emanuel García / José Murcia / Alejandro Salazar / Julio Morales:** Armado del circuito físico en protoboard.
- **Alejandro Salazar / Emanuel García / José Murcia / Julio Morales:** Elaboración de informe en sucio como guía para el contenido del Markdown.

# Conclusiones

1. Se logró diseñar e implementar funciones booleanas simplificadas mediante mapas de Karnaugh, optimizando el circuito combinacional y permitiendo que ambos displays mostraran correctamente las letras requeridas, cumpliendo plenamente el propósito de visualización digital del proyecto.
2. Se fabricaron e integraron compuertas lógicas básicas utilizando transistores y resistencias, combinándolas con compuertas TTL. Esto permitió comprobar en la práctica el funcionamiento de un sistema híbrido de lógica digital y reforzó el entendimiento del comportamiento de cada tipo de compuerta.
3. La simplificación booleana aplicada redujo significativamente el número de compuertas y conexiones necesarias. Esto dio como resultado un circuito más eficiente, ordenado y confiable, demostrando la importancia de los mapas de Karnaugh en el diseño digital.