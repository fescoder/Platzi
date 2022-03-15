# Curso de Buenas Practicas en PHP

En este curso nuestro profesor Mauro Chojrin nos enseñará una serie de técnicas que nos ayudarán a realizar aplicaciones más robustas, escalables y mantenibles en el tiempo.

**Objetivo:** Crear aplicaciones más robustas, escalables y mantenibles en el tiempo.

Temas:
- Identificación de problemas comunes en la escritura de codigo y como evitarlas.
- Principio SOLID.
- TDD -> Test Driven Development.

El código bien escrito beneficia a todos los involucrados en el proyecto.
- A tí: Cuando retomemos un proyecto después de un largo tiempo nos beneficiará ya que sabremos cómo está ordenado y cómo está escrito todo.
- A cualquiera: Cualquier persona que deba modificar el código después de tí.
- A tu cliente: Aunque nunca lo sabrá, su negocio estará mejor atendido.

**Código prolijo**

Los siguientes elementos dotan de calidad al código:
- Legibilidad: qué tan fácil es interpretar lo que el código dice. Atención en la Indentación
- Mantenibilidad: cuánto esfuerzo supondrá adaptar el código a nuevos requerimientos.
- Testeabilidad: cuánto esfuerzo supondrá realizar pruebas sobre este código.

El código fuente lo escribimos para personas como tú y yo, para las computadoras tenemos las versiones compiladas.

Debemos seguir un estándar de codificación, el cual nos ayuda a:
- Generar código claro y consistente.
- Evitar perder tiempo en decisiones triviales.
- Tips para mejorar la legibilidad de nuestro código:
- Define un estándar: Piénsalo una vez y déjalo por escrito.
- Respétalo: Haz un esfuerzo por adherir al estándar durante tu día a día.
- Apóyate en algún linter: Esta sencilla herramienta te ayudará a incorporar buenas prácticas.

**Identificadores**

Los identificadores son variables, funciones, clases, módulos, componentes, etc. Elementos a los que nosotros debamos crearles un nombre propio.

Ejemplo sin un identificador mnemotécnico una función se vería así:

```
function f( int $b, int $a ) : float {
        return ( $b * $a ) / 2;
}
```

Al leer este código no sabemos para qué funciona y hasta podríamos borrarlo por equivocación.

Ahora utilizando un identificador mnemotécnico se vería así:
function areaRectangulo( int $base, int $altura ) : float {
        return ( $base * $altura ) / 2;
}

Ahora gracias a que el código es más legible sabemos para qué funciona esta función.
Atención a los identificadores que estableces.

**Código modular**
El código modular son pedazos de códigos divididos que pueden ser utilizados en cualquier lugar para evitar tener un solo archivo con un bloque de código gigante.

Este se trata de hacer código que este organizado de forma en pequeños bloques que se unan mediante código.
A mayor cantidad de código menos visible los bugs.
El tipo de código que con frecuencia vamos a modularizar son:
Los bloques que están dentro de un ciclo for o while
Los bloques dentro de un condicional
Código que hace calculos complejos

**Código reutilizable**
Escribir código reutilizable nos va a ayudar a que en lugar de copiar y pegar una misma línea de código pero con diferentes parámetros lo hagamos a través de una función que retorne los
valores que necesitamos y luego la podremos llamar en cualquier lugar del código que necesitemos pasándole los parámetros que deseamos.

Acá te dejo unos tips para hacer un buen código reutilizable:
Mantén tu código DRY (O SECO, en español). Es decir “Don’t Repeat Yourself” (O “No te repitas”)
Haz métodos o funciones que hagan solamente una cosa.
Haz pruebas unitarias para tus métodos y que sean fáciles de testear
Trata de pensar de forma abstracta, usa interfaces o clases abstractas
Escribe código que se pueda extender fácilmente en un futuro (Básicamente que modificarlo no signifique prenderle fuego a medio código)
No escribas código innecesario o que no hace falta en el momento.
Reduce el acoplamiento (Acoplamiento hace referencia a que, el comportamiento de una función depende enteramente de lo que retorne otra función, y esta de otra, y otra, y otra…)
Usa más código modular.
Escribe tu código como si fuera una API externa (Que se pueda importar de otro código y sirva completamente)

**Código organizado**
El código organizado se refiere a cómo tenemos distribuido nuestros archivos en la raíz (root) del proyecto. A mayor organización, mayor entendimiento del código.

Cuando hablamos de código organizado nos referimos a cómo está el código distribuido en nuestro sistema de archivos. Esto significa que necesitas organizar el código y que según cómo se
llame el archivo, este adentro debe contener únicamente lo que su nombre indica.

Quiere decir, que agruparemos archivos que tengan un contenido similar en directorios.
⭐ Esto se trata de convención, no una imposición.
PHP ej:
/public -> Código que se puede acceder desde fuera del server
/src -> Recursos o código fuete, generalmente el código escrito por nosotros
/tests -> Pruebas unitarias del proyecto
/vendor -> Librerias de terceros

**Evitar el Hardcoding**
El hardcoding es la práctica de escribir valores literales en lugar de identificadores. No debe de usarse, ya que si el día de mañana debemos cambiar los valores eso significa que debemos
cambiar el código en los lugares que esté ese valor estático por completo y luego mandar a producción, cuándo podríamos hacer el cambio más orgánico en una variable que afecte a todos los
lugares que es llamada.

Hardcoding escribir valores literales en lugar de identificadores. Lo ideal es tener un identificador que contenga un valor y ese identificador en cada lugar donde va el valor del
identificador.
Otro efecto que tiene el hardcodig es oculta información, cuando estas desarrollando tienes una lluvia de ideas y las escribes directo al código y después de algunos días ya no les encuentras sentido ya que toda la idea no se escribió o desarrollo bien.

**Evitar efectos colaterales**
Debemos analizar muy bien nuestro código para evitar efectos colaterales y evitar que nuestro código deje de funcionar. Un consejo de nuestro profesor en esta clase: No uses variables
globales.

Algo que sucede algo más allá del código del código que se esta leyendo, un ejemplo de esto es la modificación de una variable global. Mas preciso es realizar cosas que no van el la
función, es decir que la función no haga mas de una cosa, lo que indica su nombre.

**Módulo 5**
Principion SOLID

SOLID son cinco principios básicos de la programación orientada a objetos que ayudan a crear software mantenible en el tiempo.

SOLID significa:
S: Single Reponsibility Principle
O: Open/Closed Principle
L: Liskov Substitution Principle
I: Interface Segregation Principle
D: Dependency Inversion Principle
La S se trata de una clase que debe tener sólo una razón para cambiar.


**Single Reponsibility Principle**
El principio de responsabilidad única (también conocido como “la alta cohesión”) nos dice que una clase debería tener un único objetivo, muy claro, muy conciso y muy acotado.
La idea es evitar que una sola clase haga muchas cosas en lo que podría compararse con un “hombre orquesta”.

Este principio no solo se aplica a las clases, igual se aplica a las funciones, ¿Alguna vez has escuchado decir “una función debe hacer una única tarea”? Pues ahora sabes por qué

**Open/Closed Principle**
Establece que una entidad de software debe quedarse abierta para su extensión, pero cerrada para su modificación.

Una manera más fácil de ver este principio es:
“La clase debe quedar abierta para añadir nuevos features, pero que esos nuevos features no impliquen modificar el código que ya estaba (A eso se refiere cerrada para su modificación)”
Es decir, todo el código nuevo que metamos debe adaptarse automáticamente con el código viejo que ya teníamos y no debe implicar modificar este código viejo.
Abierto a nuevos features, cerrado a modificación de features antiguos.

**Liskov Substitution Principle**
El Liskov Substitution Principle establece que cada clase que hereda de otra puede usarse como su padre sin necesidad de conocer las diferencias entre ellas. Para que pueda darse este
principio debe cumplir con dos puntos:
El cliente debe usar métodos de la clase padre únicamente.
La clase hija no debe alterar el comportamiento de los métodos de la clase padre.

En palabra simples las clases que heredan de otras clases deben seguir comportándose como su padre, o sea, debemos derivar de una clase solamente para AÑADIR comportamientos, NO para
MODIFICAR el que ya existía.

**Interface Segregation Principle**
El Interface Segregation Principle establece que los clientes de un programa sólo deberían conocer de éste los métodos que realmente usan.

“Si una clase implementa una interfaz, y la interfaz le obliga definir un método que no necesita, entonces probablemente tu clase no está implementando la interfaz correcta”
Y una solución a ello puede ser:
Divide esa interfaz en interfaces más específicas, y en tus clases solo implementa las interfaces que necesites.

**Dependency Inversion Principle**
Dependency Inversion Principle detalla que los módulos de alto nivel no deben depender de los de bajo nivel, ambos deben depender de abstracciones.
Las abstracciones no deben depender de los detalles, los detalles deben depender de las abstracciones.

Modulo 6
Patrones de diseño
![Patrones_de_diseño](src/Patrones_de_diseño.jpg)

**Singleton**
Los patrones de diseño son soluciones de arquitectura de software aplicables a diferentes problemas.
El patrón Singleton permite restringir la creación de objetos pertenecientes a una clase o al valor de un tipo a un único objeto.

El patrón Singleton te dice que solo puede haber una instancia en toda la aplicación y sirve para ahorrar recursos, la idea es que sus constructores sean privados y que tengan un
método que retorne una instancia de la clase para asegurar que solo se está instanciando una sola vez.

**Factory**
El patron Factory es creacional, se utiliza para ayudar a la creación de nuevas instancias de objetos.

El patrón factory plantea simplificar una instancia, y eso lo podemos hacer por medio de otra clase que se encargue de obtener la instancia haciendo los procesos complejos requeridos, así
ante cualquier cambio solo modificamos esa clase factory y no nos preocupamos por modificar cada una de las instancias.

**Command**
El patrón Command permite solicitar una operación a un objeto sin conocer realmente el contenido de esta operación, ni el receptor real de la misma. Para ello se encapsula la petición como
un objeto, con lo que además facilita la parametrización de los métodos.

Se trata de un patrón de comportamiento, y este se utiliza cuando existe alguna operación especialmente compleja que debe ser realizada desde diferentes puntos de entrada.

¿Qué es una interfaz y qué son las clases abstractas?
La siguiente explicación menciona a Java pero se puede aplicar a muchos lenguajes de programación las misma definiciones:
Las clases abstractas cuando tienen métodos define lo que tienen qué hacer pero no cómo se debe de hacer. Estas clases pueden ser heredadas por X clases que necesitemos pero no pueden ser
instanciadas.
En Java no se puede heredar de más de una clase, para esto utilizamos las interfaces. Aquí igual se especifica qué se debe de hacer pero no el cómo.
A diferencia de una clase abstracta una interfaz no puede hacer nada por si sola, o sea, que las clases hijas están encargadas de definir el comportamiento de todos los métodos abstractos
de forma obligatoria.
En otra palabras, las interfaces serán contratos que indicarán que es lo que se debe de hacer sin proveer ninguna funcionalidad.

Modulo 7
Testings

**Introducción al Testing Automatizado**
Existen dos tipos de testing:
Unit Testing: Evaluamos el funcionamiento de los componentes individualmente.
Integration Testing: Validar la interacción entre los componentes y el sistema completo.

**Clase 21 - TDD**
Test Driven Development

Este consiste en primeros las pruebas y luego el software. Etapas:
Escribir un test que falle
Hacer que el código funcione
Eliminar la redundancia
Escribir el siguiente comando para que nos de los resultados del test mas el nombre del test.

Assert -> Aseveracion, decir que una cosa es tal y como se expresa.

**Clase 22 - Pull Request**
Los pull request son pedidos de mejora a archivos de un proyecto generalmente open source. Sirve para que la comunidad ayude a mejorar el código que ha sido escrito por ti, tu equipo o una
empresa; luego de que realizamos un cambio generamos un pull request para ofrecer un cambio a mejora y solo queda esperar a que el dueño del repositorio lo pruebe y lo agregue a el código
principal.

**Documentación**
Documentar es una de las mejores prácticas que podemos hacer cuando estamos en un equipo de trabajo. Dejar por escrito cómo hemos hecho algunas funcionalidades, cómo podría ser mejorado el
código y por sobretodo debemos dejar comentarios en el código que ayuden a las personas a ubicarse en qué parte de la aplicación están y qué hacen esas líneas de código.

¿Qué documentar?
Como implementar nueva funcionalidad.
Como se realizan las pruebas.
Lo mínimo que necesita las personas que quieren colaborar o heredar tu proyecto.
¿Como documentar?
UML como documentación.
¿Dónde documentar?
Propio código.
Sistema de documentación.
Wiki
Ficheros externos.
README
¿Cuándo documentar?
Documentar inmediatamente después de codear.
Cuando se resuelve un problema, documentar la solución.