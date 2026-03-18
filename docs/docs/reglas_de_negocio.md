# Reglas de negocio

## 1. Estandarización de atributos
Los atributos del producto se capturan mediante catálogos maestros para reducir inconsistencias en la información.

## 2. Generación de ID_Camisa
El ID_Camisa se genera automáticamente a partir de atributos clave del producto:

- Marca
- Tipo de cuello
- Manga
- Estampado
- Color
- Talla

Esto permite relacionar registros entre ventas e inventario.

## 3. Fecha de corte de inventario
La fecha máxima registrada en la hoja Inventario se considera como fecha de corte global para el cálculo del stock actual.

## 4. Cálculo de stock
El Stock_Actual_Calculado se obtiene restando a la cantidad de inventario las ventas con fecha mayor o igual a la fecha de corte.

## 5. Control de inventario en ventas
Cada venta se valida contra inventario para identificar si:

- la fecha aplica al corte
- el ID_Camisa existe en inventario
- hay stock suficiente

## 6. Excepciones posibles
El campo Control_Inventario puede mostrar estados como:

- Descontado
- Fecha no aplica
- No encontrado en inventario
- Stock insuficiente
