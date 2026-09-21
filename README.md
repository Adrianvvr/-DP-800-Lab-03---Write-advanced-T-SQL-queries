# DP-800 Lab 03: Escribir consultas T-SQL avanzadas

## 🎯 Objetivo
Practicar el uso de funciones JSON para generar y analizar datos, combinándolas con expresiones de tabla comunes (CTE) y funciones de ventana (Window Functions) en la base de datos `AdventureWorksLT`.

## 📝 Resumen de Pasos

1. **Verificar la Conexión:** Comprobar el acceso a la base de datos `AdventureWorksLT` realizando consultas básicas (`SELECT TOP 5`) a las tablas `Product` y `ProductCategory`.
2. **Generar salida JSON:** Usar la cláusula `FOR JSON PATH` para convertir un conjunto de resultados de productos directamente en un array de objetos JSON.
3. **Crear JSON anidado:** Utilizar la función `JSON_OBJECT` combinada con un `INNER JOIN` para anidar los datos de la categoría dentro del objeto JSON de cada producto.
4. **Uso de CTE y Window Functions:** Construir una CTE que utilice `ROW_NUMBER() OVER (PARTITION BY ... ORDER BY ...)` para calcular un ranking de los productos más caros dentro de cada categoría.
5. **Exportar Reporte a JSON:** Filtrar el top 3 de productos por categoría desde la CTE y exportar el resultado final agregando `FOR JSON PATH, ROOT('TopProducts')` para envolver el array en un elemento raíz.
6. **Analizar datos con OPENJSON:** Declarar una variable de texto con formato JSON y utilizar la función `OPENJSON` junto con la cláusula `WITH` para convertir el texto JSON en columnas y filas tipadas (tabla relacional).
7. **Hacer JOIN con datos JSON:** Cruzar (`INNER JOIN`) la tabla temporal generada por `OPENJSON` (que contiene actualizaciones de precio) con la tabla física `Product` para comparar el precio actual con el nuevo precio propuesto.
8. **Limpieza (Opcional):** Eliminar la base de datos `AdventureWorksLT` marcando la opción de cerrar conexiones existentes desde SSMS, si no se va a utilizar en futuras prácticas.
