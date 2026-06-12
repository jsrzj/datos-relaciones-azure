# Introducción

Azure admite varios servicios de base de datos, lo que permite ejecutar en la nube diversos sistemas de administración de bases de datos relacionales conocidos, como SQL Server, PostgreSQL y MySQL.

La mayoría de los servicios de base de datos de Azure están totalmente administrados, lo que reduce el tiempo dedicado a tareas de administración. Además, ofrecen rendimiento de nivel empresarial, alta disponibilidad integrada, escalado rápido y distribución global.

Los desarrolladores pueden aprovechar:

- Seguridad integrada con supervisión automática.
- Detección automática de amenazas.
- Ajuste automático para mejorar el rendimiento.

Además, la disponibilidad está garantizada.

## Objetivo del módulo

Explorar las opciones disponibles para los servicios de bases de datos relacionales en Azure.

---

# Descripción de los servicios y las capacidades de Azure SQL

Azure SQL es un término colectivo que hace referencia a una familia de servicios de bases de datos basados en Microsoft SQL Server en Azure.

## Servicios de Azure SQL

### SQL Server en Azure Virtual Machines (VMs)

Máquina virtual que se ejecuta en Azure con SQL Server instalado.

**Características:**

- Solución de infraestructura como servicio (IaaS).
- Virtualiza la infraestructura de hardware para proceso, almacenamiento y redes en Azure.
- Permite un mayor control sobre el sistema operativo y la configuración del servidor.
- Excelente opción para migraciones *lift-and-shift* de entornos locales de SQL Server a la nube.

### Azure SQL Managed Instance

Opción de plataforma como servicio (PaaS) que proporciona una compatibilidad casi completa con instancias locales de SQL Server.

**Características:**

- Abstrae el hardware y el sistema operativo subyacentes.
- Administración automatizada de actualizaciones de software.
- Copias de seguridad automáticas.
- Tareas de mantenimiento automatizadas.
- Reduce la carga administrativa asociada a la gestión de una instancia de base de datos.

### Azure SQL Database

Servicio de base de datos PaaS totalmente administrado y altamente escalable diseñado para la nube.

**Características:**

- Incluye las capacidades principales de SQL Server local.
- Alta escalabilidad.
- Administración completamente gestionada.
- Ideal para desarrollar aplicaciones nativas de la nube.

## Comparación de los servicios de Azure SQL


| Característica | SQL Server en Azure Virtual Machines | Azure SQL Managed Instance | Azure SQL Database |
|---------------|--------------------------------------|----------------------------|-------------------|
| **Tipo de servicio en la nube** | IaaS | PaaS (Plataforma como Servicio) | PaaS (Plataforma como Servicio) |
| **Compatibilidad con SQL Server** | Totalmente compatible con instalaciones físicas y virtualizadas locales. Las aplicaciones y bases de datos se pueden migrar fácilmente mediante el enfoque *lift-and-shift* sin realizar cambios. | Casi completamente compatible con SQL Server. La mayoría de las bases de datos locales se pueden migrar con cambios mínimos de código mediante Azure Database Migration Service. | Admite la mayoría de las funcionalidades básicas de SQL Server. Algunas características de las que dependa una aplicación local podrían no estar disponibles. |
| **Arquitectura** | Las instancias de SQL Server se instalan en una máquina virtual. Cada instancia puede admitir varias bases de datos. | Cada instancia administrada puede admitir varias bases de datos. Los grupos de instancias permiten compartir recursos de forma eficiente entre instancias más pequeñas. | Puede aprovisionar una base de datos única en un servidor lógico administrado o utilizar grupos elásticos para compartir recursos entre varias bases de datos y aprovechar la escalabilidad bajo demanda. |
| **Disponibilidad** | 99,99 % | 99,99 % | 99,995 % |
| **Administración** | Debe administrar todos los aspectos del servidor, incluidos el sistema operativo, SQL Server, la configuración, las copias de seguridad y otras tareas de mantenimiento. | Actualizaciones, copias de seguridad y recuperación totalmente automatizadas. | Actualizaciones, copias de seguridad y recuperación totalmente automatizadas. |
| **Casos de uso** | Ideal para migrar o ampliar una solución de SQL Server local conservando el control total sobre la configuración del servidor y la base de datos. | Adecuado para la mayoría de los escenarios de migración a la nube, especialmente cuando se requieren cambios mínimos en las aplicaciones existentes. | Recomendado para nuevas soluciones en la nube o para migrar aplicaciones con dependencias mínimas de instancia. |

## SQL Server en Azure Virtual Machines

SQL Server en Azure Virtual Machines permite usar versiones completas de SQL Server en la nube sin necesidad de administrar hardware local. Representa un enfoque de Infraestructura como Servicio (IaaS).

### Características principales

- Replica el entorno de SQL Server que se ejecuta en hardware local.
- Facilita migraciones mediante el enfoque *lift-and-shift*.
- Permite acceso a funcionalidades del sistema operativo no disponibles en soluciones PaaS.
- Adecuado para entornos híbridos.
- Proporciona control administrativo total sobre el sistema operativo y SQL Server.

### Casos de uso

- Migraciones rápidas a la nube con cambios mínimos.
- Extensión de aplicaciones locales a la nube.
- Entornos de desarrollo y pruebas.
- Escenarios que requieren control completo del sistema.

### Ventajas empresariales

- Utiliza las mismas herramientas y conocimientos que SQL Server local.
- Reduce el impacto de la migración.
- Permite mantener requisitos específicos que podrían no ser compatibles con servicios totalmente administrados.
- Conserva el control completo sobre la configuración del servidor y la base de datos.

## Azure SQL Managed Instance

Azure SQL Managed Instance proporciona una instancia de SQL Server altamente compatible con entornos locales, pero con muchas tareas administrativas automatizadas.

### Características principales

- Compatibilidad casi completa con SQL Server local.
- Permite alojar múltiples bases de datos en una misma instancia.
- Automatiza:
  - Copias de seguridad.
  - Aplicación de revisiones.
  - Supervisión.
  - Tareas de mantenimiento.
- Mantiene el control sobre seguridad y asignación de recursos.

### Integración con Azure

Utiliza diversos servicios de Azure, entre ellos:

- Azure Storage.
- Azure Event Hubs.
- Microsoft Entra ID.
- Azure Key Vault.

### Seguridad

- Comunicaciones cifradas y firmadas mediante certificados.
- Verificación continua de certificados.
- Cierre automático de conexiones ante certificados revocados.

### Casos de uso

- Migraciones *lift-and-shift* de instancias completas de SQL Server.
- Sistemas que utilizan:
  - Linked Servers.
  - Service Broker.
  - Database Mail.

### Ventajas empresariales

- Reduce significativamente las tareas administrativas.
- Compatibilidad casi total con SQL Server Enterprise Edition.
- Soporta autenticación mediante:
- SQL Server Authentication.
- Microsoft Entra ID.

## Azure SQL Database

Azure SQL Database es una solución PaaS totalmente administrada para bases de datos SQL en la nube.

### Modalidades disponibles

#### Base de datos única

- Implementación rápida de una base de datos individual.
- Escalado bajo demanda.
- Opciones dedicadas o sin servidor (*serverless*).
- Facturación según recursos utilizados.

#### Grupo elástico

- Varias bases de datos comparten recursos comunes.
- Optimiza costes.
- Adecuado para cargas de trabajo variables.

### Casos de uso

- Aplicaciones nativas de la nube.
- Sistemas con alta disponibilidad.
- Aplicaciones con cargas variables.
- Nuevos proyectos cloud.

### Ventajas empresariales

- Actualizaciones automáticas.
- Aplicación automática de revisiones de seguridad.
- Escalabilidad dinámica.
- Alta disponibilidad (99,995 %).
- Restauración a un punto en el tiempo.
- Replicación geográfica.
- Recuperación ante desastres.

### Seguridad

#### Advanced Threat Protection

- Evaluación de vulnerabilidades.
- Detección de actividades sospechosas.
- Alertas de seguridad automáticas.
- Protección frente a ataques de inyección SQL.

#### Auditoría

- Registro de eventos de base de datos.
- Soporte para cumplimiento normativo.
- Detección de anomalías y posibles incidentes de seguridad.

#### Cifrado

- Protección de datos en reposo.
- Protección de datos en tránsito.

---

## Descripción de los servicios de Azure para bases de datos de código abierto

Además de los servicios de Azure SQL, Azure ofrece servicios de bases de datos relacionales para sistemas populares de código abierto como MySQL y PostgreSQL. Estos servicios permiten migrar aplicaciones existentes a Azure con cambios mínimos.

### ¿Qué son MySQL y PostgreSQL?

#### MySQL

MySQL es un sistema de administración de bases de datos relacionales de código abierto ampliamente utilizado en aplicaciones web.

**Características principales:**

- Base de datos relacional de código abierto.
- Componente habitual de la pila LAMP (Linux, Apache, MySQL y PHP).
- Disponible para Linux y Windows.
- Disponible en varias ediciones:
  - Community.
  - Standard.
  - Enterprise.

**Ediciones:**

| Edición | Descripción |
|----------|------------|
| Community | Gratuita y orientada a proyectos de código abierto y aplicaciones web. |
| Standard | Ofrece mejoras de rendimiento y tecnologías avanzadas de almacenamiento. |
| Enterprise | Incluye herramientas avanzadas de seguridad, disponibilidad y escalabilidad. |

#### PostgreSQL

PostgreSQL es una base de datos híbrida objeto-relacional que combina características relacionales tradicionales con capacidades avanzadas.

**Características principales:**

- Soporte para tipos de datos personalizados.
- Arquitectura extensible mediante módulos.
- Capacidad para almacenar y procesar datos geométricos.
- Soporte para procedimientos almacenados.
- Utiliza el lenguaje de consulta **pgsql**, una extensión de SQL.

---

## Azure Database for MySQL

Azure Database for MySQL es una implementación PaaS basada en la edición Community de MySQL.

### Características principales

- Alta disponibilidad integrada.
- Escalabilidad bajo demanda.
- Copias de seguridad automáticas.
- Restauración a un momento determinado.
- Seguridad mediante firewall y SSL.
- Administración completamente gestionada por Azure.

### Ventajas

- Alta disponibilidad.
- Rendimiento predecible.
- Escalado rápido.
- Protección de datos en reposo y en tránsito.
- Restauración de hasta 35 días.
- Seguridad empresarial.
- Cumplimiento normativo.
- Modelo de pago por uso.
- Supervisión mediante métricas, registros y alertas.

### Azure Database for MySQL: servidor flexible

La modalidad **Servidor Flexible** proporciona:

- Mayor control administrativo.
- Configuración más granular.
- Optimización de costos.
- Recomendado para nuevas cargas de trabajo.

---

## Azure Database for PostgreSQL

Azure Database for PostgreSQL es una implementación PaaS de PostgreSQL en Azure.

### Características principales

- Alta disponibilidad.
- Escalabilidad.
- Seguridad integrada.
- Administración automatizada.
- Compatibilidad con herramientas PostgreSQL existentes.

### Limitaciones

Algunas extensiones disponibles en instalaciones locales no están disponibles en Azure.

Las restricciones afectan principalmente a:

- Extensiones personalizadas.
- Procedimientos almacenados en lenguajes distintos de pgsql.
- Interacciones directas con el sistema operativo.

### Servidor flexible para PostgreSQL

La modalidad **Servidor Flexible** proporciona:

- Configuración avanzada del servidor.
- Mayor capacidad de personalización.
- Optimización de costos.
- Administración totalmente gestionada.

### Ventajas

- Detección automática de fallos.
- Conmutación por error integrada.
- Compatibilidad con pgAdmin.
- Administración simplificada.
- Alta disponibilidad.

### Supervisión y optimización

Azure Database for PostgreSQL incluye:

- Registro de consultas ejecutadas.
- Base de datos interna `azure_sys`.
- Vista `query_store.qs_view` para análisis de rendimiento.
- Herramientas para optimizar consultas y supervisar la actividad de usuarios.
