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
Vamos a crear una Clase de utilidad, en Java tenemos que crear el **Package** de nuestro proyecto y el nombre del mismo se escribe de la siguiente manera:
*groupId.artifactId.className.*. En nuestro caso sera `com.platzi.javatests.util`  
Tener en cuenta que dentro del Package puede haber mas Packages para organizar nuestras Clases.

Dentro del Package creado, creamos nuestra Java Class **StringUtil**  
Dentro de esta Clase vamos a escribir una Function que sirve para repetir Strings. Va a ser la Clase de prueba a la que vamos a escribirle una serie de Tests.  
Apretando `Alt + Enter` sobre el nombre de la Clase podemos ver la opción para crear Test, y se usara con la Test library **JUnit4**  
Se crea una nueva Clase con el nombre de la Clase seleccionada agregandole la palabra *Test* al final.

En Intellij tenemos algunos shortcut
- `psvm` (Public Static Void Main) que nos crea automaticamente la función Main.
- `sout` -> `System.out.println();`
- `fori` -> Bucle For

Clase StringUtil.java
![03_Tests_Unitarios_01](src/Curso_Basico_de_Testing_en_Java/03_Tests_Unitarios_01.png)
Clase StringUtilTest.java
![03_Tests_Unitarios_02](src/Curso_Basico_de_Testing_en_Java/03_Tests_Unitarios_02.png)

---

### Clase 4 - Testing en Java con JUnit para verificar contraseñas

---

### Clase 5 - Creación de test unitario: lanzar una excepción para alertar sobre un error

---

### Clase 6 - Test unitario con JUnit

---

### Clase 7 - Organización de tests con JUnit

---

### Clase 8 - Test con Mockito para simular un dado

---

### Clase 9 - Test con Mockito: simular el uso de una pasarela de pago

---

### Clase 10 - Análisis de los tests y mejoras

---

### Clase 11 - Reto 1: Crear la función isEmpty

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