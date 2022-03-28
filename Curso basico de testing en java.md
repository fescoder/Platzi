![Curso Básico de Testing en Java](src/Curso_Basico_de_Testing_en_Java/Curso_Basico_de_Testing_en_Java.png)
# Curso básico de Testing en Java
Índice
-
- [Curso básico de Testing en Java](#curso-básico-de-testing-en-java)
    - [Módulo 1 - Bienvenida e introducción](#módulo-1---bienvenida-e-introducción)
        - [Clase 1 - Paso a paso para el testing básico en Java](#clase-1---paso-a-paso-para-testing-básico-en-java)
    - [Módulo 2 - Introducción a tests en software](#módulo-2---introducción-a-tests-en-software)
        - [Clase 2 - Tipos y beneficios de los tests](#clase-2---tipos-y-beneficios-de-los-tests)
    - [Módulo 3 - Preparación del IDE, proyecto y librerías](#módulo-3---preparación-del-ide-proyecto-y-librerías)
        - [Clase 3 - Instalación de Intellij IDEA, creación del proyecto con Maven y Test Unitarios](#clase-3---instalación-de-intellij-idea-creación-del-proyecto-con-maven-y-test-unitarios)
        - [Clase 4 - Testing en Java con JUnit para verificar contraseñas](#clase-4---testing-en-java-con-junit-para-verificar-contraseñas)
        - [Clase 5 - Creación de test unitario: lanzar una excepción para alertar sobre un error](#clase-5---creación-de-test-unitario-lanzar-una-excepción-para-alertar-sobre-un-error)
        - [Clase 6 - Test unitario con JUnit](#clase-6---test-unitario-con-junit)
        - [Clase 7 - Organización de tests con JUnit](#clase-7---organización-de-tests-con-junit)
        - [Clase 8 - Test con Mockito para simular un dado](#clase-8---test-con-mockito-para-simular-un-dado)
        - [Clase 9 - Test con Mockito: simular el uso de una pasarela de pago](#clase-9---test-con-mockito-simular-el-uso-de-una-pasarela-de-pago)
        - [Clase 10 - Análisis de los tests y mejoras](#clase-10---análisis-de-los-tests-y-mejoras)
        - [Clase 11 - Reto 1: Crear la función isEmpty](#clase-11---reto-1-crear-la-función-isempty)
    - [Módulo 4 - TDD](#módulo-4---tdd)
        - [Clase 12 - TDD: Definición, beneficios, ciclos y reglas](#clase-12---tdd-definición-beneficios-ciclos-y-reglas)
        - [Clase 13 - Ejemplos de TDD: Calcular el año bisiesto](#clase-13---ejemplos-de-tdd-calcular-el-año-bisiesto)
        - [Clase 14 - Ejemplos TDD: Cálculo de descuentos](#clase-14---ejemplos-tdd-cálculo-de-descuentos)
        - [Clase 15 - Reto 2: Práctica de TDD](#clase-15---reto-2-práctica-de-tdd)
    - [Módulo 5 - Tests en una aplicación](#módulo-5---tests-en-una-aplicación)
        - [Clase 16 - Organización de una aplicación](#clase-16---organización-de-una-aplicación)
        - [Clase 17 - App de películas: Test de negocio](#clase-17---app-de-películas-test-de-negocio)
        - [Clase 18 - App de películas: Test de búsqueda de películas por su duración](#clase-18---app-de-películas-test-de-búsqueda-de-películas-por-su-duración)
        - [Clase 19 - Creación de la base de datos y tests de integración con bases de datos](#clase-19---creación-de-la-base-de-datos-y-tests-de-integración-con-bases-de-datos)
        - [Clase 20 - Test de integración con bas de datos: Guardar películas y búsqueda de películas individuales](#clase-20---test-de-integración-con-bas-de-datos-guardar-películas-y-búsqueda-de-películas-individuales)
        - [Clase 21 - Reto 3: Nuevas opciones de búsqueda](#clase-21---reto-3-nuevas-opciones-de-búsqueda)
    - [Módulo 6 - Requerimientos y tests](#módulo-6---requerimientos-y-tests)
        - [Clase 22 - Test a partir de requerimiento](#clase-22---test-a-partir-de-requerimiento)
        - [Clase 23 - Reto 4: Búsqueda por varios atributos](#clase-23---reto-4-búsqueda-por-varios-atributos)
    - [Módulo 7 - Conclusiones](#módulo-7---conclusiones)
        - [Clase 24 - Resumen y conclusiones](#clase-24---resumen-y-conclusiones)

---

## Módulo 1 - Bienvenida e introducción
### Clase 1 - Paso a paso para testing básico en Java
Este curso aprenderás:

- ¿Qué es un test?
- ¿Para qué sirve?
- Tipos de test
- Partes de un test
- TDD (Test Driven Development)

En el curso programaremos utilizando el editor **IntelliJ IDEA**, además, usaremos librerías como **JUnit** y **Mockito**.

---

## Módulo 2 - Introducción a tests en software
### Clase 2 - Tipos y beneficios de los tests
**Beneficios**
- Comprobar los requerimientos de nuestra aplicación.
- Documentación y ejemplos de nuestras clases.
- Mediante Test Driven Development (TDD) nos puede ayudar en el diseño de clases.
- Confianza al desarrollar.
- Confianza para refactorizar nuestro código.
- Es una habilidad que se solicita cada vez más en el mercado.

Existen test automáticos y manuales, los automáticos van a requerir tiempo de desarrollo y algunas veces no serán tan viables, pero de ser posible siempre trata de hacer test automáticos ya que:
- Son más rápidos.
- Son más fiables.
- Son incrementales.

**Tipos de test**
- Unitario: realizan pruebas a una función o clase muy concreta de nuestro proyecto.
- Integración: prueban cómo se conectan diferentes componentes de nuestro proyecto.
- Funcionales: prueban una funcionalidad de nuestro proyecto, pueden involucrarse varias clases.
- Inicio a fin: prueba todo un proceso del proyecto.
- Estrés: útil para probar si nuestra aplicación puede soportar grandes cantidades de procesos y peticiones a la vez.

---

## Módulo 3 - Preparación del IDE, proyecto y librerías
### Clase 3 - Instalación de Intellij IDEA, creación del proyecto con Maven y Test Unitarios
Vamos a descargar el editor IntelliJ IDEA y crear un proyecto en Maven. Para indicarle a Maven que usaremos Java 8 debemos añadir las siguientes líneas de código:
~~~
<properties>
    <maven.compiler.source>1.8maven.compiler.source>
    <maven.compiler.target>1.8maven.compiler.target>
</properties>
~~~
Vamos a crear una Clase de utilidad, en Java tenemos que crear el **Package** de nuestro proyecto y el nombre del mismo se escribe de la siguiente manera ->
*groupId.artifactId.className*.  
En nuestro caso sera `com.platzi.javatests.util`  
Tener en cuenta que dentro del Package puede haber mas Packages para organizar nuestras Clases.

Dentro del Package creado, creamos nuestra Java Class **StringUtil**  
Dentro de esta Clase vamos a escribir una Function que sirve para repetir Strings, va a ser la Clase de prueba a la que vamos a escribirle una serie de Tests.  
Apretando `Alt + Enter` sobre el nombre de la Clase podemos ver la opción para crear Test, y se usara con la Test library **JUnit4** (Una libreria de Java para escribir tests)

![03_Tests_Unitarios_03](src/Curso_Basico_de_Testing_en_Java/03_Tests_Unitarios_03.png)

Se crea una nueva Clase con el nombre de la Clase seleccionada agregandole la palabra *Test* al final.

En Intellij tenemos algunos **shortcut**
- `psvm` (Public Static Void Main) que nos crea automaticamente la función Main.
- `sout` -> `System.out.println();`
- `fori` -> Bucle For

Clase StringUtil
![03_Tests_Unitarios_01](src/Curso_Basico_de_Testing_en_Java/03_Tests_Unitarios_01.png)

Clase StringUtilTest
![03_Tests_Unitarios_02](src/Curso_Basico_de_Testing_en_Java/03_Tests_Unitarios_02.png)

---

### Clase 4 - Testing en Java con JUnit para verificar contraseñas
En esta clase se realizan Tests para verificar el nivel de seguridad del password.

**Shortcut**  
`Alt + Insert` -> en un espacio vacío para escribir un método de Test  
![04_Testing_en_Java_con_JUnit_para_Verificar_Contrasenas_03](src/Curso_Basico_de_Testing_en_Java/04_Testing_en_Java_con_JUnit_para_Verificar_Contrasenas_03.png)

PasswordUtil
![04_Testing_en_Java_con_JUnit_para_Verificar_Contrasenas_01](src/Curso_Basico_de_Testing_en_Java/04_Testing_en_Java_con_JUnit_para_Verificar_Contrasenas_01.png)

PasswordUtilTest
![04_Testing_en_Java_con_JUnit_para_Verificar_Contrasenas_02](src/Curso_Basico_de_Testing_en_Java/04_Testing_en_Java_con_JUnit_para_Verificar_Contrasenas_02.png)

---

### Clase 5 - Creación de test unitario: lanzar una excepción para alertar sobre un error
Vamos a utilizar una excepción con la función **throw new RuntimeException("Error")** en lugar de la función System.out.println("Error") para identificar más fácil los errores.
Ahora, los mensajes tendrán un color diferente y pueden mostrarnos un poco más de información sobre los errores: ubicación, el resultado esperado, mensajes personalizados, entre otros.

**Shortcut**  
`thr` -> throw new

Algunas definiciónes de JUnit  
![05_JUnit_test_definitions](src/Curso_Basico_de_Testing_en_Java/05_JUnit_test_definitions.jpg)

StringUtilTest  
![05_Creación_de_test_unitario_01](src/Curso_Basico_de_Testing_en_Java/05_Creación_de_test_unitario_01.png)

Yo ya tenia la libreria agregada por eso no me hizo falta crear desde cero esa función.

---

### Clase 6 - Test unitario con JUnit
Vamos a añadir Junit a nuestro proyecto copiando las siguientes líneas de código:
~~~
<dependencies>
  <dependency>
    <groupId>junit</groupId>
    <artifactId>junit</artifactId>
    <version>4.12</version>
     <scope>test</scope>
  </dependency>
</dependencies>
~~~

La función **assertEquals** de JUnit se encarga de comprobar que dos valores sean iguales, en este caso comprobar si nuestra función **repeat** retorna el valor esperado.

Debemos indicarle a JUnit mediante **@Test** que función va a realizar una prueba.

Con `Ctrl + P` -> Podemos ver los parámetros que pide una función.

![06_Test_unitario_con_JUnit_01](src/Curso_Basico_de_Testing_en_Java/06_Test_unitario_con_JUnit_01.png)

---

### Clase 7 - Organización de tests con JUnit
La forma correcta de separar nuestras pruebas es realizar cada una en su propia función, además, el nombre de la función debe describir que estamos probando.

Para indicarle a JUnit que esperamos una excepción lo debemos hacer de la siguiente forma:

~~~
@Test(expected = IllegalArgumentException.class)
~~~

![07_Organizacion_de_tests_con_JUnit_01](src/Curso_Basico_de_Testing_en_Java/07_Organizacion_de_tests_con_JUnit_01.png)
![07_Organizacion_de_tests_con_JUnit_02](src/Curso_Basico_de_Testing_en_Java/07_Organizacion_de_tests_con_JUnit_02.png)

---

### Clase 8 - Test con Mockito para simular un dado
**Mockito** nos va a servir para simular clases mientras probamos, para añadirlo a nuestro proyecto debemos copiar las siguientes líneas de código:
~~~
<dependency>
  <groupId>org.mockito</groupId>
  <artifactId>mockito-core</artifactId>
  <version>2.23.4</version>
  <scope>test</scope>
</dependency>
~~~
Para instanciar un mock debemos utilizar la función **Mockito.mock()** e indicarle como parámetro la clase que va a simular.
Las funciones **assertFalse** y **assertTrue** tal como su nombre lo indican, sirven para comprobar si un valor es igual a **false** o **true** respectivamente.

Creamos la Clase *Player*, en un nuevo Package, con su constructor y una método que devuelve un booleano que dice si ganó o perdió.
![08_Test_con_Mockito_para_simular_un_dado_01](src/Curso_Basico_de_Testing_en_Java/08_Test_con_Mockito_para_simular_un_dado_01.png)

Creamos la Clase *Dice* que devuelve un numero random cuando se ejecuta la función *roll()*
![08_Test_con_Mockito_para_simular_un_dado_02](src/Curso_Basico_de_Testing_en_Java/08_Test_con_Mockito_para_simular_un_dado_02.png)

Creamos 2 tests (Perder y Ganar) utilizando *Mockito* para simular el dado y forzar el resultado que devuelve la clase Dice cuando se tira.
![08_Test_con_Mockito_para_simular_un_dado_03](src/Curso_Basico_de_Testing_en_Java/08_Test_con_Mockito_para_simular_un_dado_03.png)

Podriamos decir que **Mockito** se usa para simular clases con las que se interactua o depende de ellas, muchas veces una clase depende de otros módulos y al momento de ejecutar un test,
no se sabe si el error proviene de la clase que ejecuta test o el modulo del cual depende.
Por ejemplo, si tengo una aplicación que usa una API para pedir datos sobre la temperatura de una zona específica, y en base a eso decir si la temperatura > 30°, usar bloqueador solar.
No puedo comprobar al momento del test si la API tendrá algún error y que mi test sea invalido. Debería usar Mockito para desacoplar la dependencia a la API y poder así testear mi clase
sola.

---

### Clase 9 - Test con Mockito: simular el uso de una pasarela de pago
Simular una pasarela de pagos nos ayuda a probar todas las funcionalidades de nuestra aplicación sin gastar dinero en pagos reales.

Creamos un nuevo Package ***Payments*** donde alojaremos nuestras clases y la interface ***PaymentGateway***

**Shorcut**  
`get` -> Intellij crea el método get() de alguna variable creada.

Clases creadas  
![09_Test_con_Mockito_pasarela_de_pago_01](src/Curso_Basico_de_Testing_en_Java/09_Test_con_Mockito_pasarela_de_pago_01.png)

![09_Test_con_Mockito_pasarela_de_pago_02](src/Curso_Basico_de_Testing_en_Java/09_Test_con_Mockito_pasarela_de_pago_02.png)

![09_Test_con_Mockito_pasarela_de_pago_03](src/Curso_Basico_de_Testing_en_Java/09_Test_con_Mockito_pasarela_de_pago_03.png)

![09_Test_con_Mockito_pasarela_de_pago_04](src/Curso_Basico_de_Testing_en_Java/09_Test_con_Mockito_pasarela_de_pago_04.png)

![09_Test_con_Mockito_pasarela_de_pago_05](src/Curso_Basico_de_Testing_en_Java/09_Test_con_Mockito_pasarela_de_pago_05.png)

---

### Clase 10 - Análisis de los tests y mejoras
Nuestros test siguen un mismo proceso:
- Se preparan los objetos que vamos a probar.
- Llamamos al método que estamos probando.
- Comprobamos los resultados.  
Podemos reducir la cantidad de código moviendo las partes comunes de preparación a una función que se ejecute antes de cada prueba.
Con **@Before** le indicamos a JUnit la función que debe ejecutar antes de cada prueba.

En las imagenes vemos las separaciones de las partes de los tests  
![10_Analisis_de_los_tests_y_mejoras_01](src/Curso_Basico_de_Testing_en_Java/10_Analisis_de_los_tests_y_mejoras_01.png)

Y como a veces un código se puede repetir en varias pruebas, por eso se crea una función comun *(setup())*, en este caso para inicializar las variables.
![10_Analisis_de_los_tests_y_mejoras_02](src/Curso_Basico_de_Testing_en_Java/10_Analisis_de_los_tests_y_mejoras_02.png)

---

### Clase 11 - Reto 1: Crear la función isEmpty
![11_Reto_1_crear_la_funcion_isEmpty_01](src/Curso_Basico_de_Testing_en_Java/11_Reto_1_crear_la_funcion_isEmpty_01.png)

![11_Reto_1_crear_la_funcion_isEmpty_02](src/Curso_Basico_de_Testing_en_Java/11_Reto_1_crear_la_funcion_isEmpty_02.png)

---

## Módulo 4 - TDD
### Clase 12 - TDD: Definición, beneficios, ciclos y reglas

---

### Clase 13 - Ejemplos de TDD: Calcular el año bisiesto

---

### Clase 14 - Ejemplos TDD: Cálculo de descuentos

---

### Clase 15 - Reto 2: Práctica de TDD

---

## Módulo 5 - Tests en una aplicación
### Clase 16 - Organización de una aplicación

---

### Clase 17 - App de películas: Test de negocio

---

### Clase 18 - App de películas: Test de búsqueda de películas por su duración

---

### Clase 19 - Creación de la base de datos y tests de integración con bases de datos

---

### Clase 20 - Test de integración con bas de datos: Guardar películas y búsqueda de películas individuales

---

### Clase 21 - Reto 3: Nuevas opciones de búsqueda

---

## Módulo 6 - Requerimientos y tests
### Clase 22 - Test a partir de requerimiento

---

### Clase 23 - Reto 4: Búsqueda por varios atributos

---

## Módulo 7 - Conclusiones
### Clase 24 - Resumen y conclusiones

---