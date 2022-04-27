![00_Curso_Programaciokn_funcional_Java_SE](src/Curso_Programacion_Funcional_Java_SE/00_Curso_Programaciokn_funcional_Java_SE.webp)
# Curso de Programación Funcional con Java SE
Índice
-
- [Curso de Programación Funcional con Java SE](#curso-de-programación-funcional-con-java-se)
    - [Módulo 1 - Introducción a la Programación Funcional](#módulo-1---introducción-a-la-programación-funcional)
        - [Clase 1 - ¿Qué es la Programación Funcional?](#clase-1---¿qué-es-la-programación-funcional)
    - [Módulo 2 - Entendiendo las partes de la Programación Funcional](#módulo-2---entendiendo-las-partes-de-la-programación-funcional)
        - [Clase 2 - ¿Qué es una función en Java](#clase-2---¿qué-es-una-función-en-java)
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
- Funciones
- Datos

Entendiendo que es una **Función** y que tipo de **Datos** hay, podremos generar muchísimas de las partes de la programación funcional.  
Básicamente la prog funcional se enfoca en **QUE** resolver y no en COMO resolver, generalmente cuando pensamos en POO pensamos mucho en vamos a crear esta clase, que genera este
objeto, que va a generar esta otra clase, en la prog funcional estamos más preocupados por resolver el problema, no en que elementos están involucrados, lo importante es tener una función
que pueda resolver el problema, no importa su procedencia, y en la parte de los datos vamos a aprender que son los datos mutables e inmutables, esto es muy importante porque esto nos va a
poder dar diferentes tipos de funciones, según los datos que tengamos.  
Es importante recalcar que esto ya existe en Java en versiones anteriores, solo que ahora haremos un mayor énfasis en como obtenerlo en el lenguaje para que nuestras funciones puedan ser
más simples.

La prog funcional entonces nos va a dar ciertos beneficios:
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

---

## Módulo 2 - Entendiendo las partes de la programación funcional
### Clase 2 - ¿Qué es una función en Java?

---

### Clase 3 - Funciones como ciudadanos de primera clase

---

### Clase 4 - Funciones puras

---

### Clase 5 - Entendiendo los efectos secundarios

---

### Clase 6 - Funciones de orden mayor

---

### Clase 7 - Funciones lambda

---

### Clase 8 - Inmutabilidad

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