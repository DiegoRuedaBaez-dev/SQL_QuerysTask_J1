# Consultas sobre una tabla:
### 1. Lista el nombre de todos los productos que hay en la tabla producto.
```SQL:
SELECT prod.nombre
FROM producto as prod;
```
### 2. Lista los nombres y los precios de todos los productos de la tabla producto.
```SQL:
SELECT prod.nombre, prod.precio
FROM producto as prod;
```
### 3. Lista todas las columnas de la tabla producto.Ç
```SQL:
SELECT prod.nombre, prod.precio,prod.codigo_fabricante
FROM producto as prod;
```
### 4. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD).
```SQL:
SELECT prod.nombre, prod.precio, prod.precio * 1.06 as euros
FROM producto as prod;
```
### 5. Lista el nombre de los productos, el precio en euros y el precio en dólares estadounidenses (USD). Utiliza los siguientes alias para las columnas: nombre de producto, euros, dólares.
```SQL:
SELECT prod.nombre as 'Nombre de Producto', prod.precio as dólares, prod.precio * 1.06 as euros
FROM producto as prod;
```
### 6. Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a mayúscula.
```SQL:
SELECT UPPER(prod.nombre) as 'NOMBRE PRODUCTOS', prod.precio
FROM producto as prod;
```
### 7. Lista los nombres y los precios de todos los productos de la tabla producto, convirtiendo los nombres a minúscula.
```SQL:
SELECT LOWER(prod.nombre) as 'NOMBRE PRODUCTOS', prod.precio
FROM producto as prod;
```
### 8. Lista el nombre de todos los fabricantes en una columna, y en otra columna obtenga en mayúsculas los dos primeros caracteres del nombre del fabricante.
```SQL:
SELECT prod.name as 'Nombre de Productos', UPPER(SUBSTRING (prod.name, 1, 2)) as 'Iniciales en Mayús'
FROM producto as prod;
```
### 9. Lista los nombres y los precios de todos los productos de la tabla producto, redondeando el valor del precio.
```SQL:
SELECT prod.name as 'Nombre de Productos', ROUND(prod.precio,0) as 'Precio'
FROM producto as prod;
```
### 10. Lista los nombres y los precios de todos los productos de la tabla producto, truncando el valor del precio para mostrarlo sin ninguna cifra decimal.
```SQL:
SELECT prod.name as 'Nombre de Productos', TRUNCATE(prod.precio,0) as 'Precio'
FROM producto as prod;
```
### 11. Lista el identificador de los fabricantes que tienen productos en la tabla producto.
```SQL:
SELECT prod.name as 'Nombre de Productos', TRUNCATE(prod.precio,0) as 'Precio'
FROM producto as prod;
```
### 12. Lista el identificador de los fabricantes que tienen productos en la tabla producto, eliminando los identificadores que aparecen repetidos.
```SQL:
SELECT DISTINCT prod.codigo_fabricante as 'Identificador Fabricante'
FROM producto as prod;
```
### 13. Lista los nombres de los fabricantes ordenados de forma ascendente.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
ORDER BY fab.nombre ASC;
```
### 14. Lista los nombres de los fabricantes ordenados de forma descendente.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
ORDER BY fab.nombre DESC;
```
### 15. Lista los nombres de los productos ordenados en primer lugar por el nombre de forma ascendente y en segundo lugar por el precio de forma descendente.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
ORDER BY fab.nombre ASC, precio DESC;
```
### 16. Devuelve una lista con las 5 primeras filas de la tabla fabricante.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
LIMIT 5;
```
### 17. Devuelve una lista con 2 filas a partir de la cuarta fila de la tabla fabricante. La cuarta fila también se debe incluir en la respuesta.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
LIMIT 3,3;
```
### 18. Lista el nombre y el precio del producto más barato. (Utilice solamente las cláusulas ORDER BY y LIMIT)
```SQL:
SELECT prod.precio as 'Precio'
FROM producto as prod
ORDER BY prod.precio ASC
LIMIT 0,1;
```
### 19. Lista el nombre y el precio del producto más caro. (Utilice solamente las cláusulas ORDER BY y LIMIT)
```SQL:
SELECT prod.precio as 'Precio'
FROM producto as prod
ORDER BY prod.precio DESC
LIMIT 0,1;
```
### 20. Lista el nombre de todos los productos del fabricante cuyo identificador de fabricante es igual a 2.
```SQL:
SELECT prod.codigo_fabricante as 'Identificador Fabricante', prod.nombre as "Nombre Fabricante"
FROM producto as prod;
WHERE prod.codigo_fabricante = 2;
```
### 21. Lista el nombre de los productos que tienen un precio menor o igual a 120€.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio = 120 or prod.precio < 120;
```
### 22. Lista el nombre de los productos que tienen un precio mayor o igual a 400€.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio = 400 or prod.precio > 400;
```
### 23. Lista el nombre de los productos que no tienen un precio mayor o igual a 400€.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio != 400 or prod.precio <> 400;
```
### 24. Lista todos los productos que tengan un precio entre 80€ y 300€. Sin utilizar el operador BETWEEN.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio > 80 or prod.precio < 300;
```
### 25. Lista todos los productos que tengan un precio entre 60€ y 200€. Utilizando el operador BETWEEN.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio BETWEEN 60 AND 200;
```
### 26. Lista todos los productos que tengan un precio mayor que 200€ y que el identificador de fabricante sea igual a 6.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio > 200 AND prod.codigo_fabricante = 6;
```
### 27. Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Sin utilizar el operador IN.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.codigo_fabricante = 1 OR prod.codigo_fabricante = 3 OR prod.codigo_fabricante = 5;
```
### 28. Lista todos los productos donde el identificador de fabricante sea 1, 3 o 5. Utilizando el operador IN.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.codigo_fabricante IN (1, 3, 5)
```
### 29. Lista el nombre y el precio de los productos en céntimos (Habrá que multiplicar por 100 el valor del precio). Cree un alias para la columna que contiene el precio que se llame céntimos.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio', prod.precio * 100 as 'Precio (Centimos)'
FROM producto as prod;
```
### 30. Lista los nombres de los fabricantes cuyo nombre empiece por la letra S.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
WHERE fab.nombre LIKE 'S%'
```
### 31. Lista los nombres de los fabricantes cuyo nombre termine por la vocal e.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
WHERE fab.nombre LIKE '%E'
```
### 32. Lista los nombres de los fabricantes cuyo nombre contenga el carácter w.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
WHERE fab.nombre LIKE '%W%'
```
### 33. Lista los nombres de los fabricantes cuyo nombre sea de 4 caracteres.
```SQL:
SELECT fab.nombre as 'Nombre Fabricante'
FROM fabricante as fab
WHERE LENGHT(fab.nombre)>=4;
```
### 34. Devuelve una lista con el nombre de todos los productos que contienen la cadena Portátil en el nombre.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.nombre LIKE '%Portátil%';
```
### 35. Devuelve una lista con el nombre de todos los productos que contienen la cadena Monitor en el nombre y tienen un precio inferior a 215 €.
```SQL:
SELECT prod.nombre as 'Nombre Producto', prod.precio as 'Precio'
FROM producto as prod
WHERE prod.nombre LIKE '%Monitor%' AND prod.precio < 215;
```
### 36. Lista el nombre y el precio de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente).
```SQL:
SELECT prod.nombre as 'Nombre Producto',prod.precio as 'Precio'
FROM producto as prod
WHERE prod.precio >= 180
ORDER BY prod.nombre DESC, prod.precio ASC
```
# Consultas Multitabla (Composiciòn Interna):

### 1. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo;
```
### 2. Devuelve una lista con el nombre del producto, precio y nombre de fabricante de todos los productos de la base de datos. Ordene el resultado por el nombre del fabricante, por orden alfabético.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
ORDER BY fab.nombre ASC;
```
### 3. Devuelve una lista con el identificador del producto, nombre del producto, identificador del fabricante y nombre del fabricante, de todos los productos de la base de datos.
```SQL:
SELECT prod.codigo as 'Indentificador Producto',prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio',fab.codigo as 'Identificador Fabricante', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo;
```
### 4. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más barato.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE prod.precio = (SELECT MIN(prod.precio) FROM producto);
```
### 5. Devuelve el nombre del producto, su precio y el nombre de su fabricante, del producto más caro.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE prod.precio = (SELECT MAX(prod.precio) FROM producto);
```
### 6. Devuelve una lista de todos los productos del fabricante Lenovo.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE fab.nombre LIKE '%Lenovo%';
```
### 7. Devuelve una lista de todos los productos del fabricante Crucial que tengan un precio mayor que 200€.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE fab.nombre LIKE '%Crucial%' AND prod.precio > 200;
```
### 8. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Sin utilizar el operador IN.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE fab.nombre LIKE '%Asus%' AND fab.nombre LIKE '%Hewlett-Packardy%' AND fab.nombre LIKE '%Seagate%';
```
### 9. Devuelve un listado con todos los productos de los fabricantes Asus, Hewlett-Packardy Seagate. Utilizando el operador IN.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE fab.nombre IN ('Asus','Hewlett-Packardy','Seagate');
```
### 10. Devuelve un listado con el nombre y el precio de todos los productos de los fabricantes cuyo nombre termine por la vocal e.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE fab.nombre LIKE '%e';
```
### 11. Devuelve un listado con el nombre y el precio de todos los productos cuyo nombre de fabricante contenga el carácter w en su nombre.
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE fab.nombre LIKE '%w%';
```
### 12. Devuelve un listado con el nombre de producto, precio y nombre de fabricante, de todos los productos que tengan un precio mayor o igual a 180€. Ordene el resultado en primer lugar por el precio (en orden descendente) y en segundo lugar por el nombre (en orden ascendente)
```SQL:
SELECT prod.nombre AS 'Nombre Producto', prod.precio AS 'Precio', fab.nombre AS 'Fabricante'
FROM producto AS prod
INNER JOIN fabricante AS fab ON prod.codigo_fabricante = fab.codigo
WHERE prod.precio >= 180
ORDER BY prod.nombre DESC AND prod.precio ASC;
```
### 13. Devuelve un listado con el identificador y el nombre de fabricante, solamente de aquellos fabricantes que tienen productos asociados en la base de datos.
```SQL:
SELECT fab.codigo AS 'Identificador Fabricante', fab.nombre AS 'Nombre Fabricante'
FROM fabricante AS fab
INNER JOIN producto AS prod ON fab.codigo = prod.codigo_fabricante;
```