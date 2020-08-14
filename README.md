# **ANTIPATRONES DE DISEÑO**

una buena estructura de software es esencial para la extensión y el mantenimiento del sistema. El desarrollo de software es una actividad caótica, por lo tanto, la estructura implementada de los sistemas tiende a alejarse de la estructura planificada según lo determinado por la arquitectura, el análisis y el diseño.

La refactorización de software es un enfoque eficaz para mejorar la estructura del software. La estructura resultante no tiene que parecerse a la estructura planificada original.

La estructura cambia porque los programadores aprenden restricciones y enfoques que alteran el contexto de las soluciones codificadas. Cuando se utiliza correctamente, la refactorización es ua actividad natural en el proceso de programación.

# **Codigo muerto**

Este antipatron es la acumulacion de clases que no cumplen con una funcionalidad dentro del sistema dificultando su entendimiento para futuros desarrollos.

**Nombre antipatrón**: Lava Flow

**También conocido como**: Dead Code

**Escala más frecuente**: aplicación.

**Nombre de la solución refactorizado**: Gestión de la configuración arquitectónica.

**Tipo de solución refactorizada**: proceso.

**Causas principales**: avaricia, codicia, pereza.

**Fuerzas desequilibradas**: gestión de la funcionalidad, rendimiento, complejidad.

## **ANTECEDENTES**


En una expedición de minería de datos, se comenzó a buscar información para desarrollar una interfaz estándar o base para un tipo particular de sistema. El sistema que se estaba extrayendo era muy similar a los que que se esperaba eventuualmente que admitiera el la interfaz en la cual se había trabajado. También era un sistema de investigación y muy complejo,se realizaron entrevistas a muchos de los desarrolladores sobre ciertos componentes de la enorme cantidad de páginas de código impresas para el trabajo que se estaba realizando.

Los desarrolladores siempre respodían que no sabían para que se usaba una determinada clase y que estaba modulada incluso antes de que el desarrollador empezara a trabajar en el proyecto. Gradualmente se dieron cuenta de que entre el 30 y el 50 por ciento del código real que comprendía este complejo sistema no era entendido ni documentado por nadie que trabajara en él.

Además se llego a la conclusión de que el código cuestionable realmente no tenía ningún propósito en el sistema actual; más bien, estaba allí de intentos o enfoques anteriores de desarrolladores que se habían ido. El personal actual, aunque muy inteligente, se mostraba reacio a modificar o eliminar el código que no escribían o no conocían el propósito, por temor a romper algo y no saber por qué o cómo solucionarlo.

En este punto,se comenzó a llamar a esas manchas de código "lava", refiriéndonos a la naturaleza fluida en la que se originaron en comparación con la dureza del basalto y la dificultad para eliminarlo una vez que se solidificó. Es allí en donde se identifica y se reconoce un nuevo antipatrón , incluso casi un año después, y después de varias expediciones de minería de datos y esfuerzos de diseño de interfaces, varios desarrolladores se habían encontrado con el mismo patrón con tanta frecuencia que habitualmente se referían a él como  Lava Flow en todo el departamento.

## **SÍNTOMAS Y CONSECUENCIAS**

- Variables injustificables frecuentes y fragmentos de código en el sistema.
- Funciones, clases o segmentos complejos indocumentados que parecen importantes y que no se relacionan claramente con la arquitectura del sistema.
- Arquitectura de sistema muy flexible y "en evolución".
- Bloques completos de código comentado sin explicación ni documentación.
- Muchas áreas de código "en proceso de cambio" o "por reemplazar".
- Código no utilizado (muerto), recién dejado.
- Interfaces no utilizadas, inexplicables u obsoletas ubicadas en archivos de encabezado.
- Si no se elimina el código de Lava Flow existente, puede continuar proliferando a medida que el código se reutiliza en otras áreas.
- Si no se controla el proceso que conduce a Lava Flow, puede haber un crecimiento exponencial ya que los desarrolladores sucesivos, demasiado apresurados o intimidados para analizar los flujos originales, continúan produciendo nuevos flujos secundarios mientras tratan de trabajar alrededor de los originales. el problema.
- A medida que los flujos se componen y endurecen, rápidamente se vuelve imposible documentar el código o comprender su arquitectura lo suficiente como para realizar mejoras.

## **SOLUCIÓN**


Solo hay una forma infalible de prevenir este antipatrón: 

- Asegurarse de que la arquitectura de sonido precede al desarrollo del código de producción. Esta arquitectura debe estar respaldada por un proceso de administración de configuración que garantice el cumplimiento de la arquitectura y se adapte a la "misión lenta" (requisitos cambiantes).

- Si la consideración de la arquitectura no se modifica por adelantado, en última instancia, se desarrolla un código que no es parte de la arquitectura de destino y, por lo tanto, es redundante o está muerto. Con el tiempo, el código muerto se vuelve problemático para el análisis, la prueba y la revisión.

- En los casos en los que Lava Flow ya existe, la cura puede ser dolorosa. Un principio importante es evitar cambios de arquitectura durante el desarrollo del proyecto. En particular, esto se aplica a la arquitectura computacional, las interfaces de software que definen la solución de integración de sistemas. La gerencia debe posponer el desarrollo hasta que se haya definido una arquitectura clara y se haya difundido a los desarrolladores.

  La definición de la arquitectura puede requerir una o más actividades de descubrimiento del sistema. El descubrimiento del sistema es necesario para localizar los componentes que realmente se utilizan y son necesarios para el sistema. El descubrimiento del sistema también identifica aquellas líneas de código que se pueden eliminar de forma segura. Esta actividad es tediosa; puede requerir las habilidades de investigación de un detective de software experimentado.

- A medida que se elimina el código muerto sospechoso, se introducen errores. Cuando esto suceda, resista la tentación de corregir inmediatamente los síntomas sin comprender completamente la causa del error. Estudie las dependencias. Esto le ayudará a definir mejor la arquitectura de destino.

- Para evitar Lava Flow, es importante establecer interfaces de software a nivel de sistema que sean estables, bien definidas y claramente documentadas. La inversión inicial en interfaces de software de calidad puede producir grandes dividendos a largo plazo en comparación con el costo de eliminar los glóbulos endurecidos del código Lava Flow.

  Herramientas como el sistema de control de código fuente (SCCS) ayudan en la gestión de la configuración. SCCS se incluye con la mayoría de los entornos Unix y proporciona una capacidad básica para registrar historiales de actualizaciones en archivos controlados por configuración.





# Spaghetti
Bien, muy posiblemente nos podremos haber encontrado con código spaghetti y nunca nos dimos cuenta, personalmente, si me lo he encontrado y no tenia ni idea de que lo pudiera clasificar de esa forma. Para lograr entenderlo imaginemos un plato de spaghetti... está todo revuelto, ¿verdad? y muy posiblemente el plato este sucio, sucio por la salsa, de pronto por la grasa, si este tiene albóndigas también, en fin... nos encontramos con tremendo lio, además, tratemos de separarlo y entenderlo, con esto ultimo me refiero a deducir de donde viene cada spaguetti, con quien se relaciona. Espero mediante esta análogia ya te este imaginando a que se refiere el código spaghetti.



Bien, el código spagghetti se caracteriza por que, es eso... un plato de spaghetti, es decir, podemos encontrarnos en un mismo archivo, diferente lenguajes juntos, clases mal organizadas, rompiendo principios de diseño de forma absurda, en fin, ni siquiera el código spaghetti lo podemos considerar una mala practica de programación, por que muchos programadores afirman que es peor que esto. Por ejemplo, nos encontramos con un diseño de una pagina web, y al analizar su codigo nos damos cuenta de que el programador situó tanto sentencias sql, como estilos, sentencias de javascript y html, todo en un mismo archivo jsp por ejemplo, todo esto obedece a clasificarse como codigo spaghetti.

No es solo esto, además el código se vuelve difícil de mantener, ya que, en primer lugar puede costar entenderlo y en segundo lugar, todo esta tan acoplado que un mínimo cambio dañaría por completo el software.
## ¿Como evitarlo?

Principalmente, realizando un buen diseño de software desde el principio, una buena técnica para evitar este tipo de código es usar patrones y principios de diseño, haciendo un software con una alta cohesión, es decir que cada modulo tenga mucha relación con sus funcionalidades y mantenga una sola responsabilidad y por otro lado que este código tenga un acoplamiento bajo, es decir que la relación que exista entre sus módulos no sea mucha, esto para evitar muchas dependencias en el código.


# Blob

Este antipatron ocurre cuando un programador no conoce el paradigma orientado a objetos y tiende a poner todos los atributos y objetos en la misma clase, es tambien conocida como la clase Dios.

**Nombres Alternativos:**Clase Dios,  Winnebago  

**Sinopsis:** Consiste en una clase o módulo que monopoliza las responsabilidades de la aplicación. Creando un programa en el que se evidencia una gran cantidad de líneas, sin una adecuada delegación entre clases. Es por esto que mientras hay una clase omnipotente que se ejecuta la mitad del programa, mientras que la mayoría de los demás objetos solo contienen datos o ejecutan procesos simples.

**Causas Raíces:** Realizar un código con prisa, la pereza, y la influencia de un diseño procedural.

**Consecuencias:** Se presenta un código desorganizado y fuertemente interdependendiente.

**Solucion:** La solución incluye
refactoring para la distribución de responsabilidades logrando así el aislamiento de los
efectos de cambio.
**Fuerzas desequilibradas:** Gestión de la funcionalidad, el rendimiento y la complejidad



## Origen del Nombre
El nombre de este patrón viene de una película en la que un gran monstruo al comerse a cada víctima va aumentando de tamaño, tanto así que amenaza con destruir al mundo con su gran tamaño. 

La película es una buena analogía por que este patrón consume arquitecturas enteras orientadas a objetos.

## **Síntomas y Consecuencias**
* Suele verse presente en una clase que lleve una vastta cantidad de atributos y métodos, o ambos.
Una clase con 60 o más atributos y métodos usualmente indica la presencia de este anti-patrón.
* Una falta de cohesión de los atributos y operaciones hace evidenciar este patrón. Una colección dispar de atributos y operaciones no relacionados y encapsulados en una sola clase.
* Una simple clase controladora con muchas asociaciones.
* Ausencia del paradigma de Programación Orientada a Objetos, así mismo no se evidencia una modularidad y un encapsulamiento. Limitando a casi nula las ventajas que tiene el paradigma, y por esto al no cumplir con el principio de Abierto/ Cerrado, al momento de querer editar una clase, se termina editando todo el software.
* Se vuelve inutilizable.
* Consume memoria en exceso.

## **Típicas Causas**
* Falta de una arquitectura orientada a objetos.  Probablemente quien diseño la arquitectura no tiene los adecuados conocimientos para entender los principios de una arquitectura orientada a objetos. Alternativamente el equipo puede tener debilidad en habilidades de abstracción.
* En proyectos iterativos, los desarrolladores tienden a agregar pequeñas piezas de funcionalidad a las clases existentes, en lugar de agregar nuevas clases, o revisar y refactorizar la jerarquía de clases para una asignación de responsabilidades más efectiva.
* Desastre ya especificado. A veces, el anti-patrón resulta de la forma en que se especifican los requisitos. Si los requisitos dictan una solución de tipo procedimental, entonces se pueden hacer compromisos arquitectónicos durante el análisis de requisitos que son difíciles de cambiar. Definir la arquitectura del sistema como parte del análisis de requisitos suele ser inapropiado.

## **Solución Refactorizada:**

 La clave es separar el comportamiento del God Class. Puede ser apropiado reasignar el comportamiento y la responsabilidad a algunos de los objetos de datos encapsulados de forma que estos objetos sean más independiente y la God Class menos compleja.

 ## **GoldenHammer**

Este antipatrón ocurre cuando el desarrollador o desarrolladores se aferran a una unica herramienta o lenguaje de programación para intentar solucionar todos los problemas, sin estudiar mejores alternativas.

# ANTIPATRÓN GOLDEN HAMMER O VARITA MAGICA

Este AntiPatron resulta en la aplicación incorrecta de una herramienta o concepto favorecido. Los desarrolladores y gerentes se sienten cómodos con un enfoque existente y no están dispuestos a aprender y aplicar uno que se adapte mejor. 

Esta asociado con aferrarse a un paradigma, para solucionar todos los problemas que se nos presenten al desarrollar sistemas, como el usar siempre un mismo lenguaje cuando no es el mejor pues cada lenguaje tiene sus limitaciones y sus beneficios.

## Causas 

- Cuando en varios éxitos han utilizado un enfoque particular.
Se han realizado grandes inversiones en formación y/o experiencia en un producto o tecnología. Se logra que el desarrollador siga solamente una linea.

- El grupo está aislado de la industria o de otras empresas.
- Confianza en características de productos propietarios que no están disponibles en otros productos de la industria.

## Consecuencias

- Herramientas y productos idénticos se utilizan para una amplia gama de productos conceptualmente diversos.
- Las soluciones tienen menor rendimiento, escalabilidad, etc. en comparación con otras soluciones de la industria.
  
- La arquitectura del sistema se describe mejor mediante un producto, un conjunto de aplicaciones o un conjunto de herramientas de proveedor en particular.
- Los desarrolladores debaten los requisitos del sistema con los analistas de sistemas y los usuarios finales, con frecuencia abogando por requisitos que son fácilmente acomodados por una herramienta en particular y los alejan de las áreas donde la herramienta adoptada es insuficiente.
- Los desarrolladores se aíslan de la industria. Demuestran una falta de conocimiento y experiencia con enfoques alternativos.
- Los requisitos no se cumplen plenamente, en un intento de aprovechar la inversión existente.
- Los productos existentes dictan el diseño y la arquitectura del sistema.
- El nuevo desarrollo depende en gran medida de un producto o tecnología de proveedor específico.

## Posibles soluciones

La mayor prevencion para no aplicar el golden hammer  es la exploracion de nuevas tecnologias al igual que se debe tratar de conseguir un mayor compromiso por parte de la administración en el desarrollo profesional de sus desarrolladores, junto con una estrategia de desarrollo que requiere límites de software explícitos para permitir la migración de tecnología.
