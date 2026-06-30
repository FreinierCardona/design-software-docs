# Models

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura / Base de Datos

---

# Objetivo

Este documento describe los modelos de datos utilizados en el Sistema de Gestión de Horarios SENA (SGH SENA), desde la representación del negocio hasta la implementación física en PostgreSQL.

Los modelos aquí definidos sirven como referencia para garantizar consistencia entre el dominio, los microservicios y las bases de datos del sistema.

---

# Arquitectura de datos

El SGH SENA implementa una arquitectura de persistencia basada en el patrón:

> Database per Service

Cada microservicio es propietario de su información y administra de forma independiente:

- tablas
- índices
- restricciones
- migraciones
- optimizaciones

No existe una base de datos compartida entre microservicios.

La comunicación entre servicios se realiza mediante APIs y eventos.

---

# Niveles de modelado

La arquitectura de datos se divide en tres niveles.

## Modelo Conceptual

Representa únicamente los conceptos del negocio y la relación existente entre ellos.

No incluye:

- tipos de datos
- claves primarias
- claves foráneas
- índices
- restricciones

Su propósito es comprender la información que maneja el sistema.

Ejemplos de entidades conceptuales:

- Usuario
- Instructor
- Aprendiz
- Programa
- Competencia
- RAP
- Ficha
- Ambiente
- Horario
- Sesión de clase
- Reserva
- Documento
- Notificación

---

## Modelo Lógico

Describe las entidades con sus atributos y relaciones.

Incluye:

- atributos
- cardinalidades
- claves primarias
- claves foráneas
- reglas de integridad
- normalización

Es independiente del motor de base de datos.

---

## Modelo Físico

Representa la implementación final sobre PostgreSQL.

Incluye:

- tablas
- columnas
- tipos de datos
- índices
- constraints
- UUID
- timestamps
- auditoría
- particionamiento cuando aplique

Este modelo es el utilizado durante el desarrollo del software.

---

# Modelo general del sistema

La información del SGH SENA se organiza en los siguientes dominios funcionales.

| Dominio | Información administrada |
|----------|--------------------------|
| Seguridad | Usuarios, roles, permisos, autenticación y sesiones |
| Datos Maestros | Centros, regionales, catálogos, estados y parámetros |
| Gestión Académica | Programas, competencias, RAP, fichas y ofertas |
| Ambientes | Ambientes, inventario, disponibilidad y reservas |
| Programación | Horarios, franjas, asignaciones y conflictos |
| Actores | Instructores, aprendices, empresas y etapa productiva |
| Documentos | Plantillas, documentos y versiones |
| Seguimiento | Indicadores, alertas, notificaciones y planes de mejoramiento |
| Auditoría | Registro histórico de operaciones |

---

# Distribución por microservicios

Cada módulo administra únicamente sus propias entidades.

| Microservicio | Responsabilidad |
|---------------|----------------|
| IAM | Gestión de identidad y acceso |
| Reference Data | Catálogos y datos maestros |
| Academic Management | Información académica |
| Training Environment | Ambientes y recursos físicos |
| Scheduling | Horarios y programación académica |
| Actors | Participantes del proceso formativo |
| Document | Gestión documental |
| Monitoring | Seguimiento e indicadores |
| Audit | Auditoría del sistema |

---

# Relaciones entre modelos

El flujo de diseño sigue la siguiente secuencia:

```text
Requerimientos
        │
        ▼
Modelo Conceptual
        │
        ▼
Modelo Lógico
        │
        ▼
Modelo Físico
        │
        ▼
Migraciones PostgreSQL
        │
        ▼
Base de Datos
```

---

# Principios de modelado

Todos los modelos deberán cumplir los siguientes principios:

- Alta cohesión.
- Bajo acoplamiento.
- Una única responsabilidad por entidad.
- Integridad referencial.
- Normalización hasta 3FN cuando sea aplicable.
- Uso de UUID como identificador.
- Auditoría para entidades transaccionales.
- Eliminación lógica cuando el negocio lo requiera.
- Consistencia de nombres entre dominio y persistencia.

---

# Convenciones

## Identificadores

- UUID versión 4.
- No se utilizan identificadores autoincrementales.

---

## Auditoría

Las entidades transaccionales incorporan, cuando aplique:

- created_at
- updated_at
- created_by
- updated_by

---

## Fechas

Todas las fechas se almacenan utilizando:

- TIMESTAMP WITH TIME ZONE

---

## Relaciones

Se utilizan claves foráneas únicamente dentro del mismo microservicio.

Las relaciones entre microservicios se representan mediante identificadores externos y comunicación mediante APIs o eventos.

---

# Tecnologías

La persistencia del proyecto utiliza:

- PostgreSQL
- SQL estándar
- UUID
- Migraciones versionadas
- Índices B-Tree y GIN cuando corresponda

---

# Referencias

Este documento se complementa con:

- `data-dictionary.md`
- `migration-strategy.md`
- `02-domain`
- `09-microservices`
- ADR relacionados con persistencia