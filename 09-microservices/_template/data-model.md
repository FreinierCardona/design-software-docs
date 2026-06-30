# Data Model

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura de Software

## Propósito

Este documento describe el modelo de datos del microservicio, definiendo las entidades persistidas, sus relaciones, reglas de negocio asociadas y consideraciones de almacenamiento.

El modelo de datos representa la estructura lógica de la información administrada exclusivamente por el microservicio y constituye la referencia para comprender su persistencia sin depender de detalles de implementación.

---

# Objetivos

La documentación del modelo de datos permite:

- Comprender la estructura de información del microservicio.
- Identificar las entidades del dominio persistente.
- Documentar las relaciones entre entidades.
- Registrar reglas de integridad.
- Facilitar la evolución del esquema de datos.
- Mantener la independencia entre microservicios.

---

# Alcance

Este documento debe describir únicamente los datos administrados por el microservicio.

No incluye:

- estructuras pertenecientes a otros servicios;
- consultas SQL;
- scripts DDL o DML;
- procedimientos almacenados;
- configuraciones específicas del motor de base de datos.

Cada microservicio es responsable exclusivamente de su propio modelo de datos.

---

# Información mínima requerida

La documentación deberá incluir como mínimo:

- Nombre del microservicio.
- Contexto de negocio.
- Motor de persistencia utilizado.
- Estrategia de almacenamiento.
- Principales entidades del dominio.
- Relaciones relevantes.
- Restricciones de integridad.
- Reglas de consistencia.

---

# Entidades

Para cada entidad deberá documentarse:

- Nombre.
- Descripción.
- Responsabilidad.
- Identificador principal.
- Atributos relevantes.
- Relaciones con otras entidades del mismo servicio.
- Reglas de negocio asociadas.

---

# Relaciones

Cuando existan relaciones entre entidades deberán describirse:

- Tipo de relación.
- Cardinalidad.
- Dependencia funcional.
- Restricciones de integridad.
- Reglas de eliminación o actualización.

Las relaciones deberán mantenerse únicamente dentro del límite del microservicio.

---

# Integridad de los datos

La documentación deberá especificar:

- Restricciones de unicidad.
- Campos obligatorios.
- Valores permitidos.
- Reglas de validación.
- Consistencia referencial interna.

---

# Consideraciones de persistencia

Se deberá documentar, cuando aplique:

- Estrategia de versionamiento del esquema.
- Auditoría.
- Soft Delete.
- Trazabilidad.
- Optimización de consultas.
- Índices relevantes.
- Estrategias de migración.

---

# Límites del modelo

El modelo de datos deberá respetar los principios de la arquitectura basada en microservicios:

- propiedad exclusiva de los datos;
- independencia del almacenamiento;
- ausencia de acceso directo a bases de datos de otros servicios;
- comunicación únicamente mediante APIs o eventos.

---

# Relación con otros documentos

Este documento complementa:

- Modelo de dominio.
- Diagramas UML.
- Arquitectura del microservicio.
- Contrato API.
- ADR relacionados.
- Estrategia de migraciones.

---

# Buenas prácticas

El modelo de datos deberá:

- representar únicamente el dominio del microservicio;
- evitar dependencias con otros servicios;
- mantener una nomenclatura consistente con el lenguaje del negocio;
- documentar únicamente información vigente;
- evolucionar junto con el dominio funcional.

---

# Observaciones

Este documento corresponde a una plantilla de documentación y deberá adaptarse al contexto funcional de cada microservicio, manteniendo consistencia con la arquitectura general del Sistema de Gestión de Horarios SENA y con los principios de independencia de datos definidos para el proyecto.