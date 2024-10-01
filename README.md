# Graph

## El presente trabajo analiza las tomas de desiciones por parte del consejo de seguridad de la ONU desde el 2017 hasta el 2022, para en análisis lo desarrolla a traves de graph para encontrar relaciones entre los votantes. 

## La base datos se formo a partir de un análisis de las votaciones, las cuales habían algun tipo de abstención o voto en contra de la resolución, con la finalidad de encontrar algún tipo de tendencia entre los votantes, en tal sentido se crearon dos modelos: 

1. El primero modelo muestra la relación entre los Estados que votan a favor de las nociones
2. El segundo modelo muestra la relación entre los Estados que se abstienen en las votaciones

## Resultados del primer model:

1. Conectividad

is_connected(g_1): Esta función verifica si el grafo g_1 es completamente conectado, es decir, si existe un camino entre todos los nodos de la red.
Resultado: [1] TRUE: Significa que el grafo g_1 es completamente conectado, por lo que todos los nodos pueden llegar a todos los demás, directa o indirectamente.

2. Componentes de la red

components(g_1)$no: Esta función cuenta el número de componentes conectados en el grafo.
Resultado: [1] 1: Significa que solo hay un componente conectado en la red, lo que implica que todos los nodos pertenecen al mismo grupo y están conectados de alguna forma (directa o indirecta). No hay subredes aisladas.

3. Distancia media

mean_distance(g_1, directed = FALSE): Calcula la distancia media entre todos los pares de nodos en el grafo. La distancia entre dos nodos es la longitud del camino más corto que los conecta.
Resultado: [1] 1.56871: Indica que, en promedio, la distancia más corta entre dos nodos es de 1.57 pasos. Esto es útil para entender cuán "compacta" es la red; cuanto menor sea este valor, más cercanos estarán entre sí los nodos en promedio.

4. Densidad de la red

edge_density(g_1): Calcula la densidad del grafo, que mide cuántas conexiones (aristas) hay en la red en relación con el número máximo posible de conexiones.
Resultado: [1] 2.887949: Parece que este valor es más alto de lo esperado, ya que la densidad generalmente está entre 0 y 1. Esto puede indicar que hay algún problema con el cálculo o el valor está normalizado de una manera diferente (podrías revisar la estructura del grafo).

## Resultados del segundo modelo:

1. Conectividad

is_connected(g): Esta función verifica si todos los nodos en el grafo g están conectados entre sí, ya sea directa o indirectamente.
Resultado: [1] FALSE: Esto indica que el grafo g no está completamente conectado. En otras palabras, hay nodos o grupos de nodos que no tienen un camino hacia otros nodos, es decir, la red está fragmentada.

2. Componentes de la red

components(g)$no: Esta función cuenta cuántos componentes conectados tiene el grafo. Un componente es un grupo de nodos donde existe un camino entre cada par de nodos.
Resultado: [1] 2: Esto indica que la red está dividida en 2 componentes conectados, lo que significa que existen dos grupos de nodos en la red que están conectados internamente, pero no hay conexiones entre estos grupos. Esta es la razón por la que el grafo no es completamente conectado.

3. Distancia media

mean_distance(g, directed = FALSE): Calcula la distancia media entre todos los pares de nodos en la red, considerando caminos no dirigidos.
Resultado: [1] 1.961039: La distancia media entre los nodos es de aproximadamente 1.96 pasos. Esto sugiere que, en promedio, la mayoría de los nodos están relativamente cerca, pero dado que la red no está completamente conectada, esta media se calcula solo dentro de los componentes conectados. Este valor es más alto que en el primer modelo, lo que indica que los nodos están un poco más dispersos en comparación con el grafo completamente conectado del primer ejemplo.

4. Densidad de la red

edge_density(g): Mide la proporción de conexiones existentes en la red en relación con el número máximo posible de conexiones.
Resultado: [1] 0.4894737: La densidad es aproximadamente 0.49, lo que significa que la red tiene casi el 49% de las conexiones posibles entre nodos. Esto indica una red moderadamente conectada, pero no completamente saturada de enlaces. Dado que hay dos componentes en la red, no es posible que todos los nodos estén conectados entre sí, lo que también influye en esta densidad más baja en comparación con un grafo completamente conectado.

## Link del trabajo

https://qo-dc.github.io/Graph/Index.html

## Comentarios del trabajo 

Al analizar los patrones de votación en instancias internacionales, se observa una clara alineación entre Rusia y China, dos potencias que, a menudo, se abstienen o votan en contra de las resoluciones lideradas por Estados Unidos. Esta tendencia refleja su oposición a la hegemonía estadounidense y su búsqueda de un orden multipolar, un fenómeno ya señalado por autores como Ikenberry (2008) y Mearsheimer (2014), quienes destacan cómo estos Estados, etiquetados como rivales estratégicos de EE. UU., se posicionan en el escenario internacional como contrapesos a las estructuras de poder dominadas por Occidente.

La postura de Rusia y China en las votaciones internacionales no solo subraya una competencia geopolítica, sino también una resistencia ideológica. Ambos Estados, desde una perspectiva realista de las relaciones internacionales, adoptan una actitud "revisionista" (Schweller, 1994), en la que buscan desafiar el statu quo impuesto por las potencias occidentales. Sin embargo, sus motivaciones y estrategias divergen en ciertos aspectos cruciales. Rusia, fiel a su tradición diplomática de no intervención en asuntos soberanos, promueve constantemente una política exterior basada en los principios de no injerencia y respeto a la soberanía, tal como se expone en su adherencia a los principios westfalianos (Tsygankov, 2012). Esta postura es parte integral de su discurso conservador, que rechaza cambios abruptos en el orden internacional.

Por otro lado, China, si bien comparte con Rusia el rechazo a la intervención militar en conflictos ajenos a su región de influencia, ha mostrado una mayor flexibilidad en algunos temas sociales, como la aceptación de la inclusión de un análisis de perspectiva de género en ciertos debates internacionales. Este enfoque refleja una estrategia más pragmática, donde China busca proyectarse como una potencia responsable y moderna en los foros globales, sin comprometer su política de no intervención militar (Zhang, 2015).

La divergencia entre Rusia y China en estos temas pone de relieve sus diferentes trayectorias históricas y su manera de interactuar con el orden internacional. Mientras Rusia parece enfocarse en mantener un discurso conservador, alineado con los principios de soberanía y no injerencia, China busca equilibrar su imagen de potencia emergente con un compromiso selectivo en temas globales, lo que le permite expandir su influencia sin recurrir al uso de la fuerza.

## Bibliografía 

Ikenberry, G. John. (2008). The Rise of China and the Future of the West: Can the Liberal System Survive? Foreign Affairs, 87(1), 23-37.

Mearsheimer, John J. (2014). The Tragedy of Great Power Politics. W.W. Norton & Company.

Schweller, Randall L. (1994). Bandwagoning for Profit: Bringing the Revisionist State Back In. International Security, 19(1), 72-107.

Tsygankov, Andrei P. (2012). Russia and the West from Alexander to Putin: Honor in International Relations. Cambridge University Press.

Zhang, Yongjin. (2015). China in International Society since 1949: Alienation and Beyond. Palgrave Macmillan.

## El enlace de donde se extrajo los datos necesarios para la elaboración de la data 

https://main.un.org/securitycouncil/es/content/voting-system
