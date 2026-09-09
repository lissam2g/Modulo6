# Transformaciones realizadas
## 1. Cambio del tipo de dato de id_producto

Cambié el tipo de dato de la columna id_producto de decimal a texto, porque corresponde a un identificador de producto y no a un valor sobre el cual se realizarán operaciones matemáticas. Al tratarlo como texto, se conserva su función de código o identificador.

## 2. Eliminación de filas sin datos

Eliminé las filas que no contenían ningún dato en sus columnas, ya que corresponden a registros completamente vacíos que no aportan información para el análisis. Con esta transformación evité conservar filas innecesarias en el conjunto de datos.

## 3. Reemplazo de valores nulos en descuento

Reemplacé los valores null de la columna descuento por 0, considerando que la ausencia de un valor de descuento representa una venta sin descuento. Esto permite conservar los registros y facilita los cálculos posteriores relacionados con el valor de las ventas.

## 4. Cálculo de valores nulos en total_venta

Calculé los valores null de la columna total_venta utilizando los valores disponibles de precio_unitario, cantidad y descuento. Utilicé la fórmula: total_venta = cantidad × precio_unitario × (1 − descuento)
Conservé los valores de total_venta que ya tenían información y calculé únicamente los que se encontraban nulos. De esta manera, recuperé información faltante sin eliminar registros de ventas que podían ser completados a partir de los demás datos disponibles.

##  5. Eliminación de filas duplicadas

Eliminé las filas duplicadas para evitar que un mismo registro fuera contabilizado más de una vez durante el análisis. Realicé esta transformación después de las demás operaciones de limpieza para trabajar sobre los datos ya corregidos y evitar duplicidades en el conjunto final.
