# Transformaciones realizadas

## 1. Renombrar columnas

Renombré las columnas utilizando nombres más descriptivos y fáciles de interpretar, reemplazando los nombres técnicos del archivo original por nombres que permiten identificar claramente la información contenida en cada campo. Esto facilita la lectura, comprensión y posterior análisis de los datos.

## 2. Cambio de tipos de datos

Cambié los tipos de datos de las columnas de acuerdo con la naturaleza de cada variable. Cambié la columna `F_VTA` a tipo fecha, eliminando la información correspondiente a la hora, ya que para el análisis se necesita la fecha en que se realizó la venta. También cambié `COD_PROD` de decimal a texto, porque corresponde a un código de producto y no a un valor sobre el cual se realizarán operaciones matemáticas.

## 3. Eliminación de filas sin datos

Eliminé las filas que no contenían ningún dato en sus columnas, ya que corresponden a registros completamente vacíos que no aportan información para el análisis. Con esta transformación evité conservar filas innecesarias en el conjunto de datos.

## 4. Reemplazo de valores nulos en descuento

Reemplacé los valores null de la columna `descuento` por 0, considerando que la ausencia de un valor de descuento representa una venta sin descuento. Esto permite conservar los registros y facilita los cálculos posteriores relacionados con el valor de las ventas.

## 5. Cálculo de valores nulos en total_venta

Calculé los valores null de la columna `total_venta` utilizando los valores disponibles de `precio_unitario`, `cantidad` y `descuento`. Utilicé la fórmula:

**total_venta = cantidad × precio_unitario × (1 − descuento)**

Conservé los valores de `total_venta` que ya tenían información y calculé únicamente los que se encontraban nulos. De esta manera, recuperé información faltante sin eliminar registros de ventas que podían ser completados a partir de los demás datos disponibles.

## 6. Eliminación de filas duplicadas

Eliminé las filas duplicadas para evitar que un mismo registro fuera contabilizado más de una vez durante el análisis. Realicé esta transformación después de las demás operaciones de limpieza para trabajar sobre los datos ya corregidos y evitar duplicidades en el conjunto final.

## 7. Separación de las tablas

Separé la información en dos tablas: `CLIENTES` y `VENTAS_EXPORT`, utilizando una consulta de referencia a partir de los datos previamente transformados.

En la tabla `CLIENTES` conservé la información relacionada con los clientes:

- `codigo_cliente`
- `nombre_cliente`
- `correo_cliente`
- `telefono`
- `ciudad`
- `provincia`
- `segmento_cliente`
- `Estado`
- `fecha_alta`

En la tabla `VENTAS_EXPORT` conservé la información relacionada con las ventas:

- `codigo_operacion`
- `codigo_cliente`
- `fecha_venta`
- `codigo_producto`
- `descripcion_producto`
- `rubro`
- `cantidad`
- `precio_unitario`
- `descuento`
- `total_venta`
- `moneda`
- `canal`

Realicé esta separación para organizar la información de acuerdo con su naturaleza y facilitar el análisis posterior. La columna `codigo_cliente` se mantiene en ambas tablas como campo común para relacionar la información de los clientes con sus respectivas ventas.
