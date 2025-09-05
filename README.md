# 🌐 Grupo AJE  
**Building Cloud Business Applications for Grupo AJE**

---

## 📌 Descripción General del Proyecto

Este proyecto busca implementar una arquitectura moderna de datos para el Grupo AJE, con el fin de centralizar y optimizar la información proveniente de sus operaciones de ventas, distribución y producción en los distintos países donde opera.

El diseño de esta arquitectura tiene como finalidad integrar en un único ecosistema los datos de negocio, mejorar su transformación y calidad con flujos ETL escalables, y habilitar su consulta de manera segura y flexible a través de soluciones como Power BI, Excel y PowerApps.

Gracias al uso de tecnologías en la nube como Azure SQL y Microsoft Fabric, el Grupo AJE contará con una solución moderna y flexible que facilita la integración de datos, potencia el análisis en profundidad y soporta la toma de decisiones en tiempo real.

---

## 🎯 Objetivos Principales

- Unificar la información empresarial proveniente de múltiples fuentes (ERP, CRM, SQL, Excel, entre otros).
- Automatizar los procesos de integración y transformación de datos con Microsoft Fabric, asegurando calidad y consistencia.
- Incorporar PowerApps como capa de captura, actualización y gestión operativa de la información.
- Diseñar y consolidar un Data Warehouse corporativo que respalde la generación de reportes confiables y estandarizados.
- Implementar Power Automate para la distribución automática de reportes, notificaciones y flujos de aprobación relacionados con la gestión de datos.
- Optimizar el análisis de negocio mediante reportes en Power BI.

---

## 🧰 Solución Tecnológica

Este proyecto implementa una solución de negocio moderna utilizando herramientas de Microsoft Cloud:

| Tecnología        | Función Principal                                                                 |
|------------------|------------------------------------------------------------------------------------|
| 🧱 Microsoft Fabric | Integración, transformación y consolidación de datos en un entorno centralizado. |
| ⚙️ Azure SQL        | Almacenamiento estructurado, confiable y de alto rendimiento.                    |
| ⚡ Power Apps       | Desarrollo low-code para optimizar procesos operativos.                          |
| 📊 Power BI         | Análisis interactivo y visualizaciones en tiempo real.                           |
| 🔄 Power Automate   | Automatización de reportes, aprobaciones y alertas.                              |

---

## 🚀 Diagrama de Arquitectura del Proyecto

<img width="1325" height="616" alt="image" src="https://github.com/user-attachments/assets/964c309a-0b82-4840-aefe-24d5a340fa73" />

### 📁 Data Sources  
La información se origina en archivos Excel y en un sistema de escritorio con base de datos propia. Estos insumos se incorporan al ecosistema mediante procesos manuales o parcialmente automatizados.

### 🗄️ Data Layer  
Toda la información se consolida en **Azure SQL**, funcionando como repositorio relacional en la nube. Además, se registran datos capturados desde aplicaciones desarrolladas en **Power Apps**.

### 🧩 Application Layer  
La interacción con los usuarios se gestiona a través de **Power Apps**, que ofrece una interfaz intuitiva para la carga, modificación y consulta de datos, integrada de forma nativa con Azure.

### 🔄 ETL Layer  
Con **Microsoft Fabric** (Dataflows y Pipelines) se automatiza la ingesta y transformación de datos hacia el Data Warehouse. Asimismo, se emplean **Notebooks en Python** para ejecutar validaciones y generar notificaciones por correo electrónico.

### 🧱 Data Warehouse Layer  
Los datos procesados se almacenan en un **Fabric Data Warehouse**, diseñado para consolidar información y habilitar análisis avanzados de manera eficiente.

### 📊 Presentation Layer  
Los usuarios acceden a reportes dinámicos mediante **Power BI Service** y consultas en **Excel**, favoreciendo la toma de decisiones en tiempo real.

### 🔐 User Access  
Los permisos se administran con roles definidos en **Azure**, **Power Apps** y **Power BI**. Además, se envían notificaciones automáticas por correo tras cada actualización, asegurando trazabilidad y comunicación efectiva.

---

## 🗂️ Estructura del Repositorio











