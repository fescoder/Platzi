![MitoCode_logo](src/Tutorial_Java_MitoCode/MitoCode_logo.png)
# Java Tutorial MitoCode
Índice
-
- [Tutorial Java 7 SE](#tutorial-java-7-se)
    - [36- Colecciones + iterador](#36-colecciones--iterador)
    - [37- ArrayList](#37--arraylist)
    - [38- LinkedList](#38--linkedlist-o-listas-enlazadas)
    - [39- HashMap](#39--hashmap)
    - [40- HashSet](#40--hashset)
    - [41- Exceptions](#41--exceptions)
    - [42- Jerarquía de Exceptions](#42--jerarquía-de-exceptions)
    - [43- Lanzar Exceptions - Throw y Throws](#43--lanzar-exceptions---throw-ythrows)
    - [44- Exceptions personalizadas](#44--exceptions-personalizadas)
    - [45- Files](#45--files)
    - [46 -Lectura de Archivos](#46--lectura-de-archivos)
    - [47- Escritura de Archivos](#47--escritura-de-archivos)
    - [48- try with resources](#48--try-with-resources)
    - [49- Conexión a Base de Datos](#49--conexión-a-base-de-datos)
    - [50- Insercción a BD con parámetros](#50--inserción-a-db-con-parámetros)
    - [51- Listar desde BD](#51--listar-desde-db)
    - [52- Patrón DAO](#52--patrón-dao)
- [Tutorial Java 7 SE Avanzado](#tutorial-java-7-se-avanzado)
    - [10- Ordenar colecciones](#10--ordenar-colecciones)
- [Tutorial Java 8](#tutorial-java-8)
    - [1- Paradigma Funcional](#paradigma-funcional)
    - [2- Lambda](#lambda)

---

# Tutorial Java 7 SE
## 36- Colecciones + iterador
Una coleccion de objetos es un objeto que se puede almacenar un número variable de elementos, siendo cada elemento otro objeto. Podriamos verlo como una caja que contiene mas cajas dentro.
Puede haber distintos tipos de colecciones de tamaño flexible, es decir que se pueden encoger o agrandar según las nececidades.

![36_Colecciones_e_iterador_01](src/Tutorial_Java_MitoCode/36_Colecciones_e_iterador_01.png)

Entonces teniendo esta imagen podemos decir que nosotros vamos a utilizar una Clase en particular que implementa una interfaz para poder empezar la agrupación de elementos.  
`List<String> lista = new ArrayList();`  
En esta linea de código podemos decir que declaramos el objeto llamado ***lista*** pertenece a la interfaz Lista de tipo String, y que a su vez estamos generando una instancia de la
clase ArrayList.

El Iterator instanciado es un objeto que nos permite recorrer una lista.  
`Iterator<String> iterator = lista.iterator();`  
y con este objeto podemos hacer lo siguiente:  
~~~
while(iterador.hasNext()){
    System.out.println(iterador.next());
}
~~~
Ambas hacen lo mismo, pero es mas práctico con un for para recorrer la lista, esto fue a modo de demostración.
~~~
for(String s : lista){
    System.out.println(s);
}
~~~
Esto es importante porque cuando trabajemos con BD, en muchas ocaciones vamos a requerir traer una lista, lo mas recomendable es traer esa lista en base a una coleccion de objetos y la
mejor manera de trabajar esta coleccion es por medio de listas.

---

## 37- ArrayList
ArrayList viene de la interfaz Lista, y ésta de Collection e Iterable (Se ve en la imagen de la clase anterior).  
Se explica que para mejorar el rendimiento del sistema, si se sabe la cantidad de espacio de memoria que se le puede asignar a la lista, es decir la cantidad de objetos que va a almacenar
conviene declararlo al instanciar el ArrayList y asi nos ahorramos tiempo y procesos a la hora de la ejecución.  
`List<Integer> lista = new ArrayList(10);`

Al utilizar listas tenemos a disposicion determinados métodos, por ejemplo el `get(int index)` que se le pasa una referencia del elemento que queremos.
- `add()` Para agregar a una coleccion
- `clear()` Limpiar todo el arreglo
- `contains()` Si se encuentra en el arreglo
- `isEmpty()` Para ver si esta vacio el array
- `iterator()` Recorrerlo como si fuera un iterador
- `size` Obtener el tamaño  
Y muchos más.

---

## 38- LinkedList o Listas enlazadas
Una lista enlazada tiene la particularidad de que sus elementos tienen una referencia con su próximo.  
![38_LinkedList_01](src/Tutorial_Java_MitoCode/38_LinkedList_01.png)

Y lo podemos declarar asi:  
`List lista = new LinkedList();`  
Tambien podriamos poner de que tipo es esa lista, pero al no declararlo podemos agregar objetos de varios tipos.  
`List<Integer> lista = new LinkedList();`  
Ó apoyandonos en la clase directamente:  
`LinkedList lista = new LinkedList();`

Veamos en que situaciónes es conveniente usar el LinkedList antes que un ArrayList  
Tiempos que tardan en ejecutar el agregado, lectura y eliminación de la lista.  
![38_LinkedList_02](src/Tutorial_Java_MitoCode/38_LinkedList_02.png)  
La diferencia sustancial es la obtencion del elemento de parte del ArrayList, porque? porque en LinkedList tenemos referencias uno con el otro, entonces cuando quiero obtener un elemento
en el ArrayList simplemente voy directo a él, mientras que el LinkedList tiene que recorrer toda la lista.  
Y en el agregado y eliminación es más rapida el LinkedList. Ahí sus diferencias y cuando conviene usar cada uno.

---

## 39- HashMap
Hashmap (Diccionario)  
Básicamente este tipo de dato nos va a permitir tener varios elementos pero a cada elemento le vamos a poder asociar una KEY.  
Declaración:  
`Map diccionario = new HashMap();`  
Ó mediante la Clase  
`HashMap diccionario = new HashMap();`

![39_HashMap_01](src/Tutorial_Java_MitoCode/39_HashMap_01.png)

Para agregar valores a nuestro diccionario en vez de utilizar como en el ArrayList el método `add()` lo hacemos con el método `put()` al cual le pasamos 2 argumentos, el KEY y el VALOR.  
Se pueden acceder a estos elementos usando la función `diccionario.get()` pasandole la KEY y nos devuelve el valor.  
Tambien podemos ver si existe una KEY o un VALOR en nuestro diccionario usando el método `containsKey()` ó `containsValue()`, devuelve un booleano.  
Y demas funciones que se pueden investigar.

Se usan mucho cuando se necesita pasar parametros a librerias para reportes, se usan el objeto que tenga la relación key-value.

---

## 40- HashSet
Se destaca por no tener un orden en la lista, siempre es aleatorio y no permite valores repetidos (si guardarlos pero no los devuelve al leer los elementos).

![40_HashSet_01](src/Tutorial_Java_MitoCode/40_HashSet_01.png)

![40_HashSet_02](src/Tutorial_Java_MitoCode/40_HashSet_02.png)

---

## 41- Exceptions
Una Exception notifica cuando hay algun error en el proceso.  
Para poder manejarlas utilizamos el try-catch-finally  
En este ejemplo se trata de divir un numero por cero y la exception es tratada y reportada.  
![41_Exceptions_01](src/Tutorial_Java_MitoCode/41_Exceptions_01.png)

---

## 42- Jerarquía de Exceptions
Cuando tratas de capturar una exception de nivel mayor no es necesario ni posible capturar otra de nivel inferior ya que la superior lo abarca y trata.  
Esta es la jerarquia y algunas exceptions.  
![42_jerarquia_exceptions_01](src/Tutorial_Java_MitoCode/42_jerarquia_exceptions_01.png)

![42_jerarquia_exceptions_02](src/Tutorial_Java_MitoCode/42_jerarquia_exceptions_02.png)

![42_jerarquia_exceptions_03](src/Tutorial_Java_MitoCode/42_jerarquia_exceptions_03.png)

---

## 43- Lanzar Exceptions - Throw yThrows
Aqui veremos como delegar una Exception a un método que está un nivel superior.  
Cuando desarrollamos aplicativos o sistemas se manejan las programaciones por capas, es decir que esta modularizado, y no necesariamente se manejan los errores donde se producen.  
A veces se tratan los errores en un nivel superior mucho mas arriba y donde la capa inferior unicamente tenga que informar que ha ocurrido un error.  

![43_Throw_Throws_01](src/Tutorial_Java_MitoCode/43_Throw_Throws_01.png)

`throw e` o `throw new NombreException` (para lanzar una nueva excepción)  
la **e** es la instancia de una clase que necesita throw, esta arroja la exception, el mensaje va a la capa superior (en este caso al método 2) y a su vez el método 3 tiene que
ser implementado con `throws Exception`, que **Exception** es la espificación de la clase, con este indicamos que puede transferir una exception.

---

## 44- Exceptions personalizadas
En algunos sistemas tenemos alguna lógica de negocio en particular en donde tenemos que manejar ciertas situaciones o errores, errores propios, personalizables y pueden servir para
ordenar nuestro código.

Por ejemplo vamos a verificar la edad que el usuario ingrese una edad valida y poder avisar al usuario caso que suceda una excepción. Es decir una edad muy grande 200 o 500 por ejemplo.

Entonces empezamos por crear una Clase EdadException.  
![44_Excepciones_personalizadas_01](src/Tutorial_Java_MitoCode/44_Excepciones_personalizadas_01.png)

Aquí la lógica del proceso y lanzamientos de exceptions de 2 maneras diferentes  
![44_Excepciones_personalizadas_02](src/Tutorial_Java_MitoCode/44_Excepciones_personalizadas_02.png)

![44_Excepciones_personalizadas_03](src/Tutorial_Java_MitoCode/44_Excepciones_personalizadas_03.png)

---

## 45- Files
Manejo de archivos desde Java.  
![45_Files_01](src/Tutorial_Java_MitoCode/45_Files_01.png)

Para empezar a manipular un archivo en Java es necesario hacer la referencia  
`File archivo = new File()` y se importa la libreria.  
Y le enviamos como parametro la ruta del archivo.

La clase tiene varios métodos para el manejo, `canRead()`, `canWrite()`, `canExecute()`, `delete()`, `exists()` y más.  
Es buena práctica siempre preguntar si existe o no dicho archivo.  
Con `mkdir()` podemos crear el directorio si no existe, con `mkdirs()` crea todos las carpetas en la ruta escrita que faltan.  
Con `renameTo(new File("Ruta de archivo"))` renombra al file con el contenido identico.  

![45_Files_02](src/Tutorial_Java_MitoCode/45_Files_02.png)

---

## 46- Lectura de archivos
Lectura de archivos planos, sin embargo hay que tener en cuenta que cuando hablamos de lectura de archivos, debemos pensar en que tipo de archivo es.  
Si estamos leyendo una imagen por ejemplo, es común que se encuentra guardada en una base de datos o en un repositorio en formato de Bytes.

![46_Lectura_de_archivos_01](src/Tutorial_Java_MitoCode/46_Lectura_de_archivos_01.png)

Y para este tipo de lectura seria mas conveniente una clase que sea de tipo `Stream`.  
Ahora nos vamos a trabajar con texto plano, un .txt, leer el contenido y mostrarlo en consola.  
Para esto necesito apoyarme en una clase llamada `FileReader()` que captura el archivo y en `BufferedReader()` para poder recorrer el contenido del archivo.  

![46_Lectura_de_archivos_02](src/Tutorial_Java_MitoCode/46_Lectura_de_archivos_02.png)

Tambien podriamos hacerlo con la clase `FileInputStream` y nos ayudamos con `Scanner` de la siguiente manera.  

![46_Lectura_de_archivos_03](src/Tutorial_Java_MitoCode/46_Lectura_de_archivos_03.png)

---

## 47- Escritura de archivos
Nos apoyaremos en dos clases para la escritura de archivos.  
`FileWriter` y `PrintWriter` y el try-catch para el manejo de excepciones. En este caso si existe el archivo sobreescribimos lo que hay en él.

![47_Escritura_de_archivos_01.png](src/Tutorial_Java_MitoCode/47_Escritura_de_archivos_01.png)

Pero si queremos agregar simplemente tenemos que pasarle **True** como segundo parámetro al FileWriter.  
`archivo = new FileWriter("D:\\ejemplo\\mitocode.txt", true);`

---

## 48- Try with resources
Esto simplifica un poco mas el ejemplo anterior ya que se Java maneja el archivo internamente.

![48_Try_with_resources_01.png](src/Tutorial_Java_MitoCode/48_Try_with_resources_01.png)

---

## 49- Conexión a Base de Datos
Java por defecto trae un API para poder utilizar los métodos que se proporcionen y acceder a la base de datos, se trata de ***JDBC***(Java Data Base Connectivity).  
Son los mecanismos que nos van a ayudar a poder interactuar con diferentes DB, sea SQL Server, Postgres, MySQL, o cualquier otra.  
Necesitamos tener instalado una base de datos y descargado la libreria para esa DB, en este caso es **postgresql-9.4-1201.jdbc41.jar**

![49_Conexion_DB_01.png](src/Tutorial_Java_MitoCode/49_Conexion_DB_01.png)

`JDBC_DRIVER` Indica a que tipo de base de datos nos estamos conectando.  
`DB_URL` Es la ruta en el cual estamos haciendo la conexión y tiene esta estructura -> `conector:tipo de DB://servidor: puerto/ nombre de DB`  
`Connection` Es una clase que necesitamos para conectarnos y utiliza la Clase `DriveManager` al cual le pasamos los parametros necesarios.  
`PreparedStatement` Es una clase que nos da Java para poder interactuar operaciones en DB, al cual le pasamos una sentencia SQL, ejecutamos y cerramos.  
Y por ultimo siempre cerrar la conexión.  

![49_Conexion_DB_02.png](src/Tutorial_Java_MitoCode/49_Conexion_DB_02.png)

Ahora veremos una forma mas simple para ahorrar lineas de código, con el ***Try with resources***, agregando en el Try la sentencia correspondiente y quitariamos el Finally
ya que estaria de manera implicita ya que el TWR lo manejaria.

![49_Conexion_DB_03.png](src/Tutorial_Java_MitoCode/49_Conexion_DB_03.png)

---

## 50- Inserción a DB con parámetros
Ahora insertaremos los valores de forma dinámica, es decir solicitaremos datos al usuario para poder guardarlos.

![50_Inserccion_DB_parametros_01.png](src/Tutorial_Java_MitoCode/50_Inserccion_DB_parametros_01.png)

En Values cada **?** representa un parámetro, y para definir el valor para ese signo lo hacemos con `setString(numParametro, valorParametro)`.  
Si fuese un int seria `setInt()`

![50_Inserccion_DB_parametros_02](src/Tutorial_Java_MitoCode/50_Inserccion_DB_parametros_02.png)

Y el método main quedaria asi:

![50_Inserccion_DB_parametros_03](src/Tutorial_Java_MitoCode/50_Inserccion_DB_parametros_03.png)

---

## 51- Listar desde DB
Recuperar datos de DB y mostrar al usuario.  
En este casi creamos una nueva función y cambiamos el Statement por `SELECT * FROM persona` y en vez de un executeUpdate() usaremos `executeQuery()` que nos devuelve un
**ResultSet** (un dato de tipo particular que nos ayuda a contener toda la información que nos devuelve la query).  
Recorremos el **rs** con next(), es decir, mientras tenga contenido el rs y lo guardamos todo en un objeto Persona con variables con los mismos nombres que tienen en la base (id y Nombre)  
Todo esto irá guardado en una Lista para manejarlo mejor, recorrerlo en el main y mostrar los datos.

![51_Listar_DB_01](src/Tutorial_Java_MitoCode/51_Listar_DB_01.png)

![51_Listar_DB_02](src/Tutorial_Java_MitoCode/51_Listar_DB_02.png)

---

## 52- Patrón DAO
Es un patrón de diseño muy importante a la hora de manejar conexiones a base de datos, la DAO (Data Access Object).  
Un patrón es un conjunto de buenas practicas que te permite ordenar tu manera de trabajo, nuestro código, de manera que sea mantenible en el tiempo y que si viene otro programador
pueda entender el estilo de esta programación.  
El DAO especificamente lo que hace es separar la lógica del negocio, de la aplicación, de la lógica del acceso a la DB, con el fin de tener un orden en nuestor código.  
Para empezar creamos un nuevo paquete **dao**, con la clase Conexion y en él indicamos todos los atributos y métodos que usamos anteriormente para conectarnos, y creamos dos métodos para
conectar y cerrar la DB.

![52_Patron_DAO_01](src/Tutorial_Java_MitoCode/52_Patron_DAO_01.png)

Creamos otro paquete llamado **Interfaces**, definimos una interface llamada **DAOPersona** y definimos las operaciones que soporta la interfaz.

![52_Patron_DAO_02](src/Tutorial_Java_MitoCode/52_Patron_DAO_02.png)

Creamos una nueva clase en el package DAO a la que llamamos **DAOPersonaImpl** (impl viene de implementacion, por la interfaz), heradamos de conexion e implementamos la interface.  
A continuación se muestran las implementaciones de los métodos.

**Registrar**
![52_Patron_DAO_03](src/Tutorial_Java_MitoCode/52_Patron_DAO_03.png)

**Modificar** `"UPDATE Persona set nombre = ? where id = ?"`
![52_Patron_DAO_04](src/Tutorial_Java_MitoCode/52_Patron_DAO_04.png)

**Eliminar**
![52_Patron_DAO_05](src/Tutorial_Java_MitoCode/52_Patron_DAO_05.png)

**Listar**
![52_Patron_DAO_06](src/Tutorial_Java_MitoCode/52_Patron_DAO_06.png)

Ahora en el main agregamos una Persona.

![52_Patron_DAO_07](src/Tutorial_Java_MitoCode/52_Patron_DAO_07.png)

Modificamos una Persona.

![52_Patron_DAO_08](src/Tutorial_Java_MitoCode/52_Patron_DAO_08.png)

Eliminamos una Persona.

![52_Patron_DAO_09](src/Tutorial_Java_MitoCode/52_Patron_DAO_09.png)

Listamos las Personas en nuestra DB.

![52_Patron_DAO_10](src/Tutorial_Java_MitoCode/52_Patron_DAO_10.png)

Estructura con DAO

![52_Patron_DAO_11](src/Tutorial_Java_MitoCode/52_Patron_DAO_11.png)

---

# Tutorial Java 7 SE Avanzado
## 1- Introducción
En esta primer clase muestra como funciona el mandarle parámetros al método main e imprime los mismos.

![01_Introduccion_01](src/Tutorial_Java_MitoCode/01_Introduccion_01.png)

---

## 2- Proyecto Maven
[Construcción con Maven](https://www.youtube.com/watch?v=3RunOD1VBco&list=PLvimn1Ins-43qPXR3gBcxwe7tydxZtsON&index=2)

---

## 3- Instancia y Static
Un método de instancia no puede ser sobreescrito por un método estatico ni viceversa.

![03_Instancia_Static_01](src/Tutorial_Java_MitoCode/03_Instancia_Static_01.png)

La clase hija siempre se ejecuta en vez de la clase padre

![03_Instancia_Static_02](src/Tutorial_Java_MitoCode/03_Instancia_Static_02.png)

---

## 4- InstanceOf
Este operador nos permite conocer de que tipo o instancia es un determiando objeto, saber de que clase es.  
Sabiendo que Alumno hereda de Persona también funciona.

![04_InstanceOf_01](src/Tutorial_Java_MitoCode/04_InstanceOf_01.png)

Ejemplo práctico con una canasta de frutas.

![04_InstanceOf_02](src/Tutorial_Java_MitoCode/04_InstanceOf_02.png)

![04_InstanceOf_03](src/Tutorial_Java_MitoCode/04_InstanceOf_03.png)

---

## 5- Singleton
Es un patron de diseño que nos permite tener una unica instancia de una clase particular.

[Patrón Singleton](https://www.youtube.com/watch?v=qiFeiYLzIH8&list=PLvimn1Ins-43qPXR3gBcxwe7tydxZtsON&index=5)

---

## 6- Genéricos I
Cuando hablamos de genéricos en Java estamos haciendo mención a que una clase va a poder implementar un determinado tipo de elemento.  
Creación de una clase genérica y sus estereotipos más comúnes.  
`List lista = new ArrayList();` -> Esta lista puede almacenar cualquier tipo de elemento, pero en los sistemas reales se espicifica que tipo se almacenaran.  
`List <Integer> lista = new ArrayList();` -> De esta forma, con el operador `<>` indicamos de que tipo se va a guardar, puede ser tmb String o uno customizable como Persona.

Crearemos una clase generica, siguiente al nombre de la clase escribimos `<T>`, **T** es una letra de un estereotipo, existen varios.  
Si consiguiente instanciamos un objeto de tipo generico no nos va a tirar error ya que entiende que se va a implementar más adelante.  

![06_Genericos_I_01](src/Tutorial_Java_MitoCode/06_Genericos_I_01.png)

![06_Genericos_I_02](src/Tutorial_Java_MitoCode/06_Genericos_I_02.png)

![06_Genericos_I_03](src/Tutorial_Java_MitoCode/06_Genericos_I_03.png)

Lista de estereotipos.

![06_Genericos_I_04](src/Tutorial_Java_MitoCode/06_Genericos_I_04.png)

---

## 7- Genéricos II
Los genéricos básicamente tienen dos propocitos:
- Proveer seguridad en Tipos.
- Evitar Casteos.

Seguridad en Tipos, ejemplo.  
Type safety es la proteccion que se le da a la lista para que solo reciba un tipo de elemento.

![07_Genericos_II_01](src/Tutorial_Java_MitoCode/07_Genericos_II_01.png)

En contraparte los arrays si brindan por defecto el Type safety

![07_Genericos_II_02](src/Tutorial_Java_MitoCode/07_Genericos_II_02.png)

Evita el casting

![07_Genericos_II_03](src/Tutorial_Java_MitoCode/07_Genericos_II_03.png)

Podemos tener *N* estereotipos en la clase y nosotros podemos optar por la definicion de cada una.

![07_Genericos_II_04](src/Tutorial_Java_MitoCode/07_Genericos_II_04.png)

Y en la clase principal llamamos a esa instancia e indicamos que tipo de datos son.

![07_Genericos_II_05](src/Tutorial_Java_MitoCode/07_Genericos_II_05.png)

También podemos crear una Lista de Clase que a la vez tenemos que indicarle que tipo son.

![07_Genericos_II_06](src/Tutorial_Java_MitoCode/07_Genericos_II_06.png)

---

## 8- Genéricos III Wildcards
Wildcards es un *Comodin*, se reprensenta con **?**, si lo llevamos al contexto de Java y en especial a los genéricos lo que nos va a permitir las Wildcards es poder
ejecutar nuestros genéricos sin indicar el tipo de dato, es decir este tipo de dato va a indicarse en tiempo de ejecución, o sea no lo vamos a mencionar directamente en el código.  
Para ejemplificar creamos una Clase Persona y Alumno con un atributo nombre, su constructor y métodos. De la misma manera otra Clase Profesor.

Y este vendria a ser el main creando una lista de Alumnos y mostrando los nombres.

![08_Genericos_III_Wildcards_01](src/Tutorial_Java_MitoCode/08_Genericos_III_Wildcards_01.png)

Ahora con Wildcards

**Lista con UpperBounded**  
Si solo ponemos el wildcar `<?>` es lo mismo decir `<? extends Object>` -> La palabra extends, en el contexto de genéricos, hace referencia a herencia e implementaciónes.  
Tambien es redundante esa expresion ya que estamos diciendo que el objeto pasado a la lista va a recibir cualquier objeto que herede de la clase Object, es decir todos.  
Para limitar un poco el tipo de dato a recibir podemos hacer que las clases Alumno y Profesor hereden de Persona y en consecuencia podriamos poner `<? extends Persona>`
Esto crea una Lista UpperBounded que reconoce a la misma clase o sus clases hijas.

![08_Genericos_III_Wildcards_02](src/Tutorial_Java_MitoCode/08_Genericos_III_Wildcards_02.png)

**Lista con LowerBounded**  
Esto indica que vamos a reconocer solamente a aquellas Clases que son mayores a la clase que le pasamos.  
En vez de extends usamos SUPER, entonces decimos que vamos a reconocer solo a las superclases de Alumno por ejemplo

![08_Genericos_III_Wildcards_03](src/Tutorial_Java_MitoCode/08_Genericos_III_Wildcards_03.png)

**Listar UnBounded**  
Es practicamente lo mismo pero sin indicar el tipo de dato.

![08_Genericos_III_Wildcards_04](src/Tutorial_Java_MitoCode/08_Genericos_III_Wildcards_04.png)

---

## 9- Capacidad inicial
Cuado construmos una nueva lista, en este caso, podemos pasarle al constructor un capacidad inicial, el tamaño que tendrá la lista.  
Imaginemos que tenemos una app que requiere mucho procesamiento en listas y si sabemos que un promedio de esas filas es de 5000 o 3000 quizas, pero tenemos un aproximado y si lo sabemos
es recomendable colocarlo en la lista que estamos creando para que exista un mejor rendimiento en la operación, con esto nos evitamos que el procesador este creando un nuevo espacio
a medida que se está creando una nueva lista.  
Recordemos que los arraylist, cuando incrementan, no es que se agrega un espacio al final, si no que simplemente se destruye la referencia anterior y se crea una nueva referencia
con un espacio mas, es decir se destruye y crea un nuevo objeto y así sucesivamente mientras se va iterando en un ciclo.  
La capacidad inicial por defecto de un arrayList es de 10, esta escrito en su contructor cuando no le pasamos ningún entero.

---

## 10- Ordenar Colecciones
En muchas ocaciones cuando uno lleva un curso de estructura de algoritmos y base de datos, mayormente al principio se enseña a poder trabajar con una estructura simple como los arreglos,
pero la principal desventaja de este tipo es que tenemos que indicar un tamaño fijo, y si queremos incrementarlo tendriamos que hacer un nuevo algoritmo que apunte a un nuevo arreglo y
tambien si queremos implementar una busqueda u ordenamiento, nos tenemos que apoyar en algortimos como el método de la burbuja, quickSort entro otros, que son validos cuando tenemos
situaciones de alto rendimiento.

En contra parte Java te proporciona una API, la API Colection, para que se pueda manejar listas de una manera más dinámica, aclaración siempre por rendimiento se considera trabajar con
arreglos de forma simple, pero si se necesita algo dinamico, práctico o inmediato que no requiera un algoritmo muy avanzado para poder aplicar esa lógica que se necesita podriamos optar
por el API Colection.

Ahora ordenaremos una lista que creamos y lo haremos con el método `sort()` que recibe como parámetro una lista, esta función no retorna nada pero nos ordena la lista de menos a mayor.

![10_Ordenar_colecciones_01](src/Tutorial_Java_MitoCode/10_Ordenar_colecciones_01.png)

Podemos invertir el orden original de la lista con `reverse()`

![10_Ordenar_colecciones_02](src/Tutorial_Java_MitoCode/10_Ordenar_colecciones_02.png)

Con una lista de Strings

![10_Ordenar_colecciones_03](src/Tutorial_Java_MitoCode/10_Ordenar_colecciones_03.png)

![10_Ordenar_colecciones_04](src/Tutorial_Java_MitoCode/10_Ordenar_colecciones_04.png)

Ordenamiento con un objeto tipo Persona, en este caso no tiene un criterio con el cual ordenar, entonces necesita del **comparator()**.

---

## 11- Comparator
Como la clase Persona tiene atributos varios y no se sabe que criterio debe tomar el ordenamiento es necesario indicar algunos criterios adicionales, entonces implementamos la interface
Comparator, el método sort nos pide una instancia de Comparator.  
Creamos una nueva clase llamada **NombreComparator**, al cual le implementamos Comparator que nos trae los métodos a sobreescribir, que solo es la función **compare()** al cual le pasamos
dos objetos como parámetro y nos devuelve un int.

![11_Comparator_01](src/Tutorial_Java_MitoCode/11_Comparator_01.png)

Implementamos el método para que compare los nombres en este caso.

![11_Comparator_02](src/Tutorial_Java_MitoCode/11_Comparator_02.png)

Creamos una nueva instancia de la Clase creada y recorremos la lista para imprimir su orden.

![11_Comparator_03](src/Tutorial_Java_MitoCode/11_Comparator_03.png)

Ahora podemos mejorar la performance para comparar Personas y es que en vez que sea un tipo Object sea un tipo Persona.

![11_Comparator_04](src/Tutorial_Java_MitoCode/11_Comparator_04.png)

Si queremos otros criterios para comparar tenemos que emplearlo en el método. En este caso lo creamos en la misma clase main para mostrar que se puede y comparamos las edades.

![11_Comparator_05](src/Tutorial_Java_MitoCode/11_Comparator_05.png)

---

## 12- Comparable
Mismo ejercicio para mismo resultado pero con otra interfaz.  
Primero que nada implementamos esta interfaz en la clase Persona y como hicimos antes podemos decirle que el tipo de dato que va a recibir es de tipo Persona,  
`public class Persona implements Comparable<Persona>`  
también implementamos el método obstracto correspondiente **compareTo()** que en este caso solo recibe un parámetro.  
Como primera medida lo que hace es restar las edades, depende del orden, el resultado es ascendente o descendente. Y tenemos el ejemplo también con los nombres.

![12_Comparable_01](src/Tutorial_Java_MitoCode/12_Comparable_01.png)

![12_Comparable_02](src/Tutorial_Java_MitoCode/12_Comparable_02.png)

---

## 13- HashSet
La interfaz **SET** implementa 3 métodos importantes para las listas **HashSet**, **TreeSet** y **LinkedHashSet**.
HashSet evita valores duplicados y el orden es aleatorio.

![13_HashSet_01](src/Tutorial_Java_MitoCode/13_HashSet_01.png)

Ahora si hacemos lo mismo pero con la Clase Persona, sí nos imprime valores duplicados.

![13_HashSet_02](src/Tutorial_Java_MitoCode/13_HashSet_02.png)

Y la razón es que cuando creamos una nueva instancia de objetos estamos apuntando a bloques de memoria distintos, por lo tanto cada vez que adicionamos a la lista, esta list Set está
interpretando que cada objeto pertenece a una instancia nueva por lo tanto ninguno es similar al otro.  
Entonces como hacemos la diferencia para que en el momento de agregar los objetos con atributos repetidos solamente me acepte aquellos que son únicos?  
Para ellos es importante sobreescribir 2 métodos para que esta función muestre los únicos.  
Estos son el **equals()** y el **hashCode()**, los generamos y vamos a seleccionar bajo que criterio vamos a hacer la comparación (Nombre).

![13_HashSet_03](src/Tutorial_Java_MitoCode/13_HashSet_03.png)

Y estos métodos lo que me va a permitir es comparar ambos objetos, en este caso de toda la lista, y asociar o buscar si el valor que hemos seleccionado relativamente es igual a otros
objetos. Entonces se basa en la comparación y se va a calcular o asociar un valor aleatorio, simplemente para tenerlo como un valor referencial.

![13_HashSet_04](src/Tutorial_Java_MitoCode/13_HashSet_04.png)

![13_HashSet_05](src/Tutorial_Java_MitoCode/13_HashSet_05.png)

Al agregar otro criterio, por ejemplo edad, vemos que lo toma como otro elemento en la lista.

![13_HashSet_06](src/Tutorial_Java_MitoCode/13_HashSet_06.png)

---

## 14- TreeSet
Otra implementación de la interfaz **Set**, el TreeSet me ofrece poder agregar elementos a la colección únicos, sin duplicados y también te los orden de forma ascendente.

![14_TreeSet_01](src/Tutorial_Java_MitoCode/14_TreeSet_01.png)

Ahora veremos que es lo que tenemos que hacer cuando querramos listar objetos.  
Cuando estemos en un proyecto desarrollado, tal vez se puedan traer directamente los elementos ordenados desde una base de datos con la consulta, o podriamos ordenarlas utilzando las
implementaciónes del API Java Collection.  
Para poner nuevamente los criterios para comparar, la Clase Persona tiene que implementar **Comparable** y el correspondiente **compareTo()**.

![14_TreeSet_02](src/Tutorial_Java_MitoCode/14_TreeSet_02.png)

![14_TreeSet_03](src/Tutorial_Java_MitoCode/14_TreeSet_03.png)

Aun implementando compareTo() seguimos teniendo elementos duplicados y para excluirlos es necesario también sobreescribir los métodos **equals()** y **hashCode()**.

![14_TreeSet_04](src/Tutorial_Java_MitoCode/14_TreeSet_04.png)

![14_TreeSet_05](src/Tutorial_Java_MitoCode/14_TreeSet_05.png)

![14_TreeSet_06](src/Tutorial_Java_MitoCode/14_TreeSet_06.png)

Ahora tengo 2 objetos excatamente iguales y no se muestra en el listado repetido.

![14_TreeSet_07](src/Tutorial_Java_MitoCode/14_TreeSet_07.png)

![14_TreeSet_08](src/Tutorial_Java_MitoCode/14_TreeSet_08.png)

---

## 15- LinkedHashSet
La implementación de LinkedHashSet se preocupa de que todos los elementos sean únicos y por el orden en el que los elementos se van agregando a la colección.

![15_LinkedHashSet_01](src/Tutorial_Java_MitoCode/15_LinkedHashSet_01.png)

Esta interfaz no necesita implementar el Comparable, por ende el compareTo() ya que se basa por orden de agregación, pero si tiene que sobreescribir el equals() y el hashCode() para
detectar elementos identicamente a otros.

![15_LinkedHashSet_02](src/Tutorial_Java_MitoCode/15_LinkedHashSet_02.png)

---

## 16- Map
Interfaz **Map**, también tiene 3 implementaciónes importantes, es muy parecido a la interfaz SET pese a no estar en la API Collection .

![16_Map_01](src/Tutorial_Java_MitoCode/16_Map_01.png)

**HashMap**  
No permite valores duplicados como llaves, el orden en el que se muestran los elementos no sigue un patron en particular.

![16_Map_02](src/Tutorial_Java_MitoCode/16_Map_02.png)

En la imagen anterior salio ordenado porque era de tipo integer pero si cambiamos a las KEY por Strings sale sin orden y si agregamos un valor que contenga una misma KEY, toma el ultimo
valor como referencia.

![16_Map_03](src/Tutorial_Java_MitoCode/16_Map_03.png)

**TreeMap**  
Como en SET, se preocupa por el orden ascendente de los elementos. No acepta valores nulos como Key

![16_Map_04](src/Tutorial_Java_MitoCode/16_Map_04.png)

**LinkedHashMap**  
Se preocupa por el orden en el que agregamos los elementos al mapa.

![16_Map_05](src/Tutorial_Java_MitoCode/16_Map_05.png)

Ahora si tenemos un objeto customizable, un objeto propio que hemos creado para nuestras apps, en este caso Persona va seguir el mismo enfoque que hicimos para la interfaz **SET**
en el que necesitamos implementar un Comparable para establecer los criterios del orden, y para el tema de duplicado sobreescribir el equals() y el hashCode().

Podemos sobreescribir el método toString() en la clase Persona para que en la lista nos salga algo mas legible las propiedades del objeto Persona. (Si no sale @ y un chocloHash)

![16_Map_06](src/Tutorial_Java_MitoCode/16_Map_06.png)

***LinkedHashMap*** con objeto, con este método no hay necesidad de implementar el Comparable y como compara los demás atributos de Persona salen todos los elementos.

![16_Map_07](src/Tutorial_Java_MitoCode/16_Map_07.png)

Con el ***TreeMap*** vemos que nos sale un objeto ya que este sí los compara solamente por edad.

![16_Map_08](src/Tutorial_Java_MitoCode/16_Map_08.png)

Una vez corregido lo podemos ver con su orden ascendente.

![16_Map_09](src/Tutorial_Java_MitoCode/16_Map_09.png)

Y en el ***HashMap*** nos salen todos los elementos ya que el criterio que utiliza para comparar son el nombre edad y id, entonces lo toma

![16_Map_10](src/Tutorial_Java_MitoCode/16_Map_10.png)

Si modificamos y tenemos 2 exactamente iguales ya no salen.

![16_Map_11](src/Tutorial_Java_MitoCode/16_Map_11.png)

Otra forma de iterar un Map es con el foreach y Entry.

![16_Map_12](src/Tutorial_Java_MitoCode/16_Map_12.png)

---

## 17- Stack
Clase Stack, vamos a implementar el algoritmo LIFO (Last In/ First Out), el último en entrar es el primero en salir. Puede guardar elementos repetidos.  
Algunos métodos de Stack  
`pila.push()` se agrega un elemento a la pila.  
`pila.pop()` remueve un elemento de la pila, devuelve un entero.  
`Thread.sleep(1000)` Duerme al hilo por 1 segundo para que no corra tan rápido el for.  
`pila.peek()` Me permite saber el elemento que esta a tope sin eliminarlo.  
`pila.search()` Busca el elemento en la pila, en este caso "4-Jaime" es el primer elemento, por eso el 1, si ponemos "1-Mitocode" Sale 4.  

![17_Stack_01](src/Tutorial_Java_MitoCode/17_Stack_01.png)

Ahora con un objeto

![17_Stack_02](src/Tutorial_Java_MitoCode/17_Stack_02.png)

---

## 18- Queue
Colas, en contra parte al anterior nos toca ver FIFO (First In/ First Out), en este caso trabajaremos con **PriorityQueue** quien trabaja con esta prioridad.

![18_Queue_01](src/Tutorial_Java_MitoCode/18_Queue_01.png)

Algunos métodos:  
`cola.offer()` Agrega un elemento a cola.  
`cola.poll()` Elimina un elemento de cola, devuelve un String.  
No se puede eliminar un elemento recorriendo un for, por lo cual utilizamos un while().  
`cola.peek()` Se ve con que elemento estamos trabajando.  

![18_Queue_02](src/Tutorial_Java_MitoCode/18_Queue_02.png)

Cuando queremos trabajar con un objeto debemos indicar la prioridad que debemos considerar ya que no esta definido de por si, en este caso se prioriza la edad implementando
Comparable, compareTo(), como en los anteriores ejemplos.

![18_Queue_03](src/Tutorial_Java_MitoCode/18_Queue_03.png)

---

## 19- Deque
Interfaz Deque con la implementación arrayDeque.  
Es una mezcla entre Stack y Queue. Podemos agregar y remover elementos al inicio y al final de la colección.  
Estos métodos son. addFirst(), addLast(), removeFirst() y removeLast(). Acá también se muestran los métodos para remover de Stack y Queue.

![19_Deque_01](src/Tutorial_Java_MitoCode/19_Deque_01.png)

![19_Deque_02](src/Tutorial_Java_MitoCode/19_Deque_02.png)

---

## 20- StringBuilder StringBuffer
Son dos clases para trabajar con Strings, como ya vimos, trabajar con el concatenador **+** tiene un impacto mayor en el rendimiento de nuestros procesos.  
No conviene ya que lo que hacemos es crear un StringBuilder, creando un String y llamando al método toString().  
Acá se explicara las diferencia de estas dos clases y cuando combiene usarlas.

Instanciamos un StringBuilder y vemos que tiene unas peculiaridades, por defecto tiene una capacidad inicial de 16 chars, pero podemos indicarle la capacidad nosotros.

![20_StringBuilder_StringBuffer_01](src/Tutorial_Java_MitoCode/20_StringBuilder_StringBuffer_01.png)

Igual como es mutable no es necesario indicarla, pero al hacerlo tiene mejor rendimiento y se recomienda que sea múltiplo de 4.

![20_StringBuilder_StringBuffer_02](src/Tutorial_Java_MitoCode/20_StringBuilder_StringBuffer_02.png)

![20_StringBuilder_StringBuffer_03](src/Tutorial_Java_MitoCode/20_StringBuilder_StringBuffer_03.png)

Si escribimos un String dentro del constructor se suma a esos 16, podemos setearle el tamaño también, orden inverso del contenido.

![20_StringBuilder_StringBuffer_04](src/Tutorial_Java_MitoCode/20_StringBuilder_StringBuffer_04.png)

Si cambiamos el StringBuilder por un StringBuffer tenemos exactamente los mismos métodos ya que extienden de la misma clase, AbstractStringBuilder, y entonces cuales son las diferencias?

Es más rápido usar un StringBuilder que un StringBuffer debido a la sincronización cuando manejamos hilos, StringBuilder por defecto no tiene métodos sincronos, es decir no hace una
seguridad cuando trabajamos con hilos, no es threadSave. En cambio Buffer si lo es, y nos damos cuenta ya que algunos de sus métodos presentan la palabra ***synchronized***. Quiere
decir que me dá la seguridad de que ese proceso va a ser ejecutado por un único hilo al mismo tiempo, por lo tanto estoy protegiendo los recursos que puedan compartirse en una app.  
Mientras que StringBuilder presenta los mismos métodos pero sin esta palabra, es decir varios hilos podrian ejecutar los métodos y cambiar los valores entre uno y otro.  

Cuando la integridad del mensaje es importante conviene utilizar StringBuffer porque tiene métodos sincronos, es decir va a haber una proteccion frente un ambiente de hilos. Sin embargo
si no importa eso podemos usar un StringBuffer. StringBuilder es mucho más rapido que un StringBuffer.

---

## 21- Split
Pertenece a la Clase String, y básicamente sirve para poder extraer elementos de una cadena de texto para poder asignarlos a un arreglo y puede utilizar un **Regex** (Expresión regular)

![21_Split_01](src/platziblog_tabla_usuarios_1.png21_Split_01.png)

En el caso que esten separados por el simbolo pipe (|), se hace de la siguiente manera:

![21_Split_02](src/Tutorial_Java_MitoCode/21_Split_02.png)

![21_Split_03](src/Tutorial_Java_MitoCode/21_Split_03.png)

También puedo indicarle, como segundo argumento, el limite, en cuantas partes me divide a la cadena.  

![21_Split_04](src/Tutorial_Java_MitoCode/21_Split_04.png)

---

## 22- Pattern Regex
















---

# Tutorial Java 8
## 1- Paradigma Funcional
El paradigma funcional es un subtipo del paradigma de programación Declarativa, basada en el uso de funciones matemáticas en contraste con la programación Imperativa.

Es decir, el principal fin de la programación Declarativa es tener una sintaxis de decirle al programa **que** es lo que necesitamos, sin embargo en contraste a la programación
Imperativa es decirle al lenguaje de programación **como** lo necesitamos.

Por ejemplo, para un lenguaje de programación Declarativa, nosotros le indicamos todas las sentencias a un determinado problema, por ejemplo el lenguaje **SQL**, si quiero todos los
usuarios que empiecen con la letra 'A', puedo decirlo asi:
~~~
SELECT * FROM users WHERE nombre like 'A%';
~~~
Decimos que es lo que queremos pero no como traerlo internamente al objetivo.

En contraparte, la Imperativa, si quiero lograr el mismo resultado, tendria que darle instrucción paso a paso para poder obtener el resultado.  
Por ejemplo, si me pidieran el promedio tendria que colocar un número, otro, otro y otro, sumarlos todos y dividirlos entre la cantidad de números.  
Es Imperativa porque le estoy indicando todos los pasos para lograr el objetivo.

![01_paradigma_funcional_01](src/Tutorial_Java_MitoCode/01_paradigma_funcional_01.png)

Entonces, volviendo al paradigma funcional, nos permite tener una semantica más limpia, acá entran las lambdas, y también se apoya en la recursión, porque básicamente para poder
abstraer muchas funcionalidades es necesario apoyarse en la reutilización de los mismos métodos.

Lenguajes de programación Declarativa (QUE) e Imperativa (COMO)  
![01_paradigma_funcional_02](src/Tutorial_Java_MitoCode/01_paradigma_funcional_02.png)

Java 8 se basa en un fuerte simbolo conocido como ***Lambdas***  
Las Lambdas basicamente son funciones anónimas, muy escenciales para entender la programación declarativa y presente la siguiente estructura `parámetros =>(operador) expresión`

![01_paradigma_funcional_03](src/Tutorial_Java_MitoCode/01_paradigma_funcional_03.png)

---

## 2- Lambda
Una expresión Lambda es un método anónimo que no necesita de un identificador para ser invocado.
