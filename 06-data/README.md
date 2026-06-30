# Datos

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura / Base de Datos

## Propósito

Esta sección centraliza la documentación relacionada con la arquitectura de datos del Sistema de Gestión de Horarios SENA (SGH SENA).

Su objetivo es definir la estructura conceptual de la información que maneja el sistema, establecer un lenguaje común para todas las áreas del proyecto y documentar la estrategia de evolución del modelo de datos durante el ciclo de vida del software.

La información contenida en esta carpeta sirve como referencia para arquitectos, desarrolladores, analistas funcionales, administradores de bases de datos y equipos de integración.

---

## Alcance

Esta documentación cubre:

- Modelo conceptual de la información del sistema.
- Modelo lógico de datos.
- Modelo físico de persistencia.
- Diccionario de datos compartido.
- Convenciones de nombres.
- Relaciones entre entidades.
- Estrategia de migraciones.
- Evolución del esquema de base de datos.
- Reglas generales de persistencia.

No documenta lógica de negocio ni procesos funcionales.

---

## Organización

La documentación se divide en tres componentes principales:

| Documento | Objetivo |
|-----------|----------|
| Models | Describe la estructura de datos desde el nivel conceptual hasta el modelo físico. |
| Data Dictionary | Define cada entidad, atributo, tipo de dato y reglas de almacenamiento. |
| Migration Strategy | Define cómo evolucionan los esquemas de base de datos sin afectar la continuidad del sistema. |

---

## Relación con el proyecto

El SGH SENA utiliza una arquitectura basada en microservicios.

Cada microservicio posee su propia base de datos (Database per Service), sin embargo, todos comparten un lenguaje de negocio común definido desde esta sección.

Aquí únicamente se documentan:

- conceptos compartidos;
- estándares de modelado;
- reglas generales de persistencia;
- nomenclatura;
- convenciones.

La implementación física específica de cada servicio se documenta dentro del propio microservicio.

---

## Relación con otras carpetas

### Diferencia con `02-domain`

Esta sección describe la implementación de persistencia (tablas, columnas, tipos, relaciones, índices, restricciones y migraciones).

Las entidades de negocio, reglas funcionales, agregados, objetos de valor y casos de uso se documentan exclusivamente en `02-domain`.

Un mismo concepto (por ejemplo **Horario**) tendrá:

- definición funcional en Domain;
- representación física en Data.

---

### Diferencia con `09-microservices`

Esta carpeta contiene únicamente los modelos compartidos del sistema.

Cada microservicio documenta internamente:

- su esquema propio;
- tablas locales;
- relaciones internas;
- migraciones específicas;
- índices particulares.

No debe duplicarse información entre ambas ubicaciones.

---

## Principios de diseño

La arquitectura de datos del proyecto sigue los siguientes principios:

- Base de datos por microservicio.
- Bajo acoplamiento entre esquemas.
- Alta cohesión funcional.
- Integridad referencial dentro de cada servicio.
- Comunicación entre servicios mediante APIs y eventos.
- Identificadores UUID como claves primarias.
- Auditoría en entidades que lo requieran.
- Versionamiento controlado del esquema.
- Compatibilidad hacia atrás durante migraciones.

---

## Convenciones generales

Todos los modelos deberán seguir las mismas convenciones:

- nombres descriptivos;
- singular para entidades;
- claves primarias UUID;
- claves foráneas explícitas;
- nombres consistentes entre dominio y persistencia;
- documentación obligatoria para cada entidad;
- eliminación física únicamente cuando sea permitido por la política del servicio.

---

## Archivos

| Archivo | Descripción | Estado |
|---------|-------------|--------|
| [models.md](./models.md) | Modelos conceptuales, lógicos y físicos de la arquitectura de datos del SGH SENA. | 🟢 |
| [data-dictionary.md](./data-dictionary.md) | Diccionario de entidades, atributos, tipos de datos, restricciones y reglas de persistencia. | 🟢 |
| [migration-strategy.md](./migration-strategy.md) | Estrategia para el versionamiento y evolución controlada de los esquemas de base de datos. | 🟢 |

---

## Dependencias

Esta documentación se relaciona directamente con:

- 02-domain
- 07-architecture
- 09-microservices
- ADR relacionados con persistencia
- Arquitectura de Base de Datos
- PostgreSQL

---

## Estado

Toda modificación sobre el modelo de datos deberá reflejarse en esta documentación antes de ser incorporada al repositorio principal mediante Pull Request.