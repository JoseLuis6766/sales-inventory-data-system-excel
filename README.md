# Sistema de Ventas e Inventario en Excel

Sistema estructurado de ventas e inventario desarrollado en Excel para una microempresa, con catálogos maestros, generación automática de identificadores de producto, validación de datos y conciliación dinámica de stock.

## Resumen del proyecto

Este proyecto nació a partir de una necesidad real: la microempresa registraba ventas manualmente en libreta y con alta abstracción, lo que dificultaba el control de inventario, la trazabilidad de productos y el análisis de ventas.

A partir de ello, diseñé y construí desde cero un sistema estructurado en Excel, definiendo columnas, atributos, reglas de captura y lógica de automatización para transformar registros manuales no estandarizados en una base confiable y analizable.

## Problema de negocio

Antes del proyecto, la operación presentaba estos problemas:

- ventas registradas manualmente y sin estructura
- productos descritos de forma inconsistente
- dificultad para relacionar ventas con inventario
- ausencia de control dinámico de stock
- análisis limitado por falta de estandarización

## Solución desarrollada

Se implementó un sistema compuesto por tres componentes principales:

- **Catalogos**: datos maestros para estandarizar atributos
- **Ventas**: registro transaccional con ID automático y control de inventario
- **Inventario**: conteo base con cálculo dinámico de stock actual

## Arquitectura del sistema

```text
Catalogos (datos maestros)
        ↓
Ventas (transacciones)
        ↓
Inventario (conteo base + stock calculado)
