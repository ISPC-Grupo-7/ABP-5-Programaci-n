Guía de Ejecución de Scripts SQL

Este documento te guiará a través de los pasos necesarios para ejecutar los scripts DDL y DML de la base de datos hogar_inteligente usando MySQL Workbench o en One Compiler (el gestor de base de datos que utilizamos en el grupo).

1) Archivos del Proyecto
El archivo ddl_dml_script.sql contiene:

La definición de la estructura de la base de datos y sus tablas (DDL).

La inserción de los datos de prueba (DML).

Consultas de verificación (SELECT *) al final de la inserción de cada tabla para demostrar que los datos se cargaron correctamente.

2) Requisitos

Tener acceso a una base de datos MySQL (ya sea local o en la nube).
Tener instalado MySQL Workbench o una herramienta similar (por ejemplo, DBeaver, HeidiSQL).

3)Pasos para la Ejecución en Entornos Online (One Compiler)

Dado que One Compiler ya proporciona un esquema MySQL activo y restringe comandos como CREATE DATABASE y USE, la ejecución debe ser directa:

a) Abre el Archivo SQL: Abre el archivo ddl_dml_script.sql en tu editor de código o revisa su contenido.

    Preparación (Crucial para Online DBMS):

      Verifica que las líneas DROP DATABASE IF EXISTS hogar_inteligente;, CREATE DATABASE hogar_inteligente; y USE hogar_inteligente; estén comentadas        (con doble guion --) o eliminadas.

b) Copia y Pegado:

      Copia el código completo (DDL + DML + SELECTs).

      Pega el código en la ventana de edición de One Compiler, asegurándote de que el lenguaje seleccionado sea MySQL.

c) Ejecución y Resultados:

      Haz clic en el botón "Run" o "Ejecutar".

      El sistema procesará secuencialmente: la creación de las tablas, la inserción de los datos y, finalmente, mostrará los resultados de los comandos       SELECT * en la sección de salida (Output), confirmando que todos los registros se cargaron correctamente

4) Pasos para la Ejecución (MySQL Workbench)

    1. Ejecutar el Script DDL (Definición de Datos)
        El script ddl_script.sql es el que crea la estructura de la base de datos y todas sus tablas. Es crucial que este script se ejecute primero.

    Abre MySQL Workbench y conéctate a tu instancia de MySQL.
        Haz clic en File -> Open SQL Script... y selecciona el archivo ddl_script.sql.
        Una vez que el script esté abierto, haz clic en el botón de "ejecutar" (el icono del rayo) o presiona Ctrl + Shift + Enter.
        Si el script se ejecuta correctamente, verás un mensaje de éxito. Esto significa que la base de datos hogar_inteligente y todas sus tablas han          sido creadas.

  2. Ejecutar el Script DML (Manipulación de Datos)
        El script dml_script.sql es el que llena la base de datos con los registros de prueba que hemos creado. Este script debe ejecutarse después del         DDL para evitar errores.
        En MySQL Workbench, asegúrate de que estás conectado a la base de datos hogar_inteligente. Puedes hacerlo haciendo doble clic en el nombre de           la base de datos en el panel del lado izquierdo.
        Haz clic en File -> Open SQL Script... y selecciona el archivo dml_script.sql.
        Una vez que el script esté abierto, haz clic en el botón de "ejecutar" (el icono del rayo) o presiona Ctrl + Shift + Enter.
        Si la ejecución es exitosa, todos los datos de prueba habrán sido insertados en las tablas.


Nota Importante

El script ddl_script.sql incluye la línea DROP DATABASE IF EXISTS hogar_inteligente; al inicio. Esto es para evitar errores de duplicados si lo ejecutas varias veces. Al ejecutar el DDL, la base de datos anterior se eliminará y se creará una nueva, permitiendo que el script DML se ejecute sin problemas.
