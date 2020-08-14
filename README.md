# **ANTIPATRONES DE DISEÑO**

## **Codigo muerto**

Este antipatron es la acumulacion de clases que no cumplen con una funcionalidad dentro del sistema dificultando su entendimiento para futuros desarrollos.

### **Sintomas y Consecuencias**

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

### **¿Como repararlo?**

Una manera de evitar el lava Flow es seguir un desarrollo estructurado y documentado.

Cuando el código está en continuo cambio es necesario quitar las partes desactualizadas para evitar código muerto.

Una vez aparece este antipatrón, la solución es realmente costosa ya que es difícil saber cuales son los componentes que se utilizan en un código que apenas conoces.


## Spaghetti
Bien, muy posiblemente nos podremos haber encontrado con código spaghetti y nunca nos dimos cuenta, personalmente, si me lo he encontrado y no tenia ni idea de que lo pudiera clasificar de esa forma. Para lograr entenderlo imaginemos un plato de spaghetti... está todo revuelto, ¿verdad? y muy posiblemente el plato este sucio, sucio por la salsa, de pronto por la grasa, si este tiene albóndigas también, en fin... nos encontramos con tremendo lio, además, tratemos de separarlo y entenderlo, con esto ultimo me refiero a deducir de donde viene cada spaguetti, con quien se relaciona. Espero mediante esta análogia ya te este imaginando a que se refiere el código spaghetti.



Bien, el código spagghetti se caracteriza por que, es eso... un plato de spaghetti, es decir, podemos encontrarnos en un mismo archivo, diferente lenguajes juntos, clases mal organizadas, rompiendo principios de diseño de forma absurda, en fin, ni siquiera el código spaghetti lo podemos considerar una mala practica de programación, por que muchos programadores afirman que es peor que esto. Por ejemplo, nos encontramos con un diseño de una pagina web, y al analizar su codigo nos damos cuenta de que el programador situó tanto sentencias sql, como estilos, sentencias de javascript y html, todo en un mismo archivo jsp por ejemplo, todo esto obedece a clasificarse como codigo spaghetti.

No es solo esto, además el código se vuelve difícil de mantener, ya que, en primer lugar puede costar entenderlo y en segundo lugar, todo esta tan acoplado que un mínimo cambio dañaría por completo el software.
### ¿Como evitarlo?

Principalmente, realizando un buen diseño de software desde el principio, una buena técnica para evitar este tipo de código es usar patrones y principios de diseño, haciendo un software con una alta cohesión, es decir que cada modulo tenga mucha relación con sus funcionalidades y mantenga una sola responsabilidad y por otro lado que este código tenga un acoplamiento bajo, es decir que la relación que exista entre sus módulos no sea mucha, esto para evitar muchas dependencias en el código.


## Blob

Este antipatron ocurre cuando un programador no conoce el paradigma orientado a objetos y tiende a poner todos los atributos y objetos en la misma clase, es tambien conocida como la clase Dios.

Consiste en una clase o módulo que monopoliza las responsabilidades de la aplicación. Creando un programa en el que se evidencia una gran cantidad de líneas, sin una adecuada delegación entre clases. Es por esto que mientras hay una clase omnipotente que se ejecuta la mitad del programa, mientras que la mayoría de los demás objetos solo contienen datos o ejecutan procesos simples.Esto puede suceder por realizar un código con prisa, la pereza, y la influencia de un diseño procedural, por ende, se presenta un código desorganizado y fuertemente interdependendiente.

### **Síntomas y Consecuencias**
* Suele verse presente en una clase que lleve una vasta cantidad de atributos y métodos, o ambos.
Una clase con 60 o más atributos y métodos usualmente indica la presencia de este anti-patrón.
* Una falta de cohesión de los atributos y operaciones hace evidenciar este patrón. Una colección dispar de atributos y operaciones no relacionados y encapsulados en una sola clase.
* Una simple clase controladora con muchas asociaciones.
* Ausencia del paradigma de Programación Orientada a Objetos, así mismo no se evidencia una modularidad y un encapsulamiento. Limitando a casi nula las ventajas que tiene el paradigma, y por esto al no cumplir con el principio de Abierto/ Cerrado, al momento de querer editar una clase, se termina editando todo el software.
* Se vuelve inutilizable.
* Consume memoria en exceso.

### **Causas**
* Falta de una arquitectura orientada a objetos.  Probablemente quien diseño la arquitectura no tiene los adecuados conocimientos para entender los principios de una arquitectura orientada a objetos. Alternativamente el equipo puede tener debilidad en habilidades de abstracción.
* En proyectos iterativos, los desarrolladores tienden a agregar pequeñas piezas de funcionalidad a las clases existentes, en lugar de agregar nuevas clases, o revisar y refactorizar la jerarquía de clases para una asignación de responsabilidades más efectiva.
* Desastre ya especificado. A veces, el anti-patrón resulta de la forma en que se especifican los requisitos. Si los requisitos dictan una solución de tipo procedimental, entonces se pueden hacer compromisos arquitectónicos durante el análisis de requisitos que son difíciles de cambiar. Definir la arquitectura del sistema como parte del análisis de requisitos suele ser inapropiado.

### **¿Como resolverlo?**
Al igual que la mayoría de los antipatrones que se ubican en esta sección, la solución involucra una forma de refactoring. La clave es mover comportamientos afuera del Blob. Puede ser apropiado reubicar comportamientos hacia de las clases que encapsulan datos de forma que esos objetos sean más capaces y The Blob menos complejo.

 ## **GoldenHammer**

Este AntiPatron resulta en la aplicación incorrecta de una herramienta o concepto favorecido. Los desarrolladores y gerentes se sienten cómodos con un enfoque existente y no están dispuestos a aprender y aplicar uno que se adapte mejor. 

Esta asociado con aferrarse a un paradigma, para solucionar todos los problemas que se nos presenten al desarrollar sistemas, como el usar siempre un mismo lenguaje cuando no es el mejor pues cada lenguaje tiene sus limitaciones y sus beneficios.

### Causas 

- Cuando en varios éxitos han utilizado un enfoque particular.
Se han realizado grandes inversiones en formación y/o experiencia en un producto o tecnología. Se logra que el desarrollador siga solamente una linea.

- El grupo está aislado de la industria o de otras empresas.
- Confianza en características de productos propietarios que no están disponibles en otros productos de la industria.

### Consecuencias

- Herramientas y productos idénticos se utilizan para una amplia gama de productos conceptualmente diversos.
- Las soluciones tienen menor rendimiento, escalabilidad, etc. en comparación con otras soluciones de la industria.
  
- La arquitectura del sistema se describe mejor mediante un producto, un conjunto de aplicaciones o un conjunto de herramientas de proveedor en particular.
- Los desarrolladores debaten los requisitos del sistema con los analistas de sistemas y los usuarios finales, con frecuencia abogando por requisitos que son fácilmente acomodados por una herramienta en particular y los alejan de las áreas donde la herramienta adoptada es insuficiente.
- Los desarrolladores se aíslan de la industria. Demuestran una falta de conocimiento y experiencia con enfoques alternativos.
- Los requisitos no se cumplen plenamente, en un intento de aprovechar la inversión existente.
- Los productos existentes dictan el diseño y la arquitectura del sistema.
- El nuevo desarrollo depende en gran medida de un producto o tecnología de proveedor específico.

### ¿Como resolverlo?

La mayor prevencion para no aplicar el golden hammer  es la exploracion de nuevas tecnologias al igual que se debe tratar de conseguir un mayor compromiso por parte de la administración en el desarrollo profesional de sus desarrolladores, junto con una estrategia de desarrollo que requiere límites de software explícitos para permitir la migración de tecnología.
