# 🌐 Grupo AJE  
#### Building Cloud Business Applications for Grupo AJE

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

<img width="1174" height="512" alt="image" src="https://github.com/user-attachments/assets/e5bfd148-6504-45c6-801d-1bb680f1c29e" />

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
Contiene la información específica de cada pedido, relacionando productos, cantidades y precios unitarios.

### 🧍 Cliente  
Almacena los datos de los clientes, considerando tipo de documento, identificación, nombre, contacto y canal de compra asociado. Facilita la segmentación comercial y la personalización de campañas.

### 🏪 Canal_cliente  
Clasifica el origen de los pedidos (Tradicional,Moderno, Horeca,Mayorista e Institucional), permitiendo análisis comparativos entre canales de venta.

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

<img width="1380" height="788" alt="image" src="https://github.com/user-attachments/assets/49a33939-abd3-4d5c-a686-2e499240d4b0" />

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
  - 🏷️ **Marca**  
  - 👔 **Vendedores**

- **Diseño** y visualmente atractivo, adaptable a dispositivos móviles y escritorios.
- **Uso de íconos representativos** y colores corporativos que refuercen la identidad de la marca y mejoren la experiencia del usuario.
- **Navegación intuitiva y centralizada**, garantizando consistencia en todas las pantallas del sistema.

<img width="900" height="447" alt="image" src="https://github.com/user-attachments/assets/e683f917-abfe-4d30-b588-635d84844726" />

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
- Vendedores

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
  - Ticket promedio

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

<img width="1340" height="597" alt="image" src="https://github.com/user-attachments/assets/2f951b64-acb1-4933-a13d-0e4566b127d6" />

<img width="1450" height="672" alt="image" src="https://github.com/user-attachments/assets/63f19f4f-82ad-4807-a9d5-ed1de5eb04e3" />

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
  - 10CAIDADELMES  
  - 10CAIDAMESTOP5
  - 10TEXTO_CAIDAMESTOP5
  - 8RANK_AUMENTO_MARCA
  - 8RANK_CAIDA_MARCA
  - 8TOP3_AUMENTO_MARCAS
  - 8TOP3_CAIDA_MARCAS
  - Impacto Marginal
  - KPI %
  - MAXKPI
  - MetaObjetiva
  - MINKPI
  - ParticipacionCanal
  - TEXTO_TOP3_MARCAS
  - UMBRALAMARIL
  - UMBRALROJO
  - VARIACION MENSUAL
  - Ventas
  - Ventas Día
  - VENTAS MES PASADO
  - Ventas Proyectadas
  - VentasBebidas
  - Ventas proyectadas 1%
  - Ventasproyectadas2%

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

### 📩 Enviar el Informe Mensual de KPI 2025 a responsables de negocio.

<img width="1435" height="681" alt="image" src="https://github.com/user-attachments/assets/ddcd6894-acbe-448a-85a2-3d176263b09d" />

NotificaciónCorreo

<img width="1430" height="645" alt="image" src="https://github.com/user-attachments/assets/a5192708-f64a-412a-8a3d-5024e74afeff" />

### 📩 Enviar el informe de Ventas Abril y Mayo 2025 – Marca Sporade a responsable de negocio.

<img width="1439" height="684" alt="image" src="https://github.com/user-attachments/assets/77b55da5-4cce-47cd-afc5-31304a5652bf" />

NotificaciónCorreo

<img width="1429" height="688" alt="image" src="https://github.com/user-attachments/assets/96d9c977-ce23-4e1a-9245-a1e91a4abfb5" />

### 📩 Enviar Informe de Productos Menos Vendidos - Abril y Mayo 2025 a responsable de negocio

<img width="1450" height="689" alt="image" src="https://github.com/user-attachments/assets/f386129c-0919-4359-9566-d2e98eb38121" />

NotificaciónCorreo

<img width="1424" height="686" alt="image" src="https://github.com/user-attachments/assets/72b5628e-e618-4935-a3e4-11366ee90922" />

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

**Inicio**
<img width="820" height="459" alt="image" src="https://github.com/user-attachments/assets/cee73324-56a3-4eb8-868d-7e840fd0d24e" />


**Caso de negocio**
<img width="819" height="463" alt="image" src="https://github.com/user-attachments/assets/fdd8510f-7d9a-481b-8d14-9645a3375253" />


**Indicadores**
<img width="819" height="456" alt="image" src="https://github.com/user-attachments/assets/5d88f770-b512-42aa-b041-f1974b88e90a" />


**Dashboard**
<img width="1062" height="561" alt="image" src="https://github.com/user-attachments/assets/9659b4dd-8686-4c29-bc95-3a85693eac2c" />


**Reporte**
<img width="972" height="490" alt="image" src="https://github.com/user-attachments/assets/8955bc1b-8d50-4c65-9704-350f0cb19f4e" />


**Informe 1**
<img width="818" height="459" alt="image" src="https://github.com/user-attachments/assets/1ebe5e45-1da8-42bb-a84a-9d98b484d5e0" />


**Informe 2**
<img width="820" height="460" alt="image" src="https://github.com/user-attachments/assets/75cb6cf3-2158-4f39-88bb-b63ffc656ccc" />


**Informe 3**
<img width="811" height="456" alt="image" src="https://github.com/user-attachments/assets/c28f025d-1e98-426d-8ce5-c31e64751951" />


**Informe 4**
<img width="1079" height="590" alt="image" src="https://github.com/user-attachments/assets/1b0ef139-d9f7-4449-b6cb-29e6111f5583" />


**Informe 5**
<img width="818" height="458" alt="image" src="https://github.com/user-attachments/assets/53a15edb-39f5-4b13-a1fa-cd5c43eb18cc" />


**Informe 6**
<img width="820" height="463" alt="image" src="https://github.com/user-attachments/assets/ec5c31a6-8399-4df3-a688-de263ee35fff" />


**Informe 7**
<img width="817" height="456" alt="image" src="https://github.com/user-attachments/assets/817cbc20-10b1-4533-a73e-e5321fcebd01" />


**Informe 8**
<img width="819" height="462" alt="image" src="https://github.com/user-attachments/assets/e26d2558-4fe1-4ab9-9725-2534ff27e27e" />


**Informe 9**
<img width="813" height="463" alt="image" src="https://github.com/user-attachments/assets/ecbc44c4-c654-4cff-9e7c-710e3b02bb87" />


**Informe 10**
<img width="1082" height="599" alt="image" src="https://github.com/user-attachments/assets/d211a3d1-2cde-49c6-be42-e7f3dddfaffa" />


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





















