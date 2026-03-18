# Sistema de Ventas e Inventario en Excel

Sistema estructurado de ventas e inventario desarrollado en Excel para una microempresa, con catálogos maestros, generación automática de identificadores de producto, validación de datos y conciliación dinámica de stock.

---

## Resumen del proyecto

Este proyecto surge de una necesidad real: la microempresa registraba sus ventas manualmente en libreta, con descripciones inconsistentes y alta ambigüedad, lo que dificultaba el control de inventario, la trazabilidad de productos y el análisis de ventas.

Ante este problema, diseñé y construí desde cero un sistema estructurado en Excel, definiendo la arquitectura del archivo, los atributos del producto, las reglas de captura y la lógica de automatización, con el objetivo de transformar registros manuales no estandarizados en una base de datos confiable, consistente y analizable.

---

## Problema de negocio

Antes del proyecto, la operación presentaba las siguientes limitaciones:

- Ventas registradas manualmente y sin estructura
- Productos descritos de forma inconsistente
- Dificultad para relacionar ventas con inventario
- Ausencia de control dinámico de stock
- Limitada capacidad de análisis por falta de estandarización

---

## Solución desarrollada

Diseñé e implementé un sistema basado en tres componentes principales:

- **Catalogos**: estructura de datos maestros para estandarizar atributos del producto
- **Ventas**: registro transaccional con generación automática de identificador único (`ID_Camisa`)
- **Inventario**: registro de conteo base con cálculo dinámico del stock actual

---

## Arquitectura del sistema

El sistema fue diseñado en tres capas funcionales:

- **Catalogos** → concentra los datos maestros y estandariza los atributos del producto
- **Ventas** → registra las transacciones y genera automáticamente el `ID_Camisa`
- **Inventario** → conserva el conteo base y calcula el stock actual con base en las ventas posteriores al corte

## Automatización implementada

Para convertir un registro manual en un sistema funcional de control, implementé las siguientes automatizaciones:

- Generación automática de `ID_Camisa` a partir de atributos del producto (marca, cuello, manga, estampado, color y talla)
- Validación de datos mediante catálogos maestros para asegurar consistencia en la captura
- Cálculo dinámico de `Stock_Actual_Calculado` basado en ventas posteriores al último corte de inventario
- Implementación de la columna `Control_Inventario` para identificar:
  - ventas aplicables al corte
  - productos no encontrados en inventario
  - posibles faltantes de stock

---

## Impacto del proyecto

Este sistema permitió transformar un proceso manual y no estructurado en un modelo de datos funcional con control operativo:

- Se estandarizaron atributos de producto mediante catálogos maestros
- Se habilitó la trazabilidad entre ventas e inventario mediante identificadores únicos
- Se automatizó el cálculo de stock, eliminando procesos manuales
- Se mejoró la calidad de los datos mediante validaciones y controles
- Se habilitó el análisis por atributos como tipo de tela, estampado, color y talla

---

## Enfoque técnico

Este proyecto aplica conceptos clave de análisis y gestión de datos:

- Modelado de datos
- Estandarización de información (Master Data)
- Automatización de reglas de negocio
- Control de calidad de datos
- Conciliación transaccional

---
