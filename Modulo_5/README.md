Actividades Optativas Módulo 5.

Unidad 6 · UNION vs UNION ALL: conceptos y ejemplos:

¿Cuántas filas devuelve cada consulta y por qué son distintas? Explicá con ejemplos concretos de los datos qué filas se eliminaron con UNION.
La primera consulta devuelve 11 filas, mientras que la segunda devuelve 14. Esta diferencia se debe a que UNION elimina las filas duplicadas, mientras que UNION ALL conserva todos los registros, incluidas las repeticiones.
En este caso, los productos repetidos son Monitor 4K 27'' (103), Teclado Mecánico (104) y SSD Externo 1TB (106). Estos productos aparecen en ambas tablas, por lo que UNION conserva una sola aparición de cada uno y elimina las otras tres filas.
La tercera consulta está compuesta por dos operaciones independientes que utilizan COUNT(*). Cada una devuelve una única fila: la primera contiene el valor 11, correspondiente a la cantidad de registros obtenidos mediante UNION, y la segunda contiene el valor 14, correspondiente a los registros obtenidos mediante UNION ALL.

¿Por qué UNION ALL es más eficiente que UNION? ¿Qué operación adicional realiza UNION internamente que consume más recursos?
UNION ALL es más eficiente porque combina los resultados de ambas consultas sin comprobar si existen registros duplicados. En cambio, UNION realiza una operación adicional para identificar y eliminar las filas repetidas, lo que requiere mayor consumo de recursos.

¿En qué casos de negocio usarías cada uno? Dá al menos dos ejemplos reales distintos a los del ejercicio.
UNION: Se podría utilizar para unificar las listas de clientes de dos empleados de una empresa. En caso de que ambos hayan atendido al mismo cliente UNION permitiría excluir los registros duplicados y obtener una lista general sin repeticiones.

UNION ALL: Se podría utilizar en un banco para unificar los registros de transacciones de distintos meses. En este caso sería importante conservar todos los movimientos, incluso si algunos tienen datos iguales, ya que excluirlos podría alterar el resultado del análisis financiero.

¿Qué pasa si las columnas de ambas consultas no coinciden en número o tipo? ¿Qué error genera SQL?
Debido a que UNION necesita que ambas consultas tengan el mismo número de columnas, si estas no coinciden en cantidad se genera un error de estructura (205). En caso de que las columnas no coincidan en tipo de dato, SQL intentará convertirlas a un tipo compatible. Si no puede realizar esa conversión, generará un error de conversión.
