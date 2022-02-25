# Curso de Java SE Persistencia de Datos

Empieza ya desarrollando el primer proyecto del curso, que permite ver y publica mensajes, muy similar a Twitter.

Utiliza [Draw IO](https://www.draw.io/) para hacer los diagramas del proyecto

![04_Diseñando_nuestra_BD_01](src/Curso_Java_Persistencia_Datos/04_Diseñando_nuestra_BD_01.png)


Clase 8 - Conección a Mysql desde Java

En la clase anterior vimos como crear un proyecto basico en NetBaens.

![07_Creación_del_proyecto_en_Java_01](src/Curso_Java_Persistencia_Datos/07_Creación_del_proyecto_en_Java_01.png)

Ahora vamos a conectar esa aplicacion con una base de datos Mysql, con lo que necesitamos un conector, que es un plugin que te permite generar la conexion entre Java como aplicacion
y el motor de base de datos Mysql.

Vamos a utilizar la carpeta de Dependencias que es donde se instalan todas las dependencias o plugins que necesitemos para conectar Java con otros sistemas.

![08_Conexión_a_MySQL_desde_Java_01](src/Curso_Java_Persistencia_Datos/08_Conexión_a_MySQL_desde_Java_01.png)

Buscamos el conector que se llama **mysql-connector-java**, seleccionamos la última versión y la agregamos.
Lo que hace es traer todos los plugins para trabajar con la base de datos.

![08_Conexión_a_MySQL_desde_Java_02](src/Curso_Java_Persistencia_Datos/08_Conexión_a_MySQL_desde_Java_02.png)

**Ahora vamos a crear el código para conectarnos a esa BD.**

Creamos una nueva Clase Java, en la cual creamos un método que va a devolver un objeto de tipo Connection y la vamos a llamar get_connection, entonces este método va a tener
todas las funcionalidades para conectarnos a la BD y probar la conección.
Para esto definimos un objeto de tipo Connection, llamada connection. Importamos el paquete correspondiente (java.sql.Connection).

Mediante un bloque de Try-Catch tratamos de hacer la conección.
Drive Manager es un clase para hacer la conexion con la BD y le pasamos como parametro todos los datos que necesita:
El primero es "jdbc:mysql://localhost:3306/mensajes_app -> le pasamos la ruta de nuestro host, en este caso local host, el puerto donde corre el servicio de BD y el nombre de la BD.
El segundo parametro es el usuario de la BD, en este caso "root".
Tercer parametro la contraseña -> en este caso "" (vacio)

![08_Conexión_a_MySQL_desde_Java_03](src/Curso_Java_Persistencia_Datos/08_Conexión_a_MySQL_desde_Java_03.png)

Esta configuración es una configuración que trae por defecto el paquete de herramientas que trae lampp, cuando estámos trabajando en producción es recomendable tener un propio usuario
de BD con una contraseña y tal vez usar otro puerto.

En Inicio, vamos a ejecutar y validar si verdaderamente la conexión es exitosa.

En el try le decimos que nos va a devolver un objeto de tipo Connection, un objeto llamado cnx que va a ser igual a conexion y llamamos al método get_connection().
Importamos también la clase java.sql.Connection.

![08_Conexión_a_MySQL_desde_Java_04](src/Curso_Java_Persistencia_Datos/08_Conexión_a_MySQL_desde_Java_04.png)

Ya tenemos la conexxxion a la BD y ahora podemos empezar a desarrollar el proyecto.

![08_Conexión_a_MySQL_desde_Java_05](src/Curso_Java_Persistencia_Datos/08_Conexión_a_MySQL_desde_Java_05.png)