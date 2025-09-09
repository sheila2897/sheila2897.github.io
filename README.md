# 🌐 Grupo AJE  
**Building Cloud Business Applications for Grupo AJE**

---

## 📌 Descripción General del Proyecto

Este proyecto busca implementar una arquitectura moderna de datos para el Grupo AJE, con el fin de centralizar y optimizar la información proveniente de sus operaciones de ventas, distribución y producción en los distintos países donde opera.

El diseño de esta arquitectura tiene como finalidad integrar en un único ecosistema los datos de negocio, mejorar su transformación y calidad con flujos ETL escalables, y habilitar su consulta de manera segura y flexible a través de soluciones como Power BI, Excel y PowerApps.

Gracias al uso de tecnologías en la nube como Azure SQL y Microsoft Fabric, el Grupo AJE contará con una solución moderna y flexible que facilita la integración de datos, potencia el análisis en profundidad y soporta la toma de decisiones en tiempo real.

---

## 🎯 Objetivos Principales

- Unificar la información empresarial proveniente de múltiples fuentes.
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
Toda la información se consolida en Azure SQL, funcionando como repositorio relacional en la nube. Además, se registran datos capturados desde aplicaciones desarrolladas en Power Apps.

### 🧩 Application Layer  
La interacción con los usuarios se gestiona a través de Power Apps, que ofrece una interfaz intuitiva para la carga, modificación y consulta de datos, integrada de forma nativa con Azure.

### 🔄 ETL Layer  
Con Microsoft Fabric (Dataflows y Pipelines) se automatiza la ingesta y transformación de datos hacia el Data Warehouse. Asimismo, se emplean Notebooks en Python para ejecutar validaciones y generar notificaciones por correo electrónico.

### 🧱 Data Warehouse Layer  
Los datos procesados se almacenan en un Fabric Data Warehouse, diseñado para consolidar información y habilitar análisis avanzados de manera eficiente. Además, se integra Power Automate para ejecutar flujos automáticos que distribuyen reportes, envían alertas y activan aprobaciones tras la actualización de datos, asegurando trazabilidad y respuesta oportuna.

### 📊 Presentation Layer  
Los usuarios acceden a reportes dinámicos mediante Power BI Service, favoreciendo la toma de decisiones en tiempo real.

### 🔐 User Access  
Los permisos se administran con roles definidos en Azure, Power Apps y Power BI. Además, se envían notificaciones automáticas por correo tras cada actualización, asegurando trazabilidad y comunicación efectiva.

---

# Data Layer – Capa de Datos  
### Descripción de la Base de Datos – Proyecto Grupo AJE

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
### Descripción General

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

<img width="2892" height="1358" alt="image" src="https://github.com/user-attachments/assets/b7fbce48-cfee-425b-9a6c-bb65f3517c98" />

<img width="2866" height="1366" alt="image" src="https://github.com/user-attachments/assets/3c665aaa-2b1e-4553-b766-ee12bce96b35" />

Notebook: Envio1Final

<img width="1429" height="683" alt="image" src="https://github.com/user-attachments/assets/ac5b5d57-cd41-465e-9a27-f3c69014f0d9" />

<img width="1426" height="680" alt="image" src="https://github.com/user-attachments/assets/df8f1c27-80bd-497b-90cd-88807f176ef9" />

<img width="1446" height="681" alt="image" src="https://github.com/user-attachments/assets/1894d7c5-fce3-42ae-9cce-d8edfe6db07d" />

<img width="1428" height="679" alt="image" src="https://github.com/user-attachments/assets/df7a46a3-02ce-43ec-ae17-d7f7d2a324ed" />

<img width="1424" height="673" alt="image" src="https://github.com/user-attachments/assets/ac63bfca-9fb9-446b-9c31-6fc6e2d39721" />

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

### 📩 Enviar el Informe Mensual de KPI a responsables de negocio.

<img width="1435" height="681" alt="image" src="https://github.com/user-attachments/assets/ddcd6894-acbe-448a-85a2-3d176263b09d" />

NotificaciónCorreo

<img width="1433" height="695" alt="image" src="https://github.com/user-attachments/assets/541bfbf0-b53a-4c39-9719-a2b4d9ad8fe3" />

### 📩 Enviar el Informe de Ventas – Marca Sporade a responsable de negocio.

<img width="1439" height="684" alt="image" src="https://github.com/user-attachments/assets/77b55da5-4cce-47cd-afc5-31304a5652bf" />

NotificaciónCorreo

<img width="2866" height="1384" alt="image" src="https://github.com/user-attachments/assets/5b4b60e0-bd67-49e0-b2ca-8296e673203b" />

### 📩 Enviar el Informe de Productos Menos Vendidos a responsable de negocio

<img width="1450" height="689" alt="image" src="https://github.com/user-attachments/assets/f386129c-0919-4359-9566-d2e98eb38121" />

NotificaciónCorreo

<img width="1432" height="689" alt="image" src="https://github.com/user-attachments/assets/3eae8869-5068-4c1c-a061-78df3dd75355" />

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

## 🖥️ Vista en Microsoft Fabric

<img width="1439" height="676" alt="image" src="https://github.com/user-attachments/assets/9740799b-8681-4b44-a951-c0bfdde044c0" />

## Flujos en Power Automate

PENDIENTE

---

## 📊 Capa de Presentación – Presentation Layer  

### 🌐 Descripción General

La capa de presentación, construida sobre Power BI, es el punto de acceso para los usuarios del negocio a toda la información procesada en el ecosistema de datos de Grupo AJE. Su objetivo es simplificar la complejidad de los datos y ofrecer una experiencia visual que apoye tanto el análisis operativo como las decisiones estratégicas.

---

### 🔎 Elementos Clave

- **Visualización Estratégica**  
  Los reportes están diseñados para mostrar de manera clara la evolución de:
  - Ventas  
  - Clientes  
  - Promociones  
  - Desempeño por marca  
  Facilitando el monitoreo de la operación y del mercado.

- **Exploración Flexible**  
  Segmentadores interactivos permiten filtrar la información por:
  - Periodos de tiempo  
  - Categorías de producto  
  - Tipo de cliente  
  - Canal de venta  
  Adaptando el análisis a diferentes necesidades.

- **Indicadores Clave**  
  Métricas relevantes incluidas:
  - Volumen de pedidos  
  - Ingresos acumulados   
  - Participación de mercado  
  
- **Automatización del Refresh**  
  La actualización de los datos se ejecuta mediante:
  - Pipelines en Microsoft Fabric  
  - Flujos en Power Automate  
  Garantizando información confiable y siempre al día.

---

### 📈 Impacto para el Negocio

- **Decisiones Basadas en Evidencia**  
  Acceso inmediato a métricas críticas para la toma de decisiones.

- **Detección de Patrones**  
  Identificación de oportunidades de mercado a partir del comportamiento del cliente.

- **Gestión Ejecutiva Potenciada**  
  Reportes diseñados para directores, gerentes y responsables comerciales.

- **Eficiencia Operativa**  
  Reducción de tiempos en la elaboración manual de reportes.

---

### 📑 Reportes en Power BI

**Informe 1**
**Informe 2**
**Informe 3**
**Informe 4**
**Informe 5**
**Informe 6**
**Informe 7**
**Informe 8**
**Informe 9**
**Informe 10**

---

## ✅ Conclusión

La implementación de esta arquitectura de datos marca un paso clave en la evolución digital de Grupo AJE, integrando el ecosistema Microsoft para responder a las exigencias de un mercado dinámico y altamente competitivo.

Este proyecto no solo asegura una gestión eficiente y automatizada de la información, sino que convierte los datos en un activo estratégico que impulsa la innovación, la agilidad y la capacidad de respuesta de la organización.

---

### 🌟 Logros Alcanzados

- **Unificación de la Información**  
  Consolidación de datos de pedidos, clientes, marcas y promociones en una única fuente confiable.

- **Automatización de Procesos Críticos**  
  Uso de Microsoft Fabric y Power Automate para reducir la intervención manual y optimizar los tiempos de procesamiento.

- **Información Oportuna y Accesible**  
  Reportes ejecutivos y dashboards dinámicos en Power BI, con datos siempre actualizados.

- **Experiencia Ágil para Usuarios**  
  Ingreso y actualización de información mediante Power Apps, simplificando las operaciones de los equipos internos.

- **Seguridad y Control**  
  Gestión de accesos basada en roles, garantizando trazabilidad y protección de los datos sensibles.

---

### 🚀 Valor Estratégico

Con esta solución, Grupo AJE fortalece su capacidad para:

- Tomar decisiones basadas en evidencia  
- Identificar nuevas oportunidades de mercado  
- Optimizar la eficiencia operativa  

Más que un sistema tecnológico, representa una plataforma de inteligencia empresarial que potencia la competitividad y acompaña el crecimiento de la compañía en el corto, mediano y largo plazo.





















