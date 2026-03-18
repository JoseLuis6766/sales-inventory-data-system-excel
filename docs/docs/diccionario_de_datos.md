# Diccionario de datos

## Hoja Catalogos
Contiene los valores maestros utilizados para estandarizar la captura de datos.

- Marca
- Tipo de cuello
- Manga
- Estampado
- Color
- Talla
- Tipo de tela

## Hoja Ventas
Registra las transacciones de venta.

- Marca: marca comercial de la camisa
- Tipo de cuello: clasificación del cuello
- Manga: larga o corta
- Estampado: patrón visual
- Color: color estandarizado
- Talla: talla comercial
- Cantidad: unidades vendidas
- Fecha: fecha de la venta
- ID_Camisa: identificador generado automáticamente con base en atributos del producto
- Control_Inventario: estado de validación contra inventario

## Hoja Inventario
Registra el inventario base y el stock calculado.

- ID_Camisa: identificador único del producto
- Color: color estandarizado
- Talla: talla comercial
- Cantidad: stock registrado en el último conteo
- Marca: marca comercial
- Estampado: patrón visual
- Manga: larga o corta
- Tipo de cuello: clasificación del cuello
- Fecha: fecha del conteo registrado
- Stock_Actual_Calculado: stock después de descontar ventas posteriores al corte
