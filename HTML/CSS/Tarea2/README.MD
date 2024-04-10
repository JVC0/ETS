FLEX


Flex y Grid tienen un potencial grande.


Como Flex lleva más tiempo y ya está bien establecido, dedicaremos nuestros esfuerzos en Flex y veremos que muchos de los conceptos que introduce son aplicables a Grid



Propiedades aplicables al contenedor flex

display: Flex
Lo primero que tenemos que entender es que si establecemos en un contenedor:

display: flex



los objetos hijos directos de ese contenedor serán elementos flex por defecto. Así en el siguiente código se observa que quedan todos los párrafos “repartidos” en el ancho de la fila de forma equilibrada



<!DOCTYPE html>

<html>

<head>

<meta charset="UTF-8" />

<meta name="author" content="juan carlos p.r."/>

<meta name="viewport" content="width=device-width, initial-scale=1.0"/>


<title>inicios con flex</title>

<style type="text/css" >

header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

background: #F6EBC6;

}




</style>

</head>


<body>

<main class="contenedorFlex">

<p>1 Lorem ipsum dolor sit amet, consectetur adipisicing elit. Eum incidunt, nostrum! lorem</p>

<p>2 Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore ipsa laudantium ea.</p>

<p>3 Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam laborum provident pariatur aspernatur? Lorem ipsum dolor sit amet, consectetur adipisicing elit. Id maiores reiciendis quod sit cupiditate debitis amet mollitia, recusandae consequatur alias!</p>

<p>4 Lorem ipsum dolor sit amet, consectetur adipisicing elit. Totam voluptatem tempore blanditiis facere natus.</p>

<p>5 Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptates, animi! Reiciendis, sequi, quasi. Totam, minus. Lorem ipsum dolor sit amet, consectetur adipisicing elit. Voluptatum, eius, velit reiciendis molestiae vitae ipsam.</p>

</main>

</body>

</html>





Observando como nos queda la página vemos que se ha tratado de equilibrar la altura que ocupan todos los párrafos distribuyendo más espacio en ancho a aquellos párrafos que precisan de más espacio. Pero siempre tratando de generar equilibrio



Quizás prefiramos que todas las columnas sean de un ancho parecido. En ese caso, por supuesto que podemos seguir usando el atributo width en los párrafos:

p{

max-width: 23%;

}



Así el nuevo CSS quedaría:


header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;


background: #F6EBC6;

}


p{

max-width: 20%;

border: 1px solid gray;

}





Ahora se puede observar que hay diferencias significativas del tamaño que ocupan en altura un párrafo a otro. Pero el borde de cada párrafo queda perfectamente alineado como si se tratara de una tabla. Observaremos en general, que casi cualquier cosa que quisiéramos hacer con display: table se puede resolver con flex



flex-flow


El comportamiento por defecto en flex es dejar todo distribuido en una única fila. Pero es fácil conseguir que ocupe diferentes filas. Para ello ponemos en el contenedor flex :


flex-flow: row wrap;



La anterior instrucción le dice que se quiere que el flujo dentro de nuestro contenedor sea de izquierda a derecha ( row ) y que si se acaba la fila se distribuya en la siguiente ( wrap )


El nuevo CSS queda:


header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row wrap;

background: #F6EBC6;

}


p{

max-width: 23%;

border: 1px solid gray;

}



Flex ve ahora que puede redistribuir los elementos de una forma más equilibrada. Ocupa para cada elemento el máximo que le hemos permitido ( 23%) y lo que va sobrando lo pone en la siguiente fila




Nuestra forma de escritura natural es de izquierda a derecha, que es el comportamiento que observamos al distribuir los párrafos con flex. Pero el potencial de flex-flow es grande. Por ejemplo, Si así lo quisiéramos podríamos distribuir nuestro contenido al estilo de los que escriben de derecha a izquierda. Para ello usamos: reverse


flex-flow: row-reverse wrap;


Probar la variación en nuestra página y veremos que nos rellena la primera fila de derecha a izquierda y en la segunda fila nos pone el quinto párrafo a la derecha



Como sabemos también hay estilos de escritura de arriba hacia abajo. Ese comportamiento también se puede obtener mediante flex-flow en esta ocasión usaremos:


flex-flow: column wrap;




¿pero y el desbordamiento de antes que saltábamos de fila a la siguiente fila ? Bueno, para conseguir eso debemos tener una altura establecida para nuestro contenedor, ya que las páginas html no tienen contemplado una altura límite


Pongamos en nuestro contenedor flex un height:


.contenedorFlex{

display: flex;

flex-flow: column wrap;

background: #F6EBC6;

height: 400px;

}



Ya aparece de nuevo el desbordamiento para la siguiente columna. Por supuesto también existe la posibilidad de establecer reverse en column:



flex-flow: column-reverse wrap;


justify-content

Para trabajar esta nueva propiedad en nuestro contenedor flex vamos a dejar nuestro CSS de la siguiente forma:


header, section, footer, aside, nav, main, article, figure{

display: block;

}

.contenedorFlex{

display: flex;

flex-flow: row nowrap;

justify-content: flex-start;

background: #F6EBC6;

}


p{

max-width: 15%;

border: 1px solid gray;

}


Analizando lo que hemos puesto tenemos:

flex-flow: row nowrap


que significa que los elementos se distribuyen en fila ( de izquierda a derecha ) y que no salta a la siguiente fila ( nowrap )


En el párrafo hemos especificado un max-width: 15% y así nos garantizamos que hay espacio sin ocupar en la fila para nuestros 5 párrafos


y hemos incorporado una línea nueva:

justify-content: flex-start;



Este es el comportamiento por defecto así que si retiramos esa línea no veremos diferencia


Lo que determina justify-content es la forma en la que va a quedar distribuido nuestro contenido en el eje principal ( en nuestro caso en la fila, ya que hemos escrito: row )


Así flex-start significa que ponga un elemento seguido de otro desde el comienzo


Probemos ahora flex-end:

justify-content: flex-end;


Vemos que es el equivalente si estuviéramos trabajando con texto en lugar de con bloques de un text-align: right



Y si probamos ahora center:

justify-content: center;


Tenemos el equivalente a un text-align: center


Ahora bien, justify-content tiene otas dos opciones. Una que sería

“parecida” a un text-align: justify

justify-content: space-between;


Observar que los párrafos quedan alineado a la izquierda y a la derecha distribuyendo el espacio sobrante en medio


La última opción de justify-content es space-around:

justify-content: space-around;


Este sería equivalente a calcular el espacio sobrante, dividirlo entre nuestros 5 párrafos y que cada uno tuviera ese espacio como “un margen” a izquierda y derecha de cada párrafo. Así cuando aparecen dos párrafos seguido se tiene la sensación del doble de margen que en los párrafos extremos.







align-items

Esta es la última propiedad que vamos a ver que se pueda poner en el contenedor flex


Antes vimos que podemos alinear nuestros elementos ( párrafos en nuestro ejemplo ) a lo largo de nuestro eje principal Y observamos que tiene bastantes posibilidades. Pero adicionalmente flex nos permite alinear nuestros elementos en el segundo eje mediante align-items


Tomaremos como base el siguiente CSS:


header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row wrap;

justify-content: flex-start;

align-items: flex-start;

background: #F6EBC6;

}


p{

max-width: 31%;

border: 1px solid gray;

}


Observar que los párrafos en la vertical comienzan siempre en lo alto de la fila, indistintamente de que llenen o no llenen la fila


Podemos hacer al revés. Que queden alineados en vertical todos los párrafos en la parte inferior de la fila, mediante flex-end

align-items: flex-end;





No está de más que se recuerde lo especial que resultan las alternativas que se están viendo.

Incluso con elementos en linea (inline) no siempre se puede ordenar como uno quiera su posición en vertical. Cuando se está dentro de una tabla existía valign para tal propósito y se pueden hacer cosas similares con el CSS anterior a flex si previamente se hubiera establecido un tamaño (height) en altura del objeto contenedor. Pero dejando aparte a display:table las opciones anteriores son muy inferiores en potencia respecto al ordenamiento en vertical. Algo que suele dar cierto trabajo en diseño de página web y que aquí es extremadamente sencillo es el centrado en vertical de un elemento ( no olvidar que estamos tomando elementos en bloque y posicionándolos allí como queramos ) para ellos usaremos: center;

align-items: center;


Podemos observar que tomando como referencia el elemento de la fila que sea más grande ( y por tanto es el que determina el tamaño de la fila ) los demás elementos quedan centrados en vertical



La última opción que vamos a ver nos permite hacer el efecto de las tablas. De tal forma que cuando una celda crezca en vertical haga que las demás ajusten su tamaño para que todas tengan el mismo tamaño vertical. Para esto usaremos: stretch


align-items: stretch;


Este último es el comportamiento por defecto de align-items









Con esto hemos terminado con las opciones a nivel de contenedor. Las opciones que quedan son para cada elemento en individual






Propiedades aplicables a un elemento FLEX


flex:

Mediante la propiedad: flex podemos conseguir establecer el tamaño inicial de un elemento flex y como se comportará cuando disponga de más o menos espacio para crecer/decrecer


Usaremos el siguiente CSS como base:



header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row wrap;

justify-content: flex-start;

align-items: flex-start;

background: #F6EBC6;

}


p{

flex: 0 0 20%;

border: 1px solid gray;

}



Con lo anterior obtendremos el mismo resultado que si hubiéramos establecido: width: 20%


La tercera posición de la instrucción flex ( en nuestro ejemplo el dato: 20% ) establece el tamaño incial que tendrá el elemento flex. Las otras dos posiciones establecen como se debe comportar para crecer o decrecer. Como hemos establecido 0 en ambas estamos diciendo que no queremos que crezca ni decrezca, así al final hemos tenido el mismo efecto que si hubiéramos escrito width 20%



Veamos como cambia si le permitimos crecer:

flex: 1 0 20%;


Podemos observar que la primera fila ahora se ocupa completamente repartiendo el espacio sobrante entre los 4 elementos mientras que el quinto elemento que es el único de la última fila se expande ocupando el total del espacio disponible.


Vamos a modificar nuestro CSS haciendo que haya un comportamiento diferenciado con el espacio de un párrafo a otro:



header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row wrap;

justify-content: flex-start;

align-items: stretch;

background: #F6EBC6;

}


p:not(:nth-of-type(1)){


border: 1px solid gray;

flex: 1 0 20%;


}


p:nth-of-type(1){

border: 1px solid gray;

flex: 7 0 20%;

}


Todos los elementos empiezan con un espacio del 20% y manejan el espacio sobrante en una proporción de 7partes para el primer párrafo y 1parte para cada uno de los demás elementos


Es fácil observar que el elemento que está solo en la fila le es indiferente que se establezca 1 o 7






Para observar la otra propiedad ( flex-shrink ) en la que se estrecha el espacio a partir de una cantidad inicial usaremos el siguiente CSS:


header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row nowrap;

justify-content: flex-start;

align-items: stretch;

background: #F6EBC6;

}


p:not(:nth-of-type(2)){


border: 1px solid gray;

flex: 0 1 400px;


}


p:nth-of-type(2){

border: 1px solid gray;

flex: 0 5 400px;

}



Todos los párrafos comienzan con 400px y van decrementando su tamaño proporcionalmente siendo el segundo párrafo el que decrementa a mayor velocidad y obteniendo un espacio final más reducido




Con lo que hemos explicado del crecimiento podemos observar que tenemos mediante flex una soloción fácil al problema de establecer un 50% a dos elementos de una página sin que nos afecten los márgenes y demás consideraciones que se pudiera tener cuando utilizamos width.















En el siguiente ejemplo establecemos dos elementos que al final ocupan todo el ancho de forma proporcional:



header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row wrap;

justify-content: flex-start;

align-items: stretch;

background: #F6EBC6;

}


p{


border: 5px solid gray;

margin: 3px;

flex: 1 0 45%;


}



En el ejemplo anterior se ve como los párrafos tienen el mismo tamaño inicial y la misma velocidad de crecimiento, van a terminar ocupando la misma cantidad de espacio final
























align-self

Esta propiedad de un elemento flex ( repetimos, estas dos últimas propiedades que hemos visto son de los elementos flex, no del contenedor flex ) que veremos. Nos permite particularizar el comportamiento en el segundo eje para un elemento en concreto. En el siguiente ejemplo todos los elementos tienen un comportamiento flex-start salvo el tercero que es stretch y el cuarto que es center:


header, section, footer, aside, nav, main, article, figure{

display: block;

}


.contenedorFlex{

display: flex;

flex-flow: row nowrap;

justify-content: space-between;

align-items: flex-start;

background: #F6EBC6;

}


p{


border: 5px solid gray;

margin: 3px;

flex: 1 1 15%;


}


p:nth-of-type(3){

align-self: stretch;

}

p:nth-of-type(4){

align-self: center;

}
















order
La propiedad order nos permite ubicar allí donde queramos cualquier elemento. Debemos de tener en cuenta que por defecto los elementos flex tienen un order: 0 y se van distribuyendo según el flujo normal. Veamos un ejemplo en el que especificamos un order negativo al tercer elemento:

header, section, footer, aside, nav, main, article, figure{

display: block;

}

.contenedorFlex{

display: flex;

flex-flow: row nowrap;

justify-content: space-between;

align-items: flex-start;

background: #F6EBC6;

}

p{


border: 5px solid gray;

margin: 3px;

flex: 1 1 15%;



}



p:nth-of-type(3){

align-self: stretch;

order: -1;

}

p:nth-of-type(4){

align-self: center;

}