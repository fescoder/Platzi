![Logo_Curso_Programacion_funcional_Java_SE](src/Curso_Programacion_Funcional_Java_SE/Logo_Curso_Programacion_funcional_Java_SE.webp)
# Curso de Programación Funcional con Java SE
Índice
-
- [Curso de Programación Funcional con Java SE](#curso-de-programación-funcional-con-java-se)
    - [Módulo 1 - Introducción a la Programación Funcional](#módulo-1---introducción-a-la-programación-funcional)
        - [Clase 1 - ¿Qué es la Programación Funcional?](#clase-1---¿qué-es-la-programación-funcional?)
    - [Módulo 2 - Entendiendo las partes de la Programación Funcional](#módulo-2---entendiendo-las-partes-de-la-programación-funcional)
        - [Clase 2 - ¿Qué es una función en Java?](#clase-2---¿qué-es-una-función-en-java?)
        - [Clase 3 - Funciones como ciudadanos de primera clase](#clase-3---funciones-como-ciudadanos-de-primera-clase)
        - [Clase 4 - Funciones puras](#clase-4---funciones-puras)
        - [Clase 5 - Entendiendo los efectos secundarios](#clase-5---entendiendo-los-efectos-secundarios)
        - [Clase 6 - Funciones de orden mayor](#clase-6---funciones-de-orden-mayor)
        - [Clase 7 - Funciones lambda](#clase-7---funciones-lambda)
        - [Clase 8 - Inmutabilidad](#clase-8---inmutabilidad)
    - [Módulo 3 - Functional programming en Java](#módulo-3---functional-programming-en-java)
        - [Clase 9 - Repositorio del curso](#clase-9---repositorio-del-curso)
        - [Clase 10 - Configuración del entorno de trabajo](#clase-10---configuración-del-entorno-de-trabajo)
        - [Clase 11 - Revisando el paquete java.util.function: Function](#clase-11---revisando-el-paquete-javautilfunction-function)
        - [Clase 12 - Revisando el paquete java.util.function: Predicate](#clase-12---revisando-el-paquete-javautilfunction-predicate)
        - [Clase 13 - Revisando el paquete java.util.function: Consumer y Supplier](#clase-13---revisando-el-paquete-javautilfunction-consumer-y-supplier)
        - [Clase 14 - Revisando el paquete java.util.function: Operators y BiFunction](#clase-14---revisando-el-paquete-javautilfunction-operators-y-bifunction)
        - [Clase 15 - Entendiendo dos jugadores clave SAM y FunctionalInterface](#clase-15---entendiendo-dos-jugadores-clave-sam-y-functionalinterface)
        - [Clase 16 - Operador de referencia](#clase-16---operador-de-referencia)
        - [Clase 17 - Analizando la interferencia de tipos](#clase-17---analizando-la-interferencia-de-tipos)
        - [Clase 18 - Comprendiendo la sintaxis de las funciones lambda](#clase-18---comprendiendo-la-sintaxis-de-las-funciones-lambda)
        - [Clase 19 - Usando métodos default en nuestras interfaces](#clase-19---usando-métodos-default-en-nuestras-interfaces)
        - [Clase 20 - Dándole nombre a un viejo amigo chaining](#clase-20---dándole-nombre-a-un-viejo-amigo-chaining)
        - [Clase 21 - Entendiendo la composición de funciones](#clase-21---entendiendo-la-composición-de-funciones)
    - [Módulo 4 - Optional y streams datos mas interesantes](#módulo-4---optional-y-streams-datos-mas-interesantes)
        - [Clase 22 - La clase optional](#clase-22---la-clase-optional)
        - [Clase 23 - Entendiendo los streams](#clase-23---entendiendo-los-streams)
        - [Clase 24 - ¿Qué son los stream listeners](#clase-24---¿qué-son-los-stream-listeners)
        - [Clase 25 - Operaciones y Collectors](#clase-25---operaciones-y-collectors)
        - [Clase 26 - Stream de tipo específico y paralelismo](#clase-26---stream-de-tipo-específico-y-paralelismo)
        - [Clase 27 - Operaciones terminales](#clase-27---operaciones-terminales)
        - [Clase 28 - Operaciones intermedias](#clase-28---operaciones-intermedias)
        - [Clase 29 - Collectors](#clase-29---collectors)
    - [Módulo 5 - Todo junto proyecto job search](#módulo-5---todo-junto-proyecto-job-search)
        - [Clase 30 - job search un proyecto para encontrar trabajo](#clase-30---job-search-un-proyecto-para-encontrar-trabajo)
        - [Clase 31 - Vista rápida a un proyecto de gradle](#clase-31---vista-rápida-a-un-proyecto-de-gradle)
        - [Clase 32 - Revisando las opciones para nuestro CLI](#clase-32---revisando-las-opciones-para-nuestro-cli)
        - [Clase 33 - Librerías adicionales para nuestro proyecto](#clase-33---librerías-adicionales-para-nuestro-proyecto)
        - [Clase 34 - Entendiendo la api de jobs](#clase-34---entendiendo-la-api-de-jobs)
        - [Clase 35 - Diseñando las funciones constructoras de nuestro proyecto](#clase-35---diseñando-las-funciones-constructoras-de-nuestro-proyecto)
        - [Clase 36 - Agregando validaciones de datos](#clase-36---agregando-validaciones-de-datos)
        - [Clase 37 - Diseñando las funciones de transformación de datos](#clase-37---diseñando-las-funciones-de-transformación-de-datos)
        - [Clase 38 - Creando flujos extras de transformación de datos](#clase-38---creando-flujos-extras-de-transformación-de-datos)
    - [Módulo 6 - Conclusiones](#módulo-6---conclusiones)
        - [Clase 39 - Un repaso a lo aprendido](#clase-39---un-repaso-a-lo-aprendido)

---

## Módulo 1 - Introducción a la Programación Funcional
### Clase 1 - ¿Qué es la Programación Funcional?
[PDF de las primeras clases](https://static.platzi.com/media/public/uploads/javase-functional_6a4212af-2764-4614-97ea-fb0faa854628.pdf)

La programación funcional no es mas que un paradigma, una forma de programar, un estilo de programación, hay gente que le gusta programar orientado a objetos y hay lenguajes que te ayudan
con ello, hay gente que le gusta programar con procesos y es valido, incluso hay lenguajes que tiene estructuras lógicas para programar, la programación funcional es otro tipo de
paradigma, otro tipo de estilo, es un estilo más enfocado a tener casos específicos en el cual nos preocupamos por que resolver.

Cuando pensamos en programación funcional casi siempre la primera idea que nos viene a la mente es *lambdas*, toda la gente de Java 8 habla de lambdas, pero la realidad es que es más
que eso. Hay lenguajes que te obligan a programar funcionalmente y estos lenguajes son relativamente "legendarios", pero hay otros que no te obligan si no que te dan la posibilidad
de hacerlo, lenguajes que no son 100% funcionales pero que buscan apoyarte en que puedas hacer este tipo de estilo de programación sin necesidad de que entiendas conceptos complejos
matemáticos.  
Y después tenemos a Java, el rey del POO, que a partir de Java 8 te da la posibilidad de hacer programación funcional. Veremos lo nuevo en esta versión pero nos reduciremos a dos cosas:

![01_Que_es_la_Programacion_Funcional_01](src/Curso_Programacion_Funcional_Java_SE/01_Que_es_la_Programacion_Funcional_01.png)

- Funciones
- Datos

Entendiendo que es una **Función** y que tipo de **Datos** hay, podremos generar muchísimas de las partes de la programación funcional.  
Básicamente la prog funcional se enfoca en **QUE** resolver y no en COMO resolver, generalmente cuando pensamos en POO pensamos mucho en vamos a crear esta clase, que genera este
objeto, que va a generar esta otra clase, en la prog funcional estamos más preocupados por resolver el problema, no en que elementos están involucrados, lo importante es tener una función
que pueda resolver el problema, no importa su procedencia, y en la parte de los datos vamos a aprender que son los datos mutables e inmutables, esto es muy importante porque esto nos va a
poder dar diferentes tipos de funciones, según los datos que tengamos.  
Es importante recalcar que esto ya existe en Java en versiones anteriores, solo que ahora haremos un mayor énfasis en como obtenerlo en el lenguaje para que nuestras funciones puedan ser
más simples.

**La prog funcional entonces nos va a dar ciertos beneficios:**

![01_Que_es_la_Programacion_Funcional_02](src/Curso_Programacion_Funcional_Java_SE/01_Que_es_la_Programacion_Funcional_02.png)

- **Legibilidad:** Uno de ellos es la legibilidad, vamos a estar muy enfocados en que resolver, es decir, nuestras funciones van a ser más explicitas en cuanto a que es lo que hacen, no en
como lo hacen, no nos vamos a preocupar en como construir objetos, o tener mil procesos para obtener una solución, nos vamos a preocupar por resolver un problema.
- **Testing:** Va a ser mas fácil hacer pruebas, tener testings de nuestras funciones, porque al tener nuestro código separado en funciones resolviendo pequeños problemas, es más facil
hacer un test de una sola función que tener que resolver todo el sistema.
- **Concurrencia:** La concurrencia se hace más fácil y se hace más didáctica, dinámica, porque ahora podemos liberar muchos threads o procesos simultáneos a partir de la misma función. Ya
no necesitamos tener control de los objetos que existen en memoria porque tenemos funciones y son únicas.
- **Comportamientos más definidos:** Vamos a tener comportamientos más definidos que van a estar dados por funciones simples, una función simple vamos a poder leerla rápidamente y entender
qué es lo que hace.
- **Menos manejo de estados:** También vamos a tener un menor manejo de estado, es decir, no nos vamos a preocupar porque objeto tiene el dato en el momento en el que estamos funcionando
sino si tenemos el dato o no.
- **No hay que instalar nada adicional:** Y no hay que agregar nada, ya es parte del lenguaje, no librerias o cambiar de lenguaje, es Java puro.

Otras características de la Programación Funcional:
- En el paradigma de la programación funcional, un programa se considera una función matemática, la cual describe una relación entre una entrada y una salida y donde el concepto de estado
o variable se elimina completamente.
- Fácil de combinar con la programación orientada a objetos
- Uso de listas como estructuras de datos fundamentales. No hay bucles, solo vas a iterar arrays o listas.
- En la programación funcional no existen los bucles “for” y “while”. En su lugar, para la iteración se depende de la recursividad.
- Funciones como tipos de datos primitivos: expresiones lambda y funciones de orden superior.

---

## Módulo 2 - Entendiendo las partes de la programación funcional
### Clase 2 - ¿Qué es una función en Java?
En la programación funcional una función es un tipo de dato, un tipo de dato que puede operar sobre un dato **X** y generar un dato **Y**, como la matemática de la escuela, tenemos una
función que recibe una X y genera una Y, incluso podemos generar una tabla de resultados con ellos, idealmente siempre una X va a generar la misma Y.

![02_Que_es_una_funcion_en_Java_01](src/Curso_Programacion_Funcional_Java_SE/02_Que_es_una_funcion_en_Java_01.png)

- Una función es una serie de pasos parametrizados. Por ejemplo, inicia con esto, sigue con esto y termina con aquello, las funciones pueden generar o no un resultado, la ausencia de un resultado no quiere decir que no haya un resultado como tal si no que el tipo de dato que se regresa es un tipo de dato vacio.
- Las funciones se definen, almacenan o declaran bajo demanda como cualquier otro tipo de dato.

![02_Que_es_una_funcion_en_Java_02](src/Curso_Programacion_Funcional_Java_SE/02_Que_es_una_funcion_en_Java_02.png)

- Pueden definirse funciones con respecto a otras funciones
`esPar(x) = !esNon(x)`
- Pueden definirse funciones con respecto a sí mismas (Recursividad), es decir una función que se invoque a si misma dentro de su cuerpo.
~~~
factorial(x) = if x <= 2 :
x
else : x *
factorial(x-1)
~~~
- Pueden existir funciones que toman a otras funciones como parámetros:
`f(x, g(x)) = x2 * (gx)`

---

### Clase 3 - Funciones como ciudadanos de primera clase
Una vez que definimos que es una función, tenemos que entender que ahora se vuelven ciudadanos de
primera clase y ¿que representa que sean ciudadanos de primera clase? Esto representa que ahora las
funciones son algo reconocido por el lenguaje como algo que podemos definir y utilizar.

Generalmente declaras variables de tipo String o de tipo
entero. Ahora puedes declarar variables de tipo función e incluso puedes asignarles un valor.
Y también es importante declarar que ahora puedes tomar las como parámetros de otras funciones o
retornarlas como resultado de una ejecución.

Entonces, el tenerlas como ciudadanos de primera clase
implica que ya son tipos reconocidos por el lenguaje que podemos almacenar en alguna parte.
Podemos tenerlos en variables, en parámetros o en retornos.

![03_Funciones_como_ciudadanos_de_primera_clase_01](src/Curso_Programacion_Funcional_Java_SE/03_Funciones_como_ciudadanos_de_primera_clase_01.png)

Incluso podemos empezar a definir los bajo demanda.
Así como tú definirías un string *hi*, hay también podrías definir una función.
Por ahora quedémonos con esta sintaxis. Esta sintaxis nos dice que es una función definida al
aire. Es una función que no está asignada, una variable y que simplemente estamos pasandola como
parámetro hacia otra función no se obtienen de ningún otro lado.
Son valores constantes, por así decirlo.

![03_Funciones_como_ciudadanos_de_primera_clase_02](src/Curso_Programacion_Funcional_Java_SE/03_Funciones_como_ciudadanos_de_primera_clase_02.png)

Algunos usos que puede llegar a tener el pasar este tipo
de funciones declaradas en el aire puede ser, por ejemplo, obtener una configuración de conexión o
simplemente hacer un procesamiento de un dato específico para un caso muy específico, como una petición
web o recibir un dato y manipularlo de una base de datos.  
Declarar este tipo de lógica en el aire es porque probablemente en otros lugares no se necesita, así
como el String se necesita exclusivamente en esta parte de nuestro código, tal vez este tipo de lógica
se necesita exclusivamente en esta parte del programa, y nos da el beneficio de poder tener aisladas las las partes de nuestro código, donde
vamos a necesitar lógica para hacer transformaciones, creaciones o simplemente alguien que nos provea
de un dato.

En otra parte del curso explicaremos qué tipos de funciones pueden generar datos que se pueden
utilizar, consumir posteriormente.

Cuando decimos que algo es ciudadano de primera clase en un lenguaje, quiere decir que el lenguaje reconoce que se pueden usar estos elementos como un componente mas del lenguaje. Sabe que tienen su propia sintaxis o que cumple al menos con estas caracteristicas:

Un ciudadano de primera clase puede:
- Ser pasado como argumento
- Ser el retorno de una funcion
- Ser definido y modificado
- Ser asignado a variables

Por ejemplo, otros ciudadanos de primera clase en java son:
- Clases
- Interfaces
- Datos primitivos
- Anotaciones
- Generics

---

### Clase 4 - Funciones puras
Cómo definimos las funciones pueden ser categorizadas al ser ciudadanos de primera clase.
Y el primer tipo sobre el que vamos a hablar son las **funciones puras** o conocidas como **Pure functions**.

**¿Que es una función pura?**  
Una función pura no es más que una función que
siempre genera el mismo resultado para el mismo parámetro.  
Es decir, no importa cuántas veces mandemos a invocar esta función siempre que los parámetros sean los mismos
va a generar el mismo resultado.

Las funciones puras también funcionan en aislamiento.
Eso quiere decir que no dependen del estado del sistema, no dependen sobre si el sistema está corriendo en una computadora o está corriendo en un servidor remoto, y **son deterministas**.  
Quiere decir que nosotros podemos predecir el resultado de la ejecución de una función pura.  
Si nosotros sabemos que pasamos cinco y tres a sum, podemos predecir que el resultado será ocho. (5+3) del ejemplo.  
Esto nos va a dar una ventaja gigante, y es que al estar escribiendo pruebas de nuestro código va a ser muchísimo más fácil hacer casos de prueba donde nosotros digamos. al pasar estos parámetros deberíamos obtener este resultado.

Ejemplos de funciones puras.  
Tenemos `f(x) = x^3`. Esta es una función pura porque no genera valores aleatorios.

![04_Funciones_puras_01](src/Curso_Programacion_Funcional_Java_SE/04_Funciones_puras_01.png)

A su vez, no cambia el valor de X, Es decir, para cada X genera
un Y sin alterar el valor de X. Tres siempre va a seguir siendo tres y el resultado de la invocación
siempre será veintisiete.

**No genera efectos secundarios.**  
Ahora tenemos que entender que un efecto secundario
es que no cambia en la base de datos, no crea un archivo y no modifica el sistema.
Invocar a f(x) no apaga el Internet o borra un archivo en el sistema.
Es por esto que esta es una función pura.

Un ejemplo de función pura en Java es la función `hasAvialableFound()`

![04_Funciones_puras_02](src/Curso_Programacion_Funcional_Java_SE/04_Funciones_puras_02.png)

Que recibe un double que representa el balance de un usuario
y nos dice si tiene o no disponible un balance para poder operar dentro del sistema.
Es un ejemplo muy básico que lo único que hace es decirnos si un número, es mayor o
no a cero, pero es una función pura.  
Piensa en esto, el dato del usuario no se ve modificado.
El sistema no se ve alterado por ello. Es una función pura.

A las funciones que no son puras, se les conoce como impuras.
Y las reglas nos dictan algo. Lo primero que nos dictan es que una función pura puede
invocar a otra función pura. ¿Por qué? Porque podemos pronosticar cuál va a ser el resultado de esta
ejecución. Al fin Sabemos que una función pura es determinista, es decir, podemos pronosticar
el resultado.

Sin embargo no podemos invocar una función impura desde una función pura porque rompería la estructura. Es decir, si desde una función pura tratáramos de invocar a una función impura, no podríamos pronosticar o predecir cuál va a ser el resultado.
Y al no poder pronosticar o predecir el resultado no tendríamos una función pura así
de simple. Entendemos que hay una regla entre cómo podemos invocar mutuamente las funciones y
qué categorías tenemos para ellas.

---

### Clase 5 - Entendiendo los efectos secundarios
Ya definimos que es una función pura y definimos que existen las funciones impuras, y
las funciones impuras generan efectos secundarios.  
¿Pero Que tiene esto de malo, que tiene esto de bueno, que es un efecto secundario?  
Vamos a hablar un poco más de ello y entender que son para poder identificar dentro
de nuestro código, que es un efecto secundario que no es un efecto secundario, y entonces poder separar las funciones que los generan de las que no, para poder entender nuestro proyecto
mejor.

Un efecto secundario es ***todo cambio observable desde fuera del sistema es un efecto secundario***.  
Es decir, si nosotros hacemos una operación y el resultado de esa operación es
observable desde fuera del sistema, es un efecto secundario.  
Por ejemplo, tenemos una función que, una vez invocada, cambia el color de algo.
A esto se le considera un efecto secundario y es observable desde fuera del sistema, tal
cual alguien que vaya y vea cómo va la ejecución del sistema podrá observar este cambio.
Es por ello que se le considera un efecto secundario.

Todos estos efectos secundarios no son evitables y los hemos tenido en nuestro código
toda la vida. Al final de cuentas son parte de poder interactuar en el sistema como por ejemplo:

![05_Entendiendo_los_efectos_secundarios_01](src/Curso_Programacion_Funcional_Java_SE/05_Entendiendo_los_efectos_secundarios_01.png)

Son necesarios, no podemos evitarlos.
Sin embargo, podemos reducir las ocurrencias de los efectos secundarios.

**¿Por qué querríamos reducir o evitar los efectos secundarios?**  
Porque esto nos ayuda a tener una mejor estructura de nuestro código, nos ayuda a generar más funciones puras y nos ayuda también a tener mejor separadas las
definiciones y responsabilidades de nuestro código.  
Hay que entender esto, **los efectos secundarios son inevitables**, no podemos tener código sin efectos secundarios, pero podemos reducirlos.

La principal idea es tener código bien estructurado, código bien separado donde las responsabilidades están
aisladas, es decir, tener una arquitectura o tener un sistema en el cual todas
nuestras funciones impuras sean solamente puntos de entrada para información.
Pero una vez que la información está dentro del sistema, mantener toda esa información entre
funciones puras.

Por ejemplo, una conexión de red recibió una petición va genera un efecto secundario, pero una vez el dato este dentro del sistema, podemos transformarlo, manipularlo o hacer operaciones
con él sin necesidad de generar un nuevo efecto secundario.

La intención es tener la mayor cantidad de funciones puras dentro de nuestro sistema,
con esto vamos a reducir la cantidad de errores y vamos a mejorar la estructura de nuestro sistema
y aumentar la **testeabilidad** de nuestro sistema.

Recuerda que la **testeabilidad** de nuestro sistema
es que tantas pruebas podemos escribir sobre nuestro propio código.  
Escribir pruebas nos da como beneficio evitar errores posibles o errores conocidos dentro de nuestro código nos va a permitir tener un código más
robusto y que sea más fácil de escalar a largo plazo.
Teniendo muchas pruebas de nuestro código, podemos reducir casos inesperados que puedan llegar a pasar
teniendo funciones puras. Podemos tener mayor cantidad de pruebas.

---

### Clase 6 - Funciones de orden mayor
Definimos que ahora las funciones son ciudadanos de primera clase, definimos que tenemos funciones puras e impuras, pero la parte importante aquí es definir las funciones de orden mayor.

Una función de orden mayor es una función que cumpla al menos con alguna de estas dos características:
- Toma otra función o funciones como parámetro.
- Retornar una función como resultado de su ejecución.

Eso define que es una función de orden mayor, veamos ejemplos.
~~~
int foo (Function param)
~~~
En este caso, la función ***foo*** toma una función ***param*** y la utiliza para generar un valor entero.  
¿Que puede ser esto? Por ejemplo, podríamos tener la función para Ploteo o una función a
partir de la cual generar todos los resultados de los salarios o algo por el estilo.

O tenemos este otro caso.
~~~
Function bar (int x)
~~~
La función ***bar*** que reciben un entero y genera de nueva función.  
Y este es un caso en el cual podríamos, por ejemplo, tener una función que genere accesos a una base
de datos basado en un ***ID*** o basado en una contraseña, un password.

Podemos generar funciones de manera dinámica, basado en parámetros o incluso ambos casos.
~~~
Function baz (Function f)
~~~
Podemos tener una función que tome como primer parámetro una función y que ejecute sus datos
y resulte en otra función.  
Por ejemplo, o transformaciones de datos, es decir, tenemos una función que va a tomar un Json, va a aplicar los la función F
sobre ese JSON y generar una nueva función que va a estar generando dinámicamente datos
a partir de JSON.  

Ventajas de tener high order function:
- Podemos pasar comportamientos.  
Como filtrar elementos de una base de datos, es pasar una función como una manera de filtrar los datos.
- Compartir un medio de comunicación (Callbacks).  
Sí sabemos que algo va a ir generando resultados y necesitamos un medio de comunicación, pásame los datos a través de esta función. Es un caso muy común en el caso de JS el generar este tipo de callbacks, es simplemente cuando tengas algún dato, pásamelo por esta función es
un medio de comunicación.
- Incluso compartir lógica o reglas.  
Por ejemplo, el filtrado de una base de datos, o el cómo detectar un
password seguro o inseguro y que ese tipo de lógica se repite a lo largo del proyecto. Entonces podemos mantener una sola función con esta lógica y compartirla entre diferentes invocaciones.

**En resumen:**  
FUNCIONES DE ORDEN MAYOR  
- Toma otra funciona como parámetro.
- Retorna una función después de su ejecución.

VENTAJAS  
- Pasar comportamientos.
- Compartir un medio de comunicación.
- Compartir logica/reglas.

---

### Clase 7 - Funciones lambda
Definimos entonces que tenemos funciones puras, funciones impuras, funciones de orden mayor y seguramente hasta este punto te has encontrado mucho con esto.

Cuando se habla de Programación funcional en Java se
habla de las **Lambdas**, las famosas lambdas y a veces estamos asustados porque muchos incluso refieren al lambda
cálculos.

**¿Pero que son las Landas realmente? ¿Que representan las lambdas en el proyecto? ¿Que representan las lambdas a nivel Java?**

![07_Funciones_lambda_01](src/Curso_Programacion_Funcional_Java_SE/07_Funciones_lambda_01.png)

- Las lambdas provienen del cálculo Lambda. El cálculo Lambda es un concepto que se creó en los años 30 por el matemático **Alonzo Church**.  
Pero lo único que proponía era que se podía obtener resultados de una operación a partir de funciones
anónimas. Eso es el cálculo Lambda.  
- Aqui hablaremos de que es la lambda y una lambda es una función anónima, así de simple.  
Cuando tienes una función que no tiene un nombre, es una función anónima, y eso es una lambda. 
- No hay más, tan simple como eso.

Veamos una comparativa.

![07_Funciones_lambda_02](src/Curso_Programacion_Funcional_Java_SE/07_Funciones_lambda_02.png)

Tienes una función que se llama ***baz***, lo sabemos porque está definida como una variable baz y tenemos la función ***foo***, sigue siendo una función, recibe parámetros y generó un entero. Tienen nombre, no son anónimas.  
En cambio debajo tenemos la función sin nombre, no tiene un hombre, es una función anónima.  
Al no tener nombre, se le considera una lambda, es una forma de llamar le estas funciones sin nombre, pero siguen siendo funciones.

**¿Porque querría yo utilizar algo sin nombre?, ¿Porque no querría yo tener el dato almacenado en algún lado?, ¿Porque no querría yo tener una referencia así a esta?**

![07_Funciones_lambda_03](src/Curso_Programacion_Funcional_Java_SE/07_Funciones_lambda_03.png)

- Y la solución es simple, en muchas ocasiones necesitamos un comportamiento de uso único.  
Por ejemplo, una manera de filtrar archivos bajo extensión y solamente lo necesitamos en un momento del
sistema. Generar una lamda para este tipo de caso es algo muy sencillo.
- O es una regla que se requiere de un solo lugar.  
Por ejemplo, dime cómo filtrar a los empleados basado en su edad o
dime cómo filtrar alumnos de mi base de datos que aprobaron o no aprobar una materia. Es
una regla específica que se utiliza en un solo lugar e incluso puede que también se reutiliza otros
lados.Pero serán Landas diferentes o en ese caso, crearás una función con nombre a la cual referenciaras.
- La lambda tiene que ser algo extremadamente simple.  
Una lambda idealmente es una función de una sola línea, o menos incluso que pueda ser legible de primera instancia, y ese es un gran beneficio porque hace que el código sea más fácil de entender.

Y tener siempre en cuenta que una lambda sigue siendo una función, por más que la llamemos lambda.

![07_Funciones_lambda_04](src/Curso_Programacion_Funcional_Java_SE/07_Funciones_lambda_04.png)

**Resumen**  
Función = Tiene un nombre.  
Lambda = Función que no tiene un nombre.

¿Por qué usar lambdas?  
Es un comportamiento único.  
Es una regla que solo se requiere en un lugar.  
Es una función muy simple (1 línea).

---

### Clase 8 - Inmutabilidad
Hasta este punto hemos hablado de funciones, funciones, funciones y más funciones, diferentes tipos
de funciones, diferentes utilidades pero No. Hemos hablado de una parte importante de la programación
funcional, que es la inmutabilidad de los datos, los datos en sí, con los que vamos a operar nuestras
funciones. Hablemos entonces de la diferencia con respecto a lo que usualmente hacemos en otros
lenguajes de programación. Y como la programación funcional es per a manejar los datos.
Y esto es principalmente a través de datos de dos tipos mudables e inmutables, En la mayoría de casos
vas a preferir tener datos inmutables y a continuación te voy a explicar por qué Las
principales ventajas de tener datos inmutables es que una vez creado un dato ya
no puede alterarse. Es decir, Vas creas una instancia de un cierto objeto Y, ese objeto ya
no cambia. Y por qué querrías eso? Porque ciertamente, al crear a un ciudadano, por ejemplo, su
identificador único no va a cambiar o sus nombres no van a cambiar.
O a lo mejor quieres establecer un identificador para un libro o de alguna manera necesitas una lista
de asistentes que ya no va a cambiar y esa es una ventaja que, una vez creado un dato ya
no cambia. Esto nos facilita crear funciones puras al tener datos que no cambian Tenemos
funciones que no generan efectos secundarios, lo cual hace que nuestras funciones se vuelvan puras
casi automático. Y por otro lado, si son puras, hace más fácil el tener tres.
Es decir, una función que no genera efectos secundarios es más fácil de meter en diferentes procesadores
Puedes tomar esa función Ejecutar le en un procesador de ocho núcleos en ocho diferentes ocasiones y
a final de cuentas no va a haber problema entre tratar de sincronizar los datos que la función uno y
la función ocho están tratando de generar. Es una ventaja enorme al momento de hacer programación concurrente
pero también tiene sus desventajas. No todo lo que brilla es oro y una de ellas es que por cada modificación
necesite sobre los datos. Vas a tener que crear una nueva instancia de Eldad.
Es decir, si tu quisieras alterar el apellido de una persona que es inmutable, vas a tener que generar
una nueva persona y se van a tener que identificar diferente.
Esto puede llegar a ser bastante molesto a nivel código, pero puede tener también sus ventajas.
Otra desventaja es que requiere especial atención al diseño en unos minutos.
Demostrar es un ejemplo concreto de cómo tenemos que diseñar nuestros objetos para que se vuelvan inmutables
Y por otro lado, pues los objetos mutable es que no tenemos nosotros Control + L sobre ello.
Es decir, esa es una desventaja enorme. Existen objetos de librerías, existen objetos dentro del
lenguaje o incluso datos que nos llegan de algún otro lado, que son mudables por sí mismos.
Nosotros no tenemos control de cómo funcionan esos objetos.
Entonces tenemos que generar alguna manera de que esos objetos no multen aún cuando su naturaleza se
los permite. Entonces veamos un ejemplo de mutabilidad e inmutabilidad en Ya empezamos
con algo simple tenemos una persona, le hemos llamado multa.
Good person Ya, imaginarás porque y bueno que representa representa algo que ya haba.
Conocemos como un poco o pollo, un pleito llava objecte.
Es decir, es un objeto que tiene un constructor y tiene propiedades y por cada propiedad tiene un deterioro
Z. Entonces es algo con lo que debes estar familiarizado.
Tiene UN Finish Next tiene un la acné y tiene una lista de Vim es que corresponden con esta persona
cierto? Nada fuera de lo común y bueno, al pequeño Método tres trenes sólo para poder devolviera.
Gusta. Entonces tenemos esta clase y tenemos una clase fuera que se encarga de generar objetos de este
tipo. Es cierto. Tenemos los correos de esta persona.
Generamos la persona, le asignamos sus datos y posterior a ello, mandamos a imprimir por pantalla
La parte interesante es que mandamos a llamar a una función impura que toma este dato.
Es una función que nosotros no sabemos Qué hace? Tal vez es de una librería.
Tal vez es de un Fray Mork. O tal vez es una función que hizo alguien más.
Y despues volvemos a imprimir este dato. Veamos.
Qué es lo que pasa? Al ejecutar esto. Esperaríamos ver los mismos resultados.
Cierto? Por pantalla deberíamos ver Tanto los No, el filón.
Enmiendas Next sin modificarse como el correo. Pero el resultado es sorprendente.
Resulta que aunque yo sé, le José ti. Yo puse los valores para un correo.
Esa función hizo modificaciones sobre mi objeto. Esas modificaciones son resultado de que mi clase
sea mutable. Tener una clase multable genera este tipo de problemas.
y veamos otro ejemplo. Nos damos cuenta que probablemente el error estaba en tener
acceso a los correos. Entonces modificamos con otro tipo de objeto, generamos una nueva clase que
sabemos que ya no va a ser mutable y que ya no se va a ver perjudicada por este hacker
que nos cambia el correo. Sí, vamos a ver esta clase que hicimos.
Pues quitamos la parte en la cual agregamos nosotros un CD Ter para los correos.
Ya no van a poder invocar a este setter para los correos.
Y no sólo eso, modificamos el constructor Ahora al crear este objeto nos van a tener que proveer de
los datos. Esto debería arreglar lo cierto. Veamos el código, creamos otro objeto con
el listado de correos que ya teníamos antes y lo imprimimos entonces muy volvemos a mandar a llamar
a esta función. Y al ver esta función en ejecución nos damos cuenta que no siguen saqueando
nuestros datos. Resulta que los datos multable siguen siendo perjudiciales.
Entonces no basta con sólo configurar El constructor para recibir los datos y esconder los heteros tenemos
que hacer algo más, que es lo que están haciendo.
Estas funciones están alterando nuestros datos porque son mudables Y seguramente tú tienes experiencia
Villava y pensaras Bueno, es fácil Al modificar estos datos sólo tenemos que agregar algunos caracteres
especiales, algunas palabras clave y hacemos que la clásica no se mutable.
Hacemos que la lista de correos sea final al hacer la lista de correos final.
Ya no puede cambiar la referencia. Eso debería arreglar el problema que estamos teniendo, Cierto?
Bueno, asi ejecutamos este código de nuevo. Resulta que no incluso no se están agregando correos de
Spam. Entonces no está siendo efectivo el agregar la palabra Faina y Por Qué?
Qué es lo que está mal con nuestro código Aunque Pere?
Pensábamos que la palabra final permite limitar la mutabilidad de la clase.
En realidad, hay más cosas que pueden estar pasando de fondo con respecto al objeto porque
nosotros no tenemos control sobre su mutabilidad.
Tenemos que ser todavía más astutos que eso. Entonces decidimos hacer una última clase una
clase a través de la cual ya no puedan Anja quedarnos.
Y en esta clase ya decidimos que ya no nos van a Jack header.
Pero resulta que alguien tomó nuestra clase y extendió de ella.
Y al extender de ella nos hace creer que se está comportando como nuestra clase originalmente Tenemos
Motta Volver son tres en la que nosotros creemos que arreglamos la mutabilidad y
que ya no nos va a afectar realmente. Pero alguien genera una nueva clase a partir de la nuestra y
resulta que esa clase hace cosas maliciosos por dentro que hace simplemente evita
que tuve ha reflejado el IMEI correcto, sino que te devuelve nuevos y mails.
Entonces realmente nuestra clase es mutable por donde le busquemos.
Cómo podemos arreglar esto? Veamos simplemente un casos y mucha voz Person, generaremos una
nueva clase. Inmuta muy personal Esta nueva clase va a tener las características que ya teníamos antes
Tenemos la palabra Fain al para prevenir que la clase mute.
Y no sólo lo tenemos a nivel clase para evitar que extiendan de nuestra clase sino que lo ponemos en
las propiedades para evitar que estas muten a largo plazo.
Pero vamos a hacer algo adicional. Vamos a generar que el gay de Terra de nuestro Symes de
Dorna una nueva copia. Recuerdas que dijimos que estará una desventaja?
Bueno, lo que estamos haciendo aquí es evitar que alguien pueda modificar el comportamiento de mi clase
A partir de nosotros. Proteger nuestros datos al proteger nuestros datos es generar nuevas
copias sin modificar el dato que ya tenemos. Con esto estamos garantizando la inmutabilidad
de nuestra clase. Si vemos ahora la ejecución de esta clase, Por más que tratemos de invocar a funciones
en las cuales desconocemos cómo se comportan, como es el caso de este método que se llama va de intención
Es una clase de alguna librería o Fray Moore. No sabemos qué hace por dentro, pero no es al
ser nuestros datos inmutables No vamos a ver el resultado de esta invocación afectado
Nuestro Geta. Bueno, te preguntarás en este punto bueno, y a lo mejor que hacían internamente
él ve todo va de intensión. Lo que trataba de hacer es tomar los correos de esta persona, limpiarlos
y agregar su propio correo. Pero como nosotros generamos una clase inmutable, esta nueva clase se
protege devolviendo siempre una nueva copia de la lista.
Con eso prevenimos que la lista que ya tenemos se vea afectada cuando alguien trate de acceder a ella
Tener este tipo de estrategias requiere diseño especial para determinar qué es y qué no es inmutable
pero es importante a nivel código porque con esto podemos asegurar que nadie llegue y cambio en paz
por que nadie llegue. Cambió en salario Que nadie llegue cambio Correos home agrede correos para enviar
España Si queremos ver como se comportaban las otras funciones que Hacienda alteraciones
a nuestro código era básicamente el acceso a las listas El acceso a la vista simplemente
me permitía generar nuevos y mails y agregarlos a la persona o tomar los que ya tenía la persona y limpiar
los Qué está pasando aquí? La realidad es que es algo que mencionábamos antes.
En muchas ocasiones va a ver objetos fuera de nuestro control que nosotros no podemos evitar que se
inmutables, como es el caso de las listas de Llava Pero.
Protegernos utilizando copias nuevas es una manera de generar inmutabilidad, incluso cuando no tenemos
control sobre ellos. Y bueno, ya vimos que es una función funciones puras, funciones impuras, efectos
secundarios, funciones de orden mayor, datos notables, datos inmutables e incluso vimos como
él llava Los datos son mudables por default, pero todavía faltan muchos ejemplos.
No hemos visto funciones todavía en llava. Todavía nos falta entender más estas conceptos aplicados
en un lenguaje que por su naturaleza es orientado objetos.
Entonces te invito a que me dejes komentarios me dejes preguntas hasta este punto para
que podamos seguir con los siguientes partes en donde veremos aplicación directa de cada uno de estos
conciertos ya conllevaba ocho y ya con los elementos que hacen que ya haba, puede hacer un lenguaje
para programar funcionalmente.

---

## Módulo 3 - Functional Programming en Java
### Clase 9 - Repositorio del curso

---

### Clase 10 - Configuración del entorno de trabajo

---

### Clase 11 - Revisando el paquete java.util.function: Function

---

### Clase 12 - Revisando el paquete java.util.function: Predicate

---

### Clase 13 - Revisando el paquete java.util.function: Consumer y Supplier

---

### Clase 14 - Revisando el paquete java.util.function: Operators y BiFunction

---

### Clase 15 - Entendiendo dos jugadores clave: SAM y FunctionalInterface

---

### Clase 16 - Operador de Referencia

---

### Clase 17 - Analizando la interferencia de tipos

---

### Clase 18 - Comprendiendo la sintaxis de las funciones lambda

---

### Clase 19 - Usando métodos default en nuestras interfaces

---

### Clase 20 - Dándole nombre a un viejo amigo: Chaining

---

### Clase 21 - Entendiendo la composición de funciones

---

## Módulo 4 - Optional y Streams: Datos mas interesantes
### Clase 22 - La clase Optional

---

### Clase 23 - Entendiendo los Streams

---

### Clase 24 - ¿Qué son los Stream listeners?

---

### Clase 25 - Operaciones y Collectors

---

### Clase 26 - Stream de tipo específico y Paralelismo

---

### Clase 27 - Operaciones Terminales

---

### Clase 28 - Operaciones Intermedias

---

### Clase 29 - Collectors

---

## Módulo 5 - Todo junto: Proyecto Job-search
### Clase 30 - job-search: Un proyecto para encontrar trabajo

---

### Clase 31 - Vista rápida a un proyecto de Gradle

---

### Clase 32 - Revisando las opciones para nuestro CLI

---

### Clase 33 - Librerías adicionales para nuestro proyecto

---

### Clase 34 - Entendiendo la API de jobs

---

### Clase 35 - Diseñando las Funciones Constructoras de nuestro Proyecto

---

### Clase 36 - Agregando validaciones de datos

---

### Clase 37 - Diseñando las funciones de transformación de datos

---

### Clase 38 - Creando flujos extras de transformación de datos

---

## Módulo 6 - Conclusiones
### Clase 39 - Un repaso a lo aprendido

---