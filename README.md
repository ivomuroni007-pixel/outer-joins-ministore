¿Por qué usaste LEFT JOIN para la Consulta 1 y no INNER JOIN? ¿Qué se perdería si usaras INNER JOIN?
Se utilizó LEFT JOIN porque devuelve las filas de la tabla izquierda (producto_id) que quiero conservar, y, las filas coincidentes de la tabla derecha (ventas_id) junto con los resultados NULL que representan no coincidencias. De esta manera se puede ver cuáles son los productos que no se vendieron. 
Si utilizaba el INNER JOIN no obtendría el resultado deseado. Me devolvería las filas coincidentes de ambas tablas, sin mostrar la existencia de productos sin ventas, ese dato estaría oculto por una mala elección del JOIN. 


¿Por qué usaste RIGHT JOIN para la Consulta 2? ¿Qué tabla está a la izquierda y cuál a la derecha en tu consulta?
Porque necesitaba conservar las filas de la tabla derecha (producto_id) para identificar los valores sin coincidencias de la tabla izquierda (venta_id). De esta manera se puede identificar, exactamente, cuál es la venta que tiene adjudicada un producto el cuál no está en el catálogo. 


¿Qué representan los valores NULL en cada resultado? Explicá con un ejemplo concreto de los datos qué significa que venta_id sea NULL en la Consulta 1 y que producto_id de productos sea NULL en la Consulta 2.
En la Consulta 1, si venta_id es NULL significa que el producto no fué vendido hasta el momento. 
En la consulta 2, si producto_id de productos es NULL significa que la venta número 10 tiene producto que no figura en el catálogo. 


¿Cuándo usarías FULL OUTER JOIN en un caso real de negocio?
Lo utilizaría para análisis de integridad, auditorías o validación de datos, porque permite visualizar tanto coincidencias como ausencias en ambas tablas.
