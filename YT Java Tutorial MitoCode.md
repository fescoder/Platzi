![MitoCode_logo](src/Tutorial_Java_MitoCode/MitoCode_logo.png)
# Java Tutorial MitoCode
[Github MitoCode](https://github.com/mitocode21)

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
    - [01- Introducción](#01--introducción)
    - [02- Proyecto Maven](#02--proyecto-maven)
    - [03- Instancia y Static](#03--instancia-y-static)
    - [04- Instanceof](#04--instanceof)
    - [05- Singleton](#05--singleton)
    - [06- Genéricos I](#06--genéricos-i)
    - [07- Genéricos II](#07--genéricos-ii)
    - [08- Genéricos III](#08--genéricos-iii-wildcards)
    - [09- Capacidad inicial](#09--capacidad-inicial)
    - [10- Ordenar colecciones](#10--ordenar-colecciones)
    - [11- Comparator](#11--comparator)
    - [12- Comparable](#12--comparable)
    - [13- HashSet](#13--hashset)
    - [14- TreeSet](#14--treeset)
    - [15- LinkedHashSet](#15--linkedhashset)
    - [16- Map](#16--map)
    - [17- Stack](#17--stack)
    - [18- Queue](#18--queue)
    - [19- Deque](#19--deque)
    - [20- StringBuilder StringBuffer](#20--stringbuilder-stringbuffer)
    - [21- Split](#21--split)
    - [22- Pattern regex](#22--pattern-regex)
    - [23- Matcher regex](#23--matcher-regex)
    - [24- Catch lineal](#24--catch-lineal)
    - [25- Inyección SQL](#25--inyección-sql)
    - [26- ExecuteBatch preparedStatement](#26--executebatch-preparedstatement)
    - [27- CallableStatement](#27--callablestatement)
    - [28- File (Constructores)](#28--file-constructores)
    - [29- FilInputStream](#29--fileinputstream)
    - [30- BufferedInputStream](#30--bufferedinputstream)
    - [31- FileInputStream (Copiar archivos)](#31--fileinputstream-copiar-archivos)
    - [32- BufferedOutputStream](#32--bufferedoutputstream)
    - [33- Readers y Writers](#33--readers-y-writers)
    - [34- NIO2 Path y files](#34--nio2-path-y-files)
    - [35- NIO2 Read y write](#35--nio2-read-y-write)
    - [36- NIO2 Channel y buffer](#36--nio2-channel-y-buffer)
    - [37- NIO2 WatchService](#37--nio2-watchservise)
    - [38- Thread y runnable](#38--thread-y-runnable)
    - [39- Sleep y join](#39--sleep-y-join)
    - [40- Synchronized](#40--synchronized)
    - [41- Callable Future y ExcecutorService](#41--callable-future-y-excecutorservise)
    - [42- CompletionService](#42--completionservice)
- [Tutorial Java 8](#tutorial-java-8)
    - [01- Paradigma Funcional](#01--paradigma-funcional)
    - [02- Lambda](#02--lambda)
    - [03- Sintaxis lambda](#03--sintaxis-lambda)
    - [04- Ámbitos lambda (Lambda scopes)](#04--ámbitos-lambda-lambda-scopes)
    - [05- Default methods](#05--default-methods-métodos-por-defecto)
    - [06- Interfaces funcionales](#06--interfaces-funcionales)
    - [07- Referencias de métodos](#07--referencias-de-métodos-method-references)
    - [08- Foreach RemoveIf Sort](#08--foreach-removeif-sort)
    - [09- Stream](#09--stream)
    - [10- Optional](#10--optional)
    - [11- Stream paralelo](#11--stream-paralelo)
    - [12- Map](#12--map)
    - [13- Anotaciones de repetición](#13--anotaciónes-de-repetición)
    - [14- Date API](#14--date-api)
    - [15- Funciones de alto orden](#15--funciones-de-alto-orden)
    - [16- RxJava](#16--rxjava)
    - [17- Nashorm](#17--nashorm)

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
[Videos](https://www.youtube.com/watch?v=jq9DyzOxFzs&list=PLvimn1Ins-43qPXR3gBcxwe7tydxZtsON&index=38)

## 01- Introducción
En esta primer clase muestra como funciona el mandarle parámetros al método main e imprime los mismos.

![01_Introduccion_01](src/Tutorial_Java_MitoCode/01_Introduccion_01.png)

---

## 02- Proyecto Maven
[Construcción con Maven](https://www.youtube.com/watch?v=3RunOD1VBco&list=PLvimn1Ins-43qPXR3gBcxwe7tydxZtsON&index=2)

---

## 03- Instancia y Static
Un método de instancia no puede ser sobreescrito por un método estatico ni viceversa.

![03_Instancia_Static_01](src/Tutorial_Java_MitoCode/03_Instancia_Static_01.png)

La clase hija siempre se ejecuta en vez de la clase padre

![03_Instancia_Static_02](src/Tutorial_Java_MitoCode/03_Instancia_Static_02.png)

---

## 04- InstanceOf
Este operador nos permite conocer de que tipo o instancia es un determiando objeto, saber de que clase es.  
Sabiendo que Alumno hereda de Persona también funciona.

![04_InstanceOf_01](src/Tutorial_Java_MitoCode/04_InstanceOf_01.png)

Ejemplo práctico con una canasta de frutas.

![04_InstanceOf_02](src/Tutorial_Java_MitoCode/04_InstanceOf_02.png)

![04_InstanceOf_03](src/Tutorial_Java_MitoCode/04_InstanceOf_03.png)

---

## 05- Singleton
Es un patron de diseño que nos permite tener una unica instancia de una clase particular.

[Patrón Singleton](https://www.youtube.com/watch?v=qiFeiYLzIH8&list=PLvimn1Ins-43qPXR3gBcxwe7tydxZtsON&index=5)

---

## 06- Genéricos I
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

## 07- Genéricos II
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

## 08- Genéricos III Wildcards
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

## 09- Capacidad inicial
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

![21_Split_01](src/Tutorial_Java_MitoCode/21_Split_01.png)

En el caso que esten separados por el simbolo pipe (|), se hace de la siguiente manera:

![21_Split_02](src/Tutorial_Java_MitoCode/21_Split_02.png)

![21_Split_03](src/Tutorial_Java_MitoCode/21_Split_03.png)

También puedo indicarle, como segundo argumento, el limite, en cuantas partes me divide a la cadena.

![21_Split_04](src/Tutorial_Java_MitoCode/21_Split_04.png)

---

## 22- Pattern Regex
Definición wikipedia

![22_Pattern_regex_01](src/Tutorial_Java_MitoCode/22_Pattern_regex_01.png)

Da a entender que una expresión regular es una cadena de texto que tiene un formato en particular, que respeta algunas caracteristicas, que nos va a permitir facilitar la busqueda
en otras cadenas de textos de acuerdo a ese patron que hemos definido anteriormente.

Hay dos clases importantes de expresiones regualres en Java una es **Pattern** y la otra **Matcher**.

Cuando instanciamos Pattern no lo hace como siempre, con la palabra *new* ya que .compile() es un método de la clase (Static).  
Acá también nos apoyamos enla Clase Matchers, muy por arriba, para crear la secuencia que evaluaremos.  
`m.matches()` Lo usamos para ver si hay coincidencia entre el patrón que indicamos y el matcher, devuelve un booleano.  
`.compile(".")` El punto básicamente indica que se evalua cualquier caracter en particular, si pongo mas letras en el matcher sale false.

![22_Pattern_regex_02](src/Tutorial_Java_MitoCode/22_Pattern_regex_02.png)

![22_Pattern_regex_03](src/Tutorial_Java_MitoCode/22_Pattern_regex_03.png)

Más ejemplos de uso.

![22_Pattern_regex_04](src/Tutorial_Java_MitoCode/22_Pattern_regex_04.png)

![22_Pattern_regex_05](src/Tutorial_Java_MitoCode/22_Pattern_regex_05.png)

![22_Pattern_regex_06](src/Tutorial_Java_MitoCode/22_Pattern_regex_06.png)

Hay Regexs preparadas para que copiemos y peguemos en nuestro patron para que se evaluen sin tener que construirlos desde cero. Claro que si hay una necesidad en particular habria
que analizar simplemente como se construyen estas.

![22_Pattern_regex_07](src/Tutorial_Java_MitoCode/22_Pattern_regex_07.png)

Por ejemplo, si yo evaluo `[abc]` me va a evaluar que mi texto contenga una de estas letras.

![22_Pattern_regex_08](src/Tutorial_Java_MitoCode/22_Pattern_regex_08.png)

Con **^** va a ser true siempre que lo indicado NO este en nuestro texto, es un negador.

![22_Pattern_regex_09](src/Tutorial_Java_MitoCode/22_Pattern_regex_09.png)

![22_Pattern_regex_10](src/Tutorial_Java_MitoCode/22_Pattern_regex_10.png)

Diferencias usando split() con Pattern y directamente en la cadena.  
Siempre es aconsejable usar Pattern cuando tenemos un procesamiento masivo de una cadena de texto, especialmente cuando utilizamos los métodos de la clase String que necesitan de una
expresión regular, como split(), matches(), replaceAll().

![22_Pattern_regex_12](src/Tutorial_Java_MitoCode/22_Pattern_regex_12.png)

Con expresión simple

![22_Pattern_regex_11](src/Tutorial_Java_MitoCode/22_Pattern_regex_11.png)

Cuando tiene un patron mas complejo se nota cuanto conviene usar Pattern.

![22_Pattern_regex_13](src/Tutorial_Java_MitoCode/22_Pattern_regex_13.png)

---

## 23- Matcher Regex
Otra anotación de la clase Pattern es que el `.compile()` puede recibir 2 parámetros, la primera el string a buscar y el segundo es un flag, en este caso que la busqueda no es sensible
a mayusculas o minusculas. Con `*.` y `.*` digo que no importa lo que haya adelante o atras de *mitocode*.

![23_Matcher_regex_01](src/Tutorial_Java_MitoCode/23_Matcher_regex_01.png)

Y si quisieramos resumir a una linea de código podriamos hacer lo siguiente

![23_Matcher_regex_02](src/Tutorial_Java_MitoCode/23_Matcher_regex_02.png)

En la Clase Matcher vamos a prender el método ***.lookingAt()***, básicamente busca si la cadena de texto inicia con la que le pasamos, pero también podemos indicarle con Regex si hay algo
más al inicio.

![23_Matcher_regex_03](src/Tutorial_Java_MitoCode/23_Matcher_regex_03.png)

Si le quitamos los .* vemos que matches() busca si *suscribete* es toda la cadena mientras que lookingAt() solo si comienza con ella.

![23_Matcher_regex_04](src/Tutorial_Java_MitoCode/23_Matcher_regex_04.png)

`.find()` Va a ejecutarse siempre y cuando se encuentre una coincidencia o más.  
Para saber indicies o posicion en la que se encuentra la/s coincidencias tenemos `m.start()` y `m.end()`

![23_Matcher_regex_05](src/Tutorial_Java_MitoCode/23_Matcher_regex_05.png)

---

## 24- Catch lineal
Si queremos indicar que vamos a capturar diferentes tipos de exceptions, en vez de hacer varios catches podemos expresarlo en uno agregando el operador pipe **|**

![24_Catch_lineal_01](src/Tutorial_Java_MitoCode/24_Catch_lineal_01.png)

---

## 25- Inyección SQL
Definición Wikipedia

![25_Inyeccion_SQL_01](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_01.png)

Clase Statement y las consideraciónes a tener en cuenta cuando nos conectamos a BD y hacemos consultas o insercciones, para evitar vulnerabilidades que sean atacadas.  
La inyección sql es una vulnerabilidad que es común encontrar en aplicativos que utilizan Statements para interactuar con la base de datos, es decir se vale de un hueco en el sistema,
que el usuario va a poder ingresar datos de manera manual o automática (Scripts), y estos datos son enviados a nuestra BD pudiendo ejecutar operaciónes que nosotros no deseamos.  
Hasta ahora usamos Statements para conectarnos a la BD, es rudimentario hacer este tipo de conexiones para pedir o registrar datos.  
Básicamente es la infiltración de código que nosotros podemos tener en nuestra aplicación y veremos aqui como se infiltra.  
Principalmente por los atributos a llenar, en este caso nombre y pass.

Este es el codigo con la conexión Statement de ejemplo

![25_Inyeccion_SQL_02](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_02.png)

Y al ejecutar la consulta vemos que es exitosa.

![25_Inyeccion_SQL_03](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_03.png)

Ahora podemos romperlo con la inyección SQL, aquí modificaremos el pass para escribir código e indicaremos **OR y algo que sea verdad**.

![25_Inyeccion_SQL_04](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_04.png)

![25_Inyeccion_SQL_05](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_05.png)

Vemos que la verificación me marca que es exitosa a pesar de que ese usuario no existe, entonces se burla la consulta, es decir nuestro mecanismo de verificación, y nos permite seguir
avanzando en el sistema.

![25_Inyeccion_SQL_06](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_06.png)

![25_Inyeccion_SQL_07](src/Tutorial_Java_MitoCode/25_Inyeccion_SQL_07.png)

En conclusión no es recomendable usar conexiones rudimentarias con Statement y armar toda la app simplemente usando la concatenación de los valores de acuerdo a los parámetros que uno
va indicando, para ellos existen otros mecanismos un poco mas protectores conocidos como los **PreparedStatement** o los **CallableStatement** que nos proporciona el API jdbc de Java.  
Ahora si nos queremos apoyar en mecanismos más avanzados, podemos utilizar frameworks que engloben la persistencia de datos como **Hibernate** o trabajar en base a lo que nos proporciona
el estandar en Java como JPA.  
El consejo es evitar el uso de Statement para pedir datos al usuario y asi protegernos de esa vulnerabilidad.

---

## 26- ExecuteBatch PreparedStatement
## 27- CallableStatement
## 28- File (Constructores)
## 29- FileInputStream
## 30- BufferedInputStream
## 31- FileInputStream (Copiar archivos)
## 32- BufferedOutputStream
## 33- Readers y Writers
## 34- NIO2 Path y Files
## 35- NIO2 Read y Write
## 36- NIO2 Channel y Buffer
## 37- NIO2 WatchServise
## 38- Thread y Runnable
## 39- Sleep y Join
## 40- Synchronized
## 41- Callable, Future y ExcecutorServise
## 42- CompletionService

---

# Tutorial Java 8
[Videos](https://www.youtube.com/watch?v=4WEOzOndA68&list=PLvimn1Ins-419yVe5iPfiXrg4mZJl5kLS)

## 01- Paradigma Funcional
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
Las Lambdas basicamente son funciones anónimas, muy escenciales para entender la programación declarativa y presente la siguiente estructura `parámetros =>(operador) expresión`.  
Una función anónima es una definición de función que no está vinculada a un identificador, no tiene ningun nombre asociado.  
Una clase anónima se crea al vuelo a la hora de instanciar un objeto que necesitamos y no encaja exactamente con ningún tipo.  
Se definie llamando al constructor de un tipo conocido y añadíendole un cuerpo con el comportamiento personalizado.  
Es una clase interna sin nombre y para la que solo se crea un objeto. Una clase interna anónima puede ser útil cuando se crea una instancia de un objeto con ciertos "extras" como los
métodos de sobrecarga de una clase o interfaz, sin tener que subclasificar una clase.

![01_paradigma_funcional_03](src/Tutorial_Java_MitoCode/01_paradigma_funcional_03.png)

---

## 02- Lambda
Una expresión Lambda es un método anónimo que no necesita de un identificador para ser invocado.

Para ejemplificar ordenamos una pequeña lista de la siguiente manera  

![02_Lambda_01](src/Tutorial_Java_MitoCode/02_Lambda_01.png)

Pero estamos empleando varias lineas de código para lograrlo, con un enfoque imperativo, indicando linea por linea que es lo que necesitamos.  
Entonces en JDK 1.8 existe este concepto de Lambdas, que cambia de paradigma, recordemos que tenemos que cambiar un poco la forma de pensar y hay que centrarse básicamente en que es lo
que necesito y no tanto en como lo necesito. Entonces para apoyarnos en Lambdas vamos a hacer lo siguiente:

![02_Lambda_02](src/Tutorial_Java_MitoCode/02_Lambda_02.png)

Entonces invocando al método .sort() de la Clase Collections, le pasamos la lista y nuestro Lambda, que se compone de los parámetros, el operador y la expresión a evaluar, en este caso que
el parámetro 1 se compare con el parámetro 2, con el método compareTo(), que nos devuelve en orden alfabetico y se ordena la lista.

Otro ejemplo, ahora con una interfaz, calculando un promedio:

![02_Lambda_06](src/Tutorial_Java_MitoCode/02_Lambda_06.png)

Forma imperativa:  
Recordemos que no podemos instanciar una interfaz, pero puedo implementarla, lo que estamos haciendo es creando una clase anónima para implementar los métodos de esa interfaz.

![02_Lambda_03](src/Tutorial_Java_MitoCode/02_Lambda_03.png)

Esto mismo puedo hacerlo con Lambda, todo aquel concepto que pueda hacer una implementación a traves de una Clase anónima, puede usar Lambda.  
Entonces debo escribir una clase anónima para implementarla con Lambda

![02_Lambda_04](src/Tutorial_Java_MitoCode/02_Lambda_04.png)

Otra sintaxis sin declarar el Tipo de dato, también funcióna

![02_Lambda_05](src/Tutorial_Java_MitoCode/02_Lambda_05.png)

Vemos como nos ahorramos muchas líneas de código.

---

## 03- Sintaxis Lambda
Hay muchas formas de escribir sintaxis Lambda, vimos una pero ahora analizaremos otras expresiones que Java permite.  
Seguimos usando la interfaz de la clase pasada y con ésta veremos sus variaciones posibles.  

![03_Sintaxis_Lambda_01](src/Tutorial_Java_MitoCode/03_Sintaxis_Lambda_01.png)

*Una idea de lectura propia, creo una variable de la interfaz Operacion, en el cual le asigno diciendo, voy a pasar 2 variables (X e Y) y lo que vas a hacer (->) es sumarlos y dividirlo*
*en dos. Y la forma de ejecutar esta función sin nombre es usando la instancia operacion y .calcularPromedio() que es quien recibe estas 2 variables y hace lo que le expresamos. Es decir*
*definimos lo que va a hacer calcularPromedio() en Lambda y despues ejecutamos.(Borrador)*

Otra forma de escribir es encerrando entre llaves ({}) el lado donde vamos a evaluar el método.

![03_Sintaxis_Lambda_02](src/Tutorial_Java_MitoCode/03_Sintaxis_Lambda_02.png)

Ahora nos preguntamos que sentido tiene colocar las llaves para una linea de código?.  
Lo mostraremos con un ejemplo y vemos que es posible tener una sintaxis Lambda de esta manera, cuando necesito definir más de una linea, es mejor abrir y cerrar llaves y definir el
código en ese bloque, pero si nos ponemos a pensar que el fin de una Lambda es tener un código más legible, entonces no es recomendable hacerlo de esta forma. Solo lo vemos con fines
demostrativos.

![03_Sintaxis_Lambda_03](src/Tutorial_Java_MitoCode/03_Sintaxis_Lambda_03.png)

También podemos pasarle los parámetros sin tener que definir el tipo de dato, Java implicitamente va a suponer que tipo es el parámetro dado y trabajará de manera normal.

![03_Sintaxis_Lambda_04](src/Tutorial_Java_MitoCode/03_Sintaxis_Lambda_04.png)

Ahora, que pasaria si nosotros no deseamos tener parámetros? Simplemente lo indicamos con parentesis vacios (()) y a la mano derecha lo que queremos hacer, tener en cuenta que si el
método pide argumentos para ejecutarse, sí vamos a tener que pasarle algo, si no lo requiere, solo vacio. En este caso la salida es **2.0**.

![03_Sintaxis_Lambda_05](src/Tutorial_Java_MitoCode/03_Sintaxis_Lambda_05.png)

Colocamos llaves en un Lambda sin parámetros y podemos tener más valores. Salida es **5.0** ya que el método devuelve un double.

![03_Sintaxis_Lambda_06](src/Tutorial_Java_MitoCode/03_Sintaxis_Lambda_06.png)

La recomendación es tener las Lambdas lo más legibles posibles y acordarse que la definición de tipo de los parámetros es opcional.

---

## 04- Ámbitos Lambda (Lambda Scopes)
Vamos a ver como se comportan las expresiones Lambdas con variables locales, globales, estaticas y no estaticas.  
Scope hace referencia al ámbito o alcance, en este caso de las variables en conjunto con la Lambda.  
Como una interfaz no puede instanciarse es necesario implementar los métodos, en este caso *calcular()*, aquí haremos que la variable ya definida **n3** se le asigne la suma de **n1**
y **n2**.

**Variable local**

![04_Ambitos_Lambda_01](src/Tutorial_Java_MitoCode/04_Ambitos_Lambda_01.png)

Pero vemos que esta clase anónima, que es la implementación de una interfaz, nos marca un error ya que la variable **n3** debe tener un scope final, porque cuando trabajamos
con una clase anónima y necesitamos hacer referencia a una variable local, es necesario que esta varibale local tenga final en su declaración.

![04_Ambitos_Lambda_02](src/Tutorial_Java_MitoCode/04_Ambitos_Lambda_02.png)

Al hacer esto claramente no podemos cambiar el valor de **n3** por ende tenemos que cambiar el código de nuestra función.

![04_Ambitos_Lambda_03](src/Tutorial_Java_MitoCode/04_Ambitos_Lambda_03.png)

Pero estamos en un contexto de lambdas asique lo cambiaremos a la siguiente manera

![04_Ambitos_Lambda_04](src/Tutorial_Java_MitoCode/04_Ambitos_Lambda_04.png)

La variable local se comporta igual tanto en clases anónimas como la Lambdas, la variable debe ser final y no se le puede asignar un valor, entonces el concepto de una variable local
en un scope lamda permanece tan igual para una clase anónima como una lambda. Por lo tanto yo puedo usar las variables pero no alterar su valor.

En conclusión, cuando estamos en una expresión Lambda y usamos una veriable local es opcional colocar el identificador *final*, si no lo colocas, se va a comportar como uno y tener en
cuenta que podemos usar el valor pero no asignarle uno nuevo.

**Variable static**  
Acá vamos a probar como se comportan cuando definimos variables globales static y no static.

![04_Ambitos_Lambda_05](src/Tutorial_Java_MitoCode/04_Ambitos_Lambda_05.png)

Cuando estoy en una expresión Lambda y quiero hacer referencia a un atributo de clase, uno estatico o uno no estatico, podemos tener la capacidad de lectura y escritura de esos atributos
en nuestra expresión. Es decir que tienen el mismo comportamiento que en un objeto anónimo que se instancia a traves de una interfaz donde tenemos que implementar los métodos.  
Y el comportamiento que podriamos acceder es el mismo tanto en estos objetos anónimos como en nuestras expresiones Lambdas.  
Recordar que cuando estamos en ámbito local es importante tener en consideración el atributo final cuando estamos haciendo un objeto anónimo era opcional pero el comportamiento es como un
final.  
Ejemplo:  
Atributo 1 Static, de clase - atributo 2 global y no static

![04_Ambitos_Lambda_06](src/Tutorial_Java_MitoCode/04_Ambitos_Lambda_06.png)

---

## 05- Default Methods (Métodos por defecto)
Es una funcionalidad para con las interfaces. Básicamente es escribir la funcionalidad del método en la interfaz, ya definirla, para cuando las clases implementen esa interfaz tengan
estos métodos en común funcionamiento.  
Un método default es un método que está implementado en una interfaz para que cualquier clase que implemente esta interfaz ya tenga acceso al método definido.  
Y se hace de la siguiente manera:  
Interfaz

![05_Default_methods_01](src/Tutorial_Java_MitoCode/05_Default_methods_01.png)

Main

![05_Default_methods_02](src/Tutorial_Java_MitoCode/05_Default_methods_02.png)

El IDE muestra con una 'D' el método a implementar.  
En que momentos nos serian utiles estos métodos? En un ambiente real de producción a veces tenemos que implementar nuevas funcionalidades y en muchas ocaciones se trabaja orientado
a interfaces para tener un código desacoplado, entonces imaginemos que se nos pida como requerimiento todas las clases que implementen una determinada interfaz, necesiten tener un
comportamiento por defecto. Entonces tenemos dos opciones:  
La primera es crear de forma tradicional, simplemente haciendo mencion al método y sobreescribiendo en cada clase.  
O la otra que es utilizar un método por defecto, implementar la funcionalidad y que todas las clases que implementen esa interfaz tengan acceso al método con toda la lógica implementada.

Ahora vemos que pasaria si tengo otra interfaz **PersonaB** con el mismo método. Java internamente no va a saber cual método voy a implementar porque ambos tienen el mismo nombre,
entonces para poder invocar a un determinado proceso de una interfaz. Entonces lo que hacemos es apoyarnos en el IDE y sobreescribir uno de los métodos y se nos aparece de la siguiente
manera:

![05_Default_methods_03](src/Tutorial_Java_MitoCode/05_Default_methods_03.png)

En la sobreescritura vemos como al invocar al método se hace mención a la interfaz de la que proviene, en este caso **PersonaA**. Si cambio A por B, se ejecutaria el otro método.

Ahora que pasaria si necesariamente tengo que implementar esta interfaz pero hay una clase que como exepción necesita sobreescribir su propia lógica.  
Podriamos directamente escribir el código dentro del método sobreescrito.

![05_Default_methods_04](src/Tutorial_Java_MitoCode/05_Default_methods_04.png)

---

## 06- Interfaces funcionales
Es un concepto que vimos implicitamente, ahora lo veremos mas formal.

![06_Interfaces_funcionales_01](src/Tutorial_Java_MitoCode/06_Interfaces_funcionales_01.png)

Defino un método operar, que recibe dos parámetros (X e Y), invocamos a la interfaz **Operacion** (que tiene la declaracion de *calcular()*, que recibe dos parámetros también) y le
pasamos una expresión Lambda. Por último utilizo el método *calcular()* definido en la interfaz conjuntamente con la expresión Lambda y le paso los parámetros X e Y. Y en el main
instanciamos un objeto de la clase y ejecuto el método pasandole 2 y 3 e imprimimos la respuesta.

Como nos ayuda una interfaz funcional al momento de definir expresiones lambda? Principalmente no se puede tener dos métodos en la interfaz. Si lo hacemos nos marca un error
que dice que la expresión no apunta a una interfaz funcional.

![06_Interfaces_funcionales_02](src/Tutorial_Java_MitoCode/06_Interfaces_funcionales_02.png)

![06_Interfaces_funcionales_03](src/Tutorial_Java_MitoCode/06_Interfaces_funcionales_03.png)

Entonces por definicion diremos que una interfaz funcional es aquella que solo define una unica operación, un método.  
Pero en Java 1.8 lo quiso formalizar de una maner práctica y es por eso que usaremos la siguiente anotación `@FunctionalInterface`, básicamente lo que dice es que la interfaz que
está debajo de la anotación debe ser una interfaz funcional y si quiero agregar un nuevo método me tira un error.

![06_Interfaces_funcionales_04](src/Tutorial_Java_MitoCode/06_Interfaces_funcionales_04.png)

Un ejemplo de una interfaz funcional es **Comparable** que usamos *compareTo*, por eso pudimos pasarle una expresión lambda.

---

## 07- Referencias de métodos (Method References)
La referencias a métodos es una funcionalidad muy peculiar de la JDK 1.8 y lo que nos permite es tener el código mucho más legible, y hay 4 maneras de implementarlas.

Tengo un método *operar()* que simplemente utiliza una interfaz llamada **Operacion**, que ésta tiene un único método *saludar()* y es una interfaz funcional para que podamos usar
a través de una expresión lambda el método saludar().

![07_Referencias_de_metodos_02](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_02.png)

![07_Referencias_de_metodos_01](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_01.png)

Si nosotros conocemos el uso de las expresiones lambda, vemos que considerablemente a mejorado la sintaxis de escribir nuestro código, las referencias de métodos viene a aportar más
legibilidad y obviamente menos lineas.

**Primer caso:** Referencia a un método static  
Como estaba escrito el código nos imprime a la salida "Método Referido Static", ahora haremos lo mismo pero con referencia a ese método.  
En op2 -> Indicamos el nombre de la Clase y acá es donde sustituimos la expresión lambda por una referencia a un método, para esto usamos el operador `::`, y hacemos la llamada a ese
método estático. Por el momento vamos a decir que los métodos referenciados no pueden llevar parámetros.

![07_Referencias_de_metodos_03](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_03.png)

**Segundo caso:** Referencia a un método de instancia de un objeto de una clase en particular, un objeto arbitrario.  
Cuerpo del método:

![07_Referencias_de_metodos_04](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_04.png)

Pero si pensamos todo es muy verboso de indicar, que pasaría si queremos reducir eso a una expresión lambda y por medio de ésta luego reducirlo a una referencia de método, quedaría de
la siguiente manera:  
Lambda:

![07_Referencias_de_metodos_05](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_05.png)

Y podemos reducirlo más con la referencia a métodos:

![07_Referencias_de_metodos_06](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_06.png)

En este caso, le pasamos la lista, array Nombres, la Clase **String** que vamos a comparar, en este caso Nombres es un array de tipos de texto e invoco al método *compareToIgnoreCase()*.  
Porque es un método de instancia y no estático? Porque estoy llamando al método que es de la instancia de la variable que viene en el array, es decir en el array internamente se va a
recorrer y cuando llegue elemento por elemento eso ya es una instancia y de ese elemento se va a utilizar el método *compareToIgnoreCase()*.

**Tercer caso:** Referencia a un método de instancia de un objeto en particular.  
Para esto solo estamos indicando un mensaje.  

![07_Referencias_de_metodos_07](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_07.png)

Entonces como invocamos al método?

![07_Referencias_de_metodos_08](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_08.png)

Esto de los métodos a referencia se apoyan mucho en lo que son las interfaces funcionales y lo que hacemos acá es que esta interfaz **Operacion** que tiene un único método *saludar()*,
la implementamos con la expresion de la derecha, es por eso que éste es un método de instancia de este objeto en particular *app*, me apoyo en el operador y le indico el método que va
a implementar el método *saludar()* de la interfaz **Operacion**.  
Es prácticamente una función que se la estoy mandando como implementación a mi método *saludar()*, es por eso que implicitamente Java usa los métodos como si fueran parámetros para poder
implementar otros métodos.

**Cuarto caso:** Referencia a un Constructor.  
Aqui vemos otra interfaz llamada IPersona, que tiene un método crear que lleva un *id* y *nombre*, una vez lo indicamos, obtenemos el objeto Persona.

![07_Referencias_de_metodos_10](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_10.png)

![07_Referencias_de_metodos_09](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_09.png)

Hacemos la llamada a la interfaz funcional **IPersona** e *iper*, y de la manera tradicional con una clase anónima hago new IPersona() y sobreescribimos el método *crear()*. Finalmente
uso esa implementación de interfaz que creamos, su método crear y le paso los parámetros.  
Nuevamente es excesivo el código que tenemos, vamos a simplificarlo.

Lambda

![07_Referencias_de_metodos_11](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_11.png)

Método de referencia  
Recordar que los métodos de referencia siempre se apoyan en interfaces funcionales.

![07_Referencias_de_metodos_12](src/Tutorial_Java_MitoCode/07_Referencias_de_metodos_12.png)

---

## 08- Foreach, RemoveIf, Sort
Mejoras de las Colecciones respecto a JDK 1.7.  
Básicamente tenemos una lista privada a la cual la llenamos con un método y veremos estas 3 formas de implementar las novedades.

![08_ForEach_RemoveIf_Sort_01](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_01.png)

![08_ForEach_RemoveIf_Sort_02](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_02.png)

**usarForEach()**  
Forma clásica

![08_ForEach_RemoveIf_Sort_03](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_03.png)

Aplicando las lambdas y los métodos de referencia. Escribimos `lista.forEach()` y nos dice que necesita un *Consumer* que practicamente es una interfaz funcional que tiene un único método
llamado **accept()**, y este método va a poder recibir una lógica que nosotros implementemos en una expresión lambda o un método de referencia.  
Revisando la documentación vemos que se encuentra *accept()* y tiene también un método default que esta implementado, no hay problema con ello mientras tenga un método nombrado, no
implementado, se respeta el término de las interfaces funcionales.

![08_ForEach_RemoveIf_Sort_04](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_04.png)

Volviendo, este *forEach()* necesita implementar este Consumer, lo hacemos creando una expresión lambda y le indicamos que para cada elemento vamos a imprimirlo.

![08_ForEach_RemoveIf_Sort_05](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_05.png)

Empleando la referencia a métodos:

![08_ForEach_RemoveIf_Sort_06](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_06.png)

**usarRemoveIf()**  
Como su nombre lo indica, vamos a poder remover un elemento dependiendo de la lógica.  
Antes:

![08_ForEach_RemoveIf_Sort_07](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_07.png)

Aunque no se puede eliminar asi en un for dinamico, nos salta un ConcurrentException.

![08_ForEach_RemoveIf_Sort_08](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_08.png)

Y para resolver esto usabamos un **Iterator** con un while

![08_ForEach_RemoveIf_Sort_09](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_09.png)

Se elimina el elemento "Code", pero seguimos con varias lineas de código. Entonces usemos el paradigma funcional

![08_ForEach_RemoveIf_Sort_10](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_10.png)

**Predicate** es una clase muy importante para poder armar "Predicados", intrucciónes que representan una lógica como eliminación, agregación, condicionales, que nos permite ahorrar
mucho código.

**usarSort()**  
Si queremos ordenar esta lista haciamos esto `Collections.sort(lista);` pero podemos apoyarnos exclusivamente en el método *.sort()* de la propia lista y podemos indicar de la siguiente
manera:

![08_ForEach_RemoveIf_Sort_11](src/Tutorial_Java_MitoCode/08_ForEach_RemoveIf_Sort_11.png)

---

## 09- Stream
En más de una ocasión cuando trabajamos con Colecciones nos hemos apoyado en la programación imperativa, definimos algoritmos para filtrar, limitar, contar, ordenar bajo ciertos criterios.
Pero esto demanda a veces muchas lineas de código, Java 8 gracias al Stream API, se va a poder realizar mas sencillamente, usando el paradigma declarativo.  
El API Stream va a darle un plus al desarrollador, nos permite programar de una manera más legible si se apoya conjuntamente con las expresiónes lambdas, podremos realizar operaciónes
como filtros, contar, ordenamientos, etc. De una forma muy declarativa, es decir evitando mucho la implementación línea por línea.

Veremos algunos ejemplos de implementaciones. Básicamente tengo una clase con dos listas privadas, con sus constructores que las llenan y en el main instancio la clase y vamos a ir
llamando a estos métodos veremos.

![09_Stream_01](src/Tutorial_Java_MitoCode/09_Stream_01.png)

**filtrar()**  
En muchas ocasiones hemos tenido la posibilidad o necesidad de filtrar en una lista determinada algunos elementos que respeten algún criterio, por ejemplo en este caso vamos a filtrar
de la lista todos aquellos elementos que empiecen con "M".  
Si pensamos en un enfoque imperativo, deberiamos de recorrer la lista, preguntar si el 1er elemento empieza con "M", si es así podemos almacenar o imprimir ese elemento.  
Pero bajo el enfoque declarativo podemos hacerlo de una forma muy sencilla.  
Indicamos lista, que es de la clase Collections, usamos el método *stream()* y tenemos muchos métodos, uno de ellos es *filter()* que necesita un *Predicate* que básicamente es una
expresión lambda que vamos a evaluar, se leeria: *Quiero de la lista todos aquellos que empiezan con "M"*, y como quiero imprimirlos también, nos apoyamos en el método *forEach()*
y usamos el método de referencia para invocar el println.

![09_Stream_02](src/Tutorial_Java_MitoCode/09_Stream_02.png)

Este método de referencia la podemos reemplazar con una expresión lambda, pero es preferible el anterior.

![09_Stream_03](src/Tutorial_Java_MitoCode/09_Stream_03.png)

**ordenar()**  
Es muy parecido a lo anterior.

![09_Stream_04](src/Tutorial_Java_MitoCode/09_Stream_04.png)

Nos ordena la lista de forma ascendente, pero si lo queremos de forma descendente debemos pasarle a *sort()* una expresión lambda.

![09_Stream_05](src/Tutorial_Java_MitoCode/09_Stream_05.png)

**transformar()**  
Acá usaremos la función *.map()*, esta función es de transformación, es decir que lo que vas a colocar acá (), el elemento de cada lista va a ser transformado con la expresión que
indiquemos.  
Por ejemplo, que pasaría si todos los elementos quiero pasarlos a mayusculas? Podríamos hacer lo siguiente:  
Nos apoyamos en un método de referencia y le indicamos *toUpperCase*

![09_Stream_06](src/Tutorial_Java_MitoCode/09_Stream_06.png)

La función map es para transformar los elementos de esta colección uno a uno a traves de la expresión que estemos indicando como parámetro, y acá entra la lista de numeros.  
Queremos convertir cada elemento a entero (Son de tipo String) y sumarle un número adicional.  
Forma tradicional:

![09_Stream_07](src/Tutorial_Java_MitoCode/09_Stream_07.png)

Ahora apoyandonos en la API Stream y el método map, le decimos que a cada elemento le vas a hacer un Integer.parseInt del mismo elemento y le sumas 1 e imprimimos la colección.

![09_Stream_08](src/Tutorial_Java_MitoCode/09_Stream_08.png)

**limitar()**  
Lo que hacemos acá es usar el método *limit()*, al que se le pasa un entero e imprimimos esa cantidad de elementos.

![09_Stream_09](src/Tutorial_Java_MitoCode/09_Stream_09.png)

**contar()**  
Usamos *count()* que nos devuelve un long, entonces guardamos ese valor e imprimimos la cantidad de elementos de la lista.

![09_Stream_10](src/Tutorial_Java_MitoCode/09_Stream_10.png)

---

## 10- Optional
Nos permite gestionar de una manera adecuada los errores para poder evitar los **NullPointerException**.

![10_Optional_01](src/Tutorial_Java_MitoCode/10_Optional_01.png)

Muestra instanciar Optional vacío

![10_Optional_02](src/Tutorial_Java_MitoCode/10_Optional_02.png)

Este **Optional** es básicamente como un envoltorio, un wrapper, que hay que indicarle el tipo de dato y si queremos obtener el contenido de este envoltorio nos apoyamos en el
método *get()*, devuelve del mismo tipo de dato indicado.  
Si nos sale un error de tipo *NoSuchElementException* es porque el contenido de ese optional no fue inicializado.

![10_Optional_03](src/Tutorial_Java_MitoCode/10_Optional_03.png)

**orElse()**  
Se le indica un valor por defecto cuando el valor es *null* y evitamos el NullException.  
Ya no lo vamos a inicializar en un valor vacío, si no en el valor que se nos pasa en el método. Despues obtengo el valor para imprimirlo. Si es nulo se imprime "Predeterminado" si no
simplemente el valor.

![10_Optional_04](src/Tutorial_Java_MitoCode/10_Optional_04.png)

**orElseThrow**  
Es muy similar al anterior pero en esta ocasión si el valor es nulo podremos arrojar una exception.  
Indicamos de ejemplo el *NumberFormatException* e invocamos al contructor a través del método de referencia , de modo que si tiene un valor nulo arrojara la exception que indicamos si no
simplemente no hará nada.

![10_Optional_05](src/Tutorial_Java_MitoCode/10_Optional_05.png)

**isPresent()**  
Es básicamente para verificar si el valor ha sido inicializado o no. Devuelve un booleano, si le pasamos nulo es false.

![10_Optional_06](src/Tutorial_Java_MitoCode/10_Optional_06.png)

En algunas ocasiones no es muy recomendable usar esto, especialmente si queremos tener apps criticas en rendimiento puesto que usar esta clase es un poco costoso.

---

## 11- Stream paralelo
Sirve para mejorar el rendimiento pero con cuidado ya que es manejo con hilos.  
Tenemos una lista de números que nos va a servir para comprobar el funcionamiento del Stream en paralelo, el stream normal si lo ejecutamos para llenar la lista nos lo hace desde el 0
al 9, en ese orden.

![11_Stream_paralelo_01](src/Tutorial_Java_MitoCode/11_Stream_paralelo_01.png)

Pero si vemos el resultado al usar un *parallelStream()* veremos que el orden cambia cada vez que lo ejecutemos y esto es porque se ejecuta en diferentes hilos.

![11_Stream_paralelo_02](src/Tutorial_Java_MitoCode/11_Stream_paralelo_02.png)

Esto cambia la aplicación y de manera implicita va a utilizar el Framework **Fork/Join**, va a emplearse en un pool de este tipo y va a crear un procesamiento con hilos, asíncrono.

El **Fork/Join** es una implementación de la interfaz *ExecutorService* que lo ayuda a aprovechar múltiples procesadores. Está diseñado para trabajos que se pueden dividir en piezas más
pequeñas de forma recursiva. El objetivo es utilizar toda la potencia de procesamiento disponible para mejorar el rendimiento de su aplicación.  
En Java, el framework fork/join brinda soporte para la programación paralela al dividir una tarea en tareas más pequeñas para procesarlas utilizando los núcleos de CPU disponibles. De
hecho, los flujos paralelos de Java 8 y el método Arrays#parallelSort utilizan bajo el capó el marco de trabajo fork/join para ejecutar tareas paralelas.

Entonces esto puede aliviar o mejorar nuestras apps pero hay documentación, casos de estudio donde indican que abusar de este tipo de parallelStream no es recomendable, especialmente
si trabajamos con Java EE Containers, imaginense tener un ambiente donde ya de por si usamos muchas peticiones, requests, en un ambiente asincrono, podríamos saturarlo un poco más.  
Por ejemplo servidores de en aplicaciónes que tengan interacción con JPA y JB, todo lo que tiene el container propio de Java Enterprise.

Entonces podemos usarlo pero con moderación, no abusen toda su app con streams paralelos y de preferencia en procesos de tipo bach o aplicaciones de escritorio, midamos bien nuestro
tiempo, saquemos provecho a esta forma declarativa de poder usar los hilos de una manera un poco más sencilla y no apoyarnos en lo que son Callable, Future, ExecutorServide, cosa que se
ven en Java 7 SE avanzado.

Algunas páginas para leer un poco más de esto:  
[Caso de estudio](https://www.overops.com/blog/benchmark-how-java-8-lambdas-and-streams-can-make-your-code-5-times-slower/) [DZone](https://dzone.com/articles/whats-wrong-java-8-part-iii)

---

## 12- Map
Compararemos como se implementa y las mejoras de la clase Map en Java 8.  
Cuando queremos recorrer el contenido de un mapa, siempre tenemos que apoyarnos en el *entrySet()*, que viene a ser la lista de valores que tiene nuestro mapa.

![12_Map_01](src/Tutorial_Java_MitoCode/12_Map_01.png)

**imprimir_v8()**  
Pero en Java 8, en esta forma declarativa lo podemos hacer asi:

![12_Map_02](src/Tutorial_Java_MitoCode/12_Map_02.png)

map. e indicamos un *forEach()* que nos pide un *BIConsumer* que practicamente es una expresión lambda que acepta dos parámetros.

Ahora, podemos apoyarnos también en *entrySet()* que nos habilita a poder usar el framework *stream()* para seguir usando esos métodos que vimos antes.  
Entre ellos el forEach() y podemos usar nuestros métodos a referencia.

![12_Map_03](src/Tutorial_Java_MitoCode/12_Map_03.png)

Otros métodos importantes en la clase map:  
**insertarSiAusente()**  
Usamos el método *putIfAbsent()*, este lo que nos provee es poder agregar un valor que le indiquemos si no se encuentra. (con *put()* sí lo agrega, lo sobreescribe en la lista)

![12_Map_04](src/Tutorial_Java_MitoCode/12_Map_04.png)

**operarSiPresente()**  
Es muy parecido al anterior, usamos el método *computerIfPresent()* y si encuentra la llave que le indicamos va a hacer lo que le pasemos como segundo parámetro. En este caso sumar la KEY
con el VALUE.

![12_Map_05](src/Tutorial_Java_MitoCode/12_Map_05.png)

**obtenerOrPredeterminado()**  
Con la función *getOrDefault()*, básicamente lo que hace es que si no existe el valor para esa KEY le asignaremos un valor por defecto, si existe no hace nada.

![12_Map_06](src/Tutorial_Java_MitoCode/12_Map_06.png)

**recolectar()**  
Es algo que se utiliza en operaciones con listas o mapas, imaginemos tener un conjunto de elementos en un mapa y queremos filtrar esos elementos bajo un criterio a otra lista o mapa.  
Vamos a evaluar el mapa, filtrar y crear un mapa nuevo.  
Entonces creamos un nuevo mapa, nos apoyamos en `entreySet().stream().filter()` y acá indicamos el predicado que necesitamos para el filtrado `e-getValue().contains("Sus"))` entonces le
indicamos que se filtre si algun elemento empieza con "Sus". Y nos apoyamos en el método `collect()`. Especificamente en la clase `Collectors.toMap()` y este toMap() va a necesitar evaluar
como armar este nuevo mapa en base a la colección filtrada, para ellos vamos a indicar lo siguiente `p-> p.getKey(), p-> p.getValue()` estamos armando llave y valor del nuevo elemento.
E imprimimos en Java 8

![12_Map_07](src/Tutorial_Java_MitoCode/12_Map_07.png)

---

## 13- Anotaciónes de repetición
## 14- Date API
## 15- Funciones de alto orden
## 16- RxJava
## 17- Nashorm