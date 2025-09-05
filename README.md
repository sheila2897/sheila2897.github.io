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
Los datos procesados se almacenan en un Fabric Data Warehouse, diseñado para consolidar información y habilitar análisis avanzados de manera eficiente. Además, se integra Power Automate para ejecutar flujos automáticos que distribuyen reportes, envían alertas y activan aprobaciones tras la actualización de datos, asegurando trazabilidad y respuesta oportuna.

### 📊 Presentation Layer  
Los usuarios acceden a reportes dinámicos mediante **Power BI Service** y consultas en **Excel**, favoreciendo la toma de decisiones en tiempo real.

### 🔐 User Access  
Los permisos se administran con roles definidos en **Azure**, **Power Apps** y **Power BI**. Además, se envían notificaciones automáticas por correo tras cada actualización, asegurando trazabilidad y comunicación efectiva.

---

# Data Layer – Capa de Datos  
### Descripción de la Base de Datos – Proyecto Grupo AJE**

La base de datos para el sistema de gestión comercial del Grupo AJE ha sido diseñada para administrar de manera integral las operaciones de ventas, distribución y promociones de bebidas. Su modelo relacional permite consolidar información de clientes, trabajadores, productos y pedidos, con el fin de garantizar un control eficiente de la operación y habilitar análisis estratégicos en múltiples mercados.

La estructura se encuentra normalizada y distribuida en las siguientes tablas principales:

---

### 📦 Pedido  
Registra los pedidos realizados por los clientes, incluyendo la fecha, trabajador asociado, canal de venta, tipo de formato y las condiciones de entrega.

### 📑 Detalle_pedido  
Contiene la información específica de cada pedido, relacionando productos, cantidades, precios unitarios, descuentos y promociones aplicadas.

### 🧍 Cliente  
Almacena los datos de los clientes, considerando tipo de documento, identificación, nombre, contacto y canal de compra asociado. Facilita la segmentación comercial y la personalización de campañas.

### 🏪 Canal_cliente  
Clasifica el origen de los pedidos (tienda física, distribuidor, mayorista, autoservicio, e-commerce, etc.), permitiendo análisis comparativos entre canales de venta.

### 🥤 Producto  
Centraliza la información de cada producto, vinculando marca, categoría y formato. Incluye atributos como nombre, código, capacidad y precio base.

### 🏷️ Marca_producto  
Agrupa los productos según la marca (ejemplo: Big Cola, Cielo, Pulp, Sporade), lo que permite medir participación de mercado por línea de negocio.

### 📂 Categoría_producto  
Clasifica los productos en familias (gaseosas, agua, jugos, energizantes, etc.) para facilitar la gestión de portafolio y análisis de rentabilidad por categoría.

### 📦 Formato_producto  
Describe la presentación del producto (ejemplo: botella 500ml, pack 6 unidades, lata 355ml), clave para análisis logísticos y comerciales.

### 🧾 Tipo_formato  
Define y estandariza los tipos de formatos (individual, familiar, multipack), asegurando consistencia en la gestión de inventario y ventas.

### 💳 Tipo_pago  
Lista los métodos de pago disponibles (efectivo, tarjeta, transferencia, crédito comercial), estandarizando las transacciones y la conciliación contable.

### 🎟️ Promoción  
Gestiona las promociones vigentes, especificando condiciones, productos aplicables, descuentos y vigencia.

### 🏷️ Tipo_promoción  
Estandariza los tipos de promociones (descuentos directos, combos, 2x1, bonificaciones) para facilitar el análisis de efectividad comercial.

### 🧑‍💼 Trabajador  
Contiene la información del personal que participa en el proceso de ventas, incluyendo datos personales, cargo y sede asignada.

### 📌 Cargo_trabajador  
Clasifica los roles del personal (ejecutivo de ventas, supervisor, repartidor, administrativo), permitiendo evaluar desempeño por función.

### 📄 Tipo_documento  
Define los tipos de documentos aceptados (DNI, RUC, pasaporte, carnet de extranjería), estandarizando el registro de clientes y trabajadores.

### 📄 Tipo_documento  
La Base de datos en la nube donde se almacenan los datos procesados desde múltiples orígenes.

## Modelo de datos en Azure SQL
La Base de datos en la nube donde se almacenan los datos procesados desde múltiples orígenes.


---

# 🧩 Application Layer – Capa de Aplicación  
### Pantalla de Inicio / Bienvenida

### 🎯 Propósito

Servir como punto de entrada principal para los usuarios del sistema comercial del Grupo AJE, facilitando el acceso centralizado a todas las funcionalidades mediante una interfaz moderna, clara e intuitiva.

### 🧰 Funcionalidades

- **Presentación visual** con el logotipo corporativo del Grupo AJE y/o el nombre de la aplicación.
- **Menú central** con botones o íconos de navegación que dirigen a las pantallas principales del sistema:

  - 🛒 **Pedido**  
  - 🥤 **Producto**
  - 🧍 **Cliente**
  - 🏪 **Canal de Cliente**      
  - 🏷️ **Marca de Producto**  
  - 👔 **Vendedores**

- **Diseño responsive** y visualmente atractivo, adaptable a dispositivos móviles y escritorios.
- **Uso de íconos representativos** y colores corporativos que refuercen la identidad de la marca y mejoren la experiencia del usuario.
- **Navegación intuitiva y centralizada**, garantizando consistencia en todas las pantallas del sistema.

---

CAPTURA DE PANTALLA BIENVENIDA

## 🛒 Pantalla de Pedido

### 🎯 Propósito

Registrar y visualizar las ventas realizadas, incluyendo el detalle del proceso de **buyback** (canje de equipo), asegurando trazabilidad, eficiencia operativa y consistencia en la gestión comercial.

### Funcionalidades

## 🛒 Pantalla de Producto

### 🎯 Propósito

Registrar y visualizar las ventas realizadas, incluyendo el detalle del proceso de **buyback** (canje de equipo), asegurando trazabilidad, eficiencia operativa y consistencia en la gestión comercial.

### Funcionalidades

## 🛒 Pantalla de Cliente

### 🎯 Propósito

Registrar y visualizar las ventas realizadas, incluyendo el detalle del proceso de **buyback** (canje de equipo), asegurando trazabilidad, eficiencia operativa y consistencia en la gestión comercial.

### Funcionalidades

## 🛒 Pantalla de Canal de cliente

### 🎯 Propósito

Registrar y visualizar las ventas realizadas, incluyendo el detalle del proceso de **buyback** (canje de equipo), asegurando trazabilidad, eficiencia operativa y consistencia en la gestión comercial.

### Funcionalidades

## 🛒 Pantalla de Marca de producto

### 🎯 Propósito

Registrar y visualizar las ventas realizadas, incluyendo el detalle del proceso de **buyback** (canje de equipo), asegurando trazabilidad, eficiencia operativa y consistencia en la gestión comercial.

### Funcionalidades

## 🛒 Pantalla de Vendedores

### 🎯 Propósito

Registrar y visualizar las ventas realizadas, incluyendo el detalle del proceso de **buyback** (canje de equipo), asegurando trazabilidad, eficiencia operativa y consistencia en la gestión comercial.

### Funcionalidades

---

# ETL Layer (Capa de extracción, transformación y carga)
### Descripción General**

Este sistema implementa un flujo de datos automatizado y eficiente, integrando múltiples capas tecnológicas dentro del ecosistema Microsoft. El objetivo es garantizar la correcta ingesta, transformación y disponibilidad de la información para apoyar la gestión comercial, logística y la toma de decisiones estratégicas.

## 1️⃣ Origen de Datos

Los datos se generan principalmente desde Power Apps, donde los usuarios registran operaciones como:

- Ventas
- Pedidos
- Clientes
- Productos y marcas
- Trabajadores

📦 Esta información se almacena de forma estructurada en una base de datos relacional: Azure SQL Database.

---

## 2️⃣ Pipeline ETL – Microsoft Fabric Data Factory

La orquestación del proceso ETL (Extracción, Transformación y Carga) se gestiona mediante Microsoft Fabric Data Factory, con el objetivo de consolidar los datos en el Fabric Data Warehouse para análisis posterior.

### 🔁 Flujo del pipeline `pl_tablas`:

- **Extracción**  
  Obtiene datos desde las tablas transaccionales:
  - Pedido
  - Detalle de Pedido
  - Cliente
  - Producto
  - Promoción
  - Trabajador

- **Transformación**  
  Aplica procesos de:
  - Limpieza
  - Estandarización
  - Enriquecimiento  
  Utilizando Dataflows para asegurar calidad y consistencia.

- **Carga**  
  Inserta la información transformada en el Fabric Data Warehouse, optimizada para análisis comercial y estratégico.

---

## 3️⃣ Automatización con Notebooks en Python

Una vez finalizado el pipeline, se ejecuta un Notebook en Python que permite:

- 📊 Generar y enviar por correo electrónico un reporte diario con indicadores clave:
  - Volumen de pedidos
  - Clientes atendidos
  - Monto total vendido

- 📧 Notificar el estado del proceso ETL (ejecución exitosa o errores detectados)

- 🔍 Asegurar trazabilidad y transparencia en la actualización de datos

---

## 4️⃣ Seguridad y Ejecución Programada

El flujo completo se ejecuta de forma segura, programada y sin intervención manual, utilizando:

- 🔐 Credenciales protegidas
- ⏰ Reglas de ejecución automática

🕕 El pipeline `pl_tablas` corre todos los días a las 17:00 p.m., garantizando que los reportes y tableros en Power BI cuenten siempre con información actualizada.


Notebook: Envio1Final

<img width="1442" height="682" alt="image" src="https://github.com/user-attachments/assets/9fcd4d8e-4ec0-476a-b325-d53ec507cef3" />

<img width="1443" height="680" alt="image" src="https://github.com/user-attachments/assets/d9c35679-762e-4632-ae1f-597e2d846b41" />

<img width="1439" height="679" alt="image" src="https://github.com/user-attachments/assets/a4853cf9-7212-4418-a486-743d45a8ae30" />

<img width="1436" height="678" alt="image" src="https://github.com/user-attachments/assets/6d0006c6-b294-4b09-b97f-ae67c01930e6" />

Correo electrónico de notificación del éxito del pipeline

<img width="559" height="536" alt="image" src="https://github.com/user-attachments/assets/20c31dec-6d30-4a3e-8fa1-904d9676daae" />

---

## 🏢 Data Warehouse Layer – Capa de Almacén de Datos  

### 📌 Descripción General

La capa de Data Warehouse constituye el núcleo estructurado del sistema analítico de Grupo AJE. Aquí se concentran los datos procesados desde la capa ETL (gestionada con Pipelines y Dataflows en Microsoft Fabric). Una vez integrados, los datos se almacenan en un Fabric Data Warehouse, donde son normalizados, modelados y optimizados para su consulta, análisis y visualización en Power BI.

---

### ⚙️ Funcionalidades Clave

- **Modelado de Datos**  
  Se establecen relaciones entre tablas clave como `Pedidos`, `Clientes`, `Productos`, `Marcas`, `Promociones` y `Trabajadores`, asegurando una estructura sólida para el análisis empresarial.

- **Medidas Calculadas**  
  Se definen indicadores estratégicos como:
  - Volumen de pedidos  
  - Clientes atendidos  
  - Ingresos totales  
  - Impacto de promociones  
  - Margen de rentabilidad

- **Tabla Calendario**  
  Implementación de una dimensión temporal que habilita análisis detallados por:
  - Día  
  - Semana  
  - Mes  
  - Trimestre  
  - Año  
  Además de comparaciones dinámicas entre periodos.

- **Dimensiones de Negocio**  
  Se incorporan atributos adicionales como:
  - Categoría de producto  
  - Canal de cliente  
  - Tipo de pago  
  - Formato de producto  
  Lo que permite segmentar y analizar desde distintas perspectivas.

---

### 🔄 Flujos de Automatización con Power Automate

Para complementar esta capa, se han desarrollado flujos en Power Automate que permiten:
# PENDIENTE
- 📩 Enviar reportes automáticos con métricas clave (pedidos, clientes atendidos y ventas diarias) a responsables de negocio.
- ⏰ Programar alertas en caso de variaciones significativas en ventas o clientes.
- 🔗 Integrar notificaciones en Microsoft Teams o correo electrónico tras cada actualización del Data Warehouse.
- 🛠️ Reducir la intervención manual, asegurando procesos más rápidos, seguros y con menor riesgo de error.

---

### 📊 Beneficios

- **Escalabilidad**  
  Capacidad de crecer con el volumen de datos y expansión de nuevas líneas de negocio.

- **Automatización**  
  Procesos diarios gestionados sin intervención manual gracias a Power Automate y Fabric Pipelines.

- **Trazabilidad**  
  Registro claro de la procedencia y transformación de datos.

- **Soporte a BI**  
  Base confiable para dashboards interactivos y reportes distribuidos en Power BI.

---

### 🖥️ Vista en Microsoft Fabric

<img width="1439" height="676" alt="image" src="https://github.com/user-attachments/assets/9740799b-8681-4b44-a951-c0bfdde044c0" />



---

> 💡 Este diseño permite escalar la solución, mantener la integridad de los datos y ofrecer insights confiables para la toma de decisiones estratégicas en Grupo AJE.




















