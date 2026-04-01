# Sistema de Ventas e Inventario en Excel | Análisis de Demanda Comercial con Power BI

Sistema estructurado de ventas e inventario desarrollado en Excel para una microempresa, complementado con un análisis de demanda comercial en Power BI. El proyecto integra estandarización de datos, generación automática de identificadores de producto, validación de captura y conciliación dinámica de stock, con el fin de construir una base confiable para la toma de decisiones y el análisis de ventas.

---

## Resumen del proyecto

Este proyecto surge de una necesidad real: la microempresa registraba sus ventas manualmente, con descripciones ambiguas, inconsistentes y poco estructuradas, lo que dificultaba el control de inventario, la trazabilidad de productos y el análisis de productos y el análisis comercial.

Para resolverlo, diseñé e implementé desde cero un sistema estructurado en Excel, definiendo la arquitectura del archivo, los atributos del producto, las reglas de captura y la lógica de automatización. Posteriormente, utilicé la hoja **Ventas** como fuente para desarrollar un primer análisis de negocio en **Power BI**, enfocado en entender la **demanda comercial** del negocio.

El resultado fue una solución que no solo mejora la operación diaria, sino que también habilita análisis confiables sobre qué productos generan mayor demanda, qué atributos concentran más ventas y cómo cambia el comportamiento comercial en el tiempo.

---

## Contexto del negocio

La microempresa necesitaba una forma más confiable de registrar sus ventas e inventario. Antes del proyecto, la operación dependía de capturas manuales sin estandarización, lo que generaba problemas para responder preguntas clave como:

- ¿Qué productos se venden más?
- ¿Qué marcas sostienen el negocio?
- ¿Qué tallas tienen mayor demanda?
- ¿Cómo cambian las ventas mes a mes?
- ¿Cómo relacionar correctamente ventas e inventario?

Sin una estructura consistente, cualquier análisis estaba limitado por la baja calidad de los datos.

---

## Problema de negocio

Antes del proyecto, la operación presentaba las siguientes limitaciones:

- Ventas registradas manualmente y sin estructura
- Productos descritos de forma inconsistente
- Dificultad para relacionar ventas con inventario
- Ausencia de control dinámico de stock
- Limitada capacidad de análisis por falta de estandarización

---

## Objetivo del proyecto

Transformar un registro manual y ambiguo en un sistema estructurado y analizable que permitiera:

- estandarizar la captura de ventas,
- garantizar trazabilidad entre ventas e inventario,
- automatizar reglas de negocio,
- mejorar la calidad de los datos,
- y habilitar análisis comerciales útiles para la toma de decisiones.

---

## Solución desarrollada

Diseñé e implementé una solución basada en tres componentes principales:

- **Catálogos**: estructura de datos maestros para estandarizar atributos del producto
- **Ventas**: registro transaccional con generación automática de identificador único (`ID_Camisa`)
- **Inventario**: registro base con cálculo dinámico del stock actual

---

## Arquitectura del sistema

El sistema fue diseñado en tres capas funcionales:

- **Catálogos** → concentran los datos maestros y estandarizan los atributos del producto
- **Ventas** → registran las transacciones y generan automáticamente el `ID_Camisa`
- **Inventario** → conserva el conteo base y calcula el stock actual con base en las ventas posteriores al corte

---

## Automatización implementada

Para convertir un registro manual en un sistema funcional de control, implementé las siguientes automatizaciones:

- Generación automática de `ID_Camisa` a partir de atributos del producto:
  - marca
  - tipo de cuello
  - manga
  - estampado
  - color
  - talla
- Validación de datos mediante catálogos maestros para asegurar consistencia en la captura
- Cálculo dinámico de `Stock_Actual_Calculado` basado en ventas posteriores al último corte de inventario
- Implementación de la columna `Control_Inventario` para identificar:
  - ventas aplicables al corte
  - productos no encontrados en inventario
  - posibles faltantes de stock

---

## Antes y después de la normalización de datos

### Antes de la normalización
<img width="899" height="347" alt="image" src="https://github.com/user-attachments/assets/7ce582e5-aa80-4fab-82a4-1aaa3159c132" />


### Después de la normalización
<img width="1299" height="182" alt="image" src="https://github.com/user-attachments/assets/fd6b2000-f673-456b-aff2-4d92de31c35d" />


---

## Fuente de datos para el análisis en Power BI

Para el primer análisis exploratorio y de negocio en Power BI, utilicé exclusivamente la hoja **Ventas** del archivo Excel estructurado.

### Variables disponibles en la hoja Ventas

- `ID_Venta`
- `Marca`
- `Tipo de cuello`
- `Manga`
- `Estampado`
- `Color`
- `Talla`
- `Cantidad`
- `Fecha`
- `Precio`
- `ID_camisa`
- `Tipo de tela`
- `Control_Inventario`

Estas variables permitieron analizar la demanda desde una perspectiva comercial, observando tanto el comportamiento temporal como la concentración de ventas por atributos del producto.

---

## Caso de estudio: Análisis de Demanda Comercial

el primer análisis desarrollado en Power BI se planteó a partir de la siguiente tarea de negocio:

> **Identificar qué productos y atributos concentran la demanda comercial del negocio y cómo cambia esa demanda en el tiempo, con el fin de apoyar decisiones de surtido y priorización comercial.**

---

## Pregunta de negocio principal

La primera pregunta estratégica que guié en el análisis fue:

> **¿Qué productos y atributos concentran la demanda, y cómo evoluciona esa demanda en el tiempo?**

A partir de ella se derivaron preguntas complementarias como:

- ¿Qué marcas generan más ingresos?
- ¿Qué tallas tienen mayor salida?
- ¿Cómo se comportan los ingresos por mes?
- ¿Qué combinaciones de marca y talla concentran mayor volumen de ventas?

---

## Preparación de datos para Power BI

Antes del análisis, la hoja **Ventas** fue revisada y depurada para asegurar consistencia en el modelo:

- validación de nombres de columnas,
- revisión de tipos de datos,
- limpieza de encabezados,
- control de filas vacías o registros no útiles,
- preparación de campos necesarios para el análisis temporal y comercial.

Posteriormente, se construyeron medidas y campos calculados en Power BI para analizar el negocio desde una perspectiva más ejecutiva.

### Medidas principales creadas

- **Ingresos Totales**
- **Unidades Vendidas**
- **Ventas Registradas**
- **Productos Distintos**
- **Precio Promedio por Unidad**

### Campo calculado adicional

- **Inicio de Mes** para analizar tendencia temporal mensual

---

## Dashboard 1: Análisis de Demanda Comercial

El primer dashboard fue diseñado para responder cuatro preguntas clave:

1. ¿Cuánto se ha vendido?
2. ¿Cómo evolucionan los ingresos en el tiempo?
3. ¿Qué marcas concentran la demanda?
4. ¿Qué tallas y combinaciones de producto tienen mayor salida?

### Visualizaciones incluidas

- **Tarjetas KPI**
  - Ingresos Totales
  - Unidades Vendidas
  - Ventas Registradas
  - Productos Distintos

- **Gráfico de línea**
  - Tendencia mensual de ingresos

- **Gráfico de barras**
  - Ingresos por marca

- **Gráfico de columnas**
  - Unidades vendidas por talla

- **Matriz con formato condicional**
  - Demanda por marca y talla

---

## Justificación de las visualizaciones

Las visualizaciones fueron seleccionadas con base en el tipo de pregunta de negocio y el patrón de datos que se quería comunicar:

- **Gráfico de línea**: para observar cambios y tendencias en el tiempo
- **Gráfico de barras**: para comparar el desempeño entre marcas
- **Gráfico de columnas**: para analizar la demanda por talla
- **Matriz con formato condicional**: para identificar concentración de demanda en combinaciones específicas de marca y talla
- **Tarjetas KPI**: para ofrecer una vista ejecutiva rápida del desempeño comercial

Este enfoque permitió construir una página clara y funcional, priorizando el entendimiento del negocio antes que la complejidad visual.

---

## Dashboard en Power BI

### Vista general del dashboard
<img width="1216" height="735" alt="image" src="https://github.com/user-attachments/assets/90ace976-d4d8-4e16-bac4-968cc09b8a4a" />


### KPI principales
<img width="294" height="723" alt="image" src="https://github.com/user-attachments/assets/8b346af6-c64a-4d9e-85d5-cc8fcbaa3e59" />


### Tendencia mensual de ingresos
<img width="402" height="278" alt="image" src="https://github.com/user-attachments/assets/92986c6c-2c56-42e5-8aba-dcc4ec19cfc4" />


### Ingresos por marca
<img width="393" height="380" alt="image" src="https://github.com/user-attachments/assets/c5c1e2f4-a2c6-4a4b-8a4b-a0366a09379a" />


### Unidades vendidas por talla
<img width="401" height="282" alt="image" src="https://github.com/user-attachments/assets/4e860f6b-1c80-4bae-b912-6cc4b693de2c" />


### Demanda por marca y talla
<img width="393" height="379" alt="image" src="https://github.com/user-attachments/assets/f0a4bcef-90c1-4697-92b5-f5f29169d951" />


---

## Hallazgos iniciales del análisis

A partir del primer dashboard, se identificaron patrones relevantes en la demanda comercial:

- La demanda se concentra en un grupo reducido de marcas, lo que sugiere dependencia comercial en ciertos productos
- Algunas tallas presentan una salida claramente superior a otras, lo que puede ayudar a priorizar reposición
- La tendencia mensual de ingresos muestra variaciones que podrían estar relacionadas con estacionalidad, disponibilidad o cambios en la operación
- El cruce entre **marca** y **talla** permite identificar combinaciones específicas que concentran gran parte del volumen vendido

Estos hallazgos convierten una base operativa en una herramienta analítica útil para decisiones comerciales.

---

## Impacto del proyecto

Este proyecto permitió transformar un proceso manual y no estructurado en un modelo de datos funcional con utilidad operativa y analítica:

- Se estandarizaron atributos de producto mediante catálogos maestros
- Se habilitó la trazabilidad entre ventas e inventario mediante identificadores únicos
- Se automatizó el cálculo de stock, reduciendo dependencia de procesos manuales
- Se mejoró la calidad de los datos mediante validaciones y controles
- Se habilitó el análisis por atributos como marca, talla, color, tipo de tela y estampado
- Se construyó un primer dashboard en Power BI para apoyar decisiones de surtido y enfoque comercial

---

## Enfoque técnico

Este proyecto aplica conceptos clave de análisis y gestión de datos:

- Modelado de datos
- Estandarización de información (Master Data)
- Diseño de reglas de negocio
- Automatización en Excel
- Control de calidad de datos
- Conciliación transaccional
- Análisis exploratorio de datos
- Visualización de datos en Power BI
- Storytelling orientado a negocio

---

## Herramientas utilizadas

- **Excel**
  - validación de datos
  - fórmulas
  - estructura de catálogos
  - automatización del identificador de producto
  - conciliación de inventario

- **Power BI**
  - modelado básico
  - medidas DAX
  - análisis temporal
  - dashboard de demanda comercial

