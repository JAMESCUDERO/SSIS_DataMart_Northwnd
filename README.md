# Data Mart Dimensional – Northwind

## Contexto del Proyecto
Este repositorio presenta el diseño e implementación de un **Data Mart Dimensional** construido a partir de la base de datos transaccional **Northwind**, con un enfoque **Data Engineering**.

El objetivo principal del proyecto es **diseñar y construir una capa analítica robusta**, aplicando principios de **Data Warehousing, ETL y modelado dimensional**, orientada a soportar cargas analíticas, reporting y consumo por herramientas de BI.

---

## Objetivos Técnicos
- Diseñar una arquitectura de **Data Mart desacoplada del sistema OLTP**
- Implementar procesos **ETL confiables y mantenibles**
- Transformar datos normalizados en un **modelo dimensional**
- Garantizar calidad, consistencia e integridad de los datos
- Preparar estructuras optimizadas para consultas analíticas
- Sentar bases para escalabilidad e incrementalidad

---

## Arquitectura de Datos
**OLTP → ETL → Data Mart Dimensional**

### 1. Sistema Origen (OLTP)
- Base de datos Northwind
- Modelo relacional normalizado
- Datos transaccionales (pedidos, clientes, productos, empleados)

### 2. Capa ETL
Responsable de la ingesta y transformación de datos:

- Extracción controlada desde tablas fuente
- Limpieza y estandarización de atributos
- Manejo de valores nulos y consistencia de tipos
- Generación de **claves sustitutas**
- Construcción de dimensiones conformadas
- Carga de tablas de hechos
- Diseño preparado para **cargas incrementales**

Los procesos ETL están implementados mediante **scripts SQL y/o paquetes SSIS**, siguiendo criterios de reutilización y mantenibilidad.

---

## Modelo Dimensional
El Data Mart está diseñado bajo un **Esquema en Estrella**, optimizado para workloads analíticos.

### Tabla de Hechos
- **FactVentas**
  - Nivel de granularidad: detalle de pedido
  - Métricas cuantitativas (importe, cantidad, descuentos)

### Tablas de Dimensiones
- **DimFecha**
- **DimCliente**
- **DimProducto**
- **DimEmpleado**
- **DimTransportista**

Características del modelo:
- Uso exclusivo de **surrogate keys**
- Atributos descriptivos desnormalizados
- Relaciones simples y eficientes
- Modelo preparado para BI y analítica avanzada

---

## Stack Tecnológico
- Base de datos relacional (SQL)
- Procesos ETL (SSIS / SQL)
- Modelado Dimensional
- Principios de Data Warehousing
- Control de versiones con GitHub

---

## 📌 Notas
Este Data Mart fue desarrollado con fines **demostrativos y profesionales**, utilizando Northwind como dataset de referencia.  
La arquitectura puede extenderse para:
- Implementar SCD Tipo 2
- Incorporar control de auditoría (metadata, logging)
- Integrarse con herramientas de BI o capas semánticas
- Migrar a entornos cloud o arquitecturas modernas

---
