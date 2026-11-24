# union-retailchain

1.¿Cuántas filas devuelve cada consulta y por qué son distintas? Explicá con ejemplos concretos de los datos qué filas se eliminaron con UNION.
La consulta con UNION devuelve 11 filas y la que tiene UNION ALL devuelve 14 filas. La diferencia es porque la que tiene UNION elimina las filas duplicadas, mientras la que tiene UNION ALL conserva todos los registros. Por ejemplo.. los productos con ID 103 (Monitor 4K 27"), 104 (Teclado Mecánico) y 106 (SSD Externo 1TB) aparecen en las dos sucursales con el mismo identificador, nombre y categoria. 
Cuando se usa UNION, esas tres filas se cuentan una sola vez y cuando se usa UNION ALL se conservan las dos de cada producto.
La Webcam HD 1080p no se elimina porque tiene distintos identificadores, 107 en Norte y 111 en Sur.

2.¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?
UNION ALL es mas eficiente porque combina los resultados sin tener que buscar y eliminar los duplicados.
UNION necesita realizar una operaciones extras para identificar las filas repetidas, estas operaciones consumen recursos adicionales y pueden aumentar el tiempo de ejecución..
Por eso cuando necesitamos conservar todos los registros, conviene utilizar UNION ALL.

3.¿En qué casos de negocio usarías cada uno? Dá al menos dos ejemplos reales distintos a los del ejercicio.
Utilizaria UNION en situaciones donde necesito obtener informacion sin filas repetidas

Por ejemplo
- Unificar los correos electronicos de clientes provenientes de distintas bases de datos.
- Crear un catalogo unico de proveedores que aparecen registrados en diferentes sistemas.

Utilizaria UNION ALL cuando necesito conservar todos los registros originales

Por ejemplo
- Combinar las ventas de diferentes sucursales para analizar el volumen total.
- Unificar los registros de pedidos de distintos meses para saber la actividad completa de una empresa.

4.¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?
Para que se puedan usar ambas consultas (UNION o UNION ALL), las consultas tienen que tener la misma cantidad de columnas y tienen que aparecer en el mismo orden.
Si una consulta tiene cuatro columnas y la otra solo tiene tres columnas, SQL Server te tira un error indicando que las consultas tienen diferente cantidad de expresiones en sus listas de seleccion.
Tambien tiene que tener tipos de datos compatibles entre sus columnas. Porque si no son compatibles, SQL Server puede generar un error de conversion de tipos.
Por eso es importante revisar la estructura de ambas consultas antes de combinarlas.
