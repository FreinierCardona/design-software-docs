# Domain Map

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

El mapa de dominio identifica los principales contextos funcionales (Bounded Contexts) del Sistema de Gestión de Horarios SENA y define la separación de responsabilidades entre los diferentes módulos del negocio.

Cada contexto encapsula un conjunto de reglas de negocio, entidades y casos de uso relacionados con una capacidad específica del sistema, permitiendo una arquitectura desacoplada basada en microservicios y Domain-Driven Design (DDD).

---

# Bounded Contexts

## IAM (Identity and Access Management)

**Responsabilidad**

Gestionar la autenticación, autorización e identidad de los usuarios del sistema.

**Entidades principales**

- Usuario
- Rol
- Permiso
- Sesión
- Token

**Consumido por**

Todos los módulos del sistema.

---

## Reference Data

**Responsabilidad**

Administrar la información maestra utilizada por los demás módulos.

**Entidades principales**

- Macroregión
- Centro de Formación
- Catálogo
- Estado
- Parámetro

**Consumido por**

Todos los módulos.

---

## Academic Management

**Responsabilidad**

Gestionar la estructura académica de la oferta de formación.

**Entidades principales**

- Programa
- Competencia
- RAP
- Ficha
- Oferta

**Depende de**

- Reference Data

---

## Actors

**Responsabilidad**

Administrar las personas y organizaciones que participan en el proceso de formación.

**Entidades principales**

- Instructor
- Aprendiz
- Empresa
- Etapa Productiva
- Bitácora

**Depende de**

- IAM
- Academic Management

---

## Training Environment

**Responsabilidad**

Gestionar los ambientes de formación y los recursos físicos disponibles.

**Entidades principales**

- Ambiente
- Inventario
- Mantenimiento
- Reserva
- Disponibilidad

**Depende de**

- Reference Data

---

## Scheduling

**Responsabilidad**

Planificar y administrar la programación académica.

**Entidades principales**

- Horario
- Sesión de Clase
- Franja Horaria
- Asignación
- Conflicto

**Depende de**

- Academic Management
- Actors
- Training Environment

---

## Document

**Responsabilidad**

Gestionar la documentación institucional utilizada por el sistema.

**Entidades principales**

- Documento
- Versión
- Plantilla

**Consumido por**

Todos los módulos cuando requieren documentos oficiales.

---

## Monitoring

**Responsabilidad**

Realizar seguimiento al funcionamiento operativo y académico del sistema.

**Entidades principales**

- Indicador
- Alerta
- Notificación
- Sesión de Seguimiento
- Plan de Mejoramiento

**Depende de**

Todos los módulos productores de información.

---

## Audit

**Responsabilidad**

Registrar de forma permanente todas las operaciones relevantes realizadas dentro del sistema.

**Entidades principales**

- Registro de Auditoría

**Consumido por**

Toda la plataforma.

---

# Relaciones entre Contextos

```text
                    IAM
                     │
                     │
             Reference Data
                     │
     ┌───────────────┼───────────────┐
     │               │               │
Academic        Training        Document
Management     Environment
     │               │
     └───────┬───────┘
             │
          Scheduling
             │
          Actors
             │
       Monitoring
             │
           Audit
```

---

# Principios del dominio

- Cada contexto posee una única responsabilidad de negocio.
- Ningún contexto accede directamente a la persistencia de otro.
- La comunicación entre contextos se realiza mediante contratos y eventos de dominio.
- Cada microservicio mantiene autonomía funcional y de datos.
- El lenguaje ubicuo debe mantenerse consistente entre todos los contextos.

---

# Lenguaje ubicuo

| Término | Definición |
|----------|------------|
| Programa | Estructura oficial de formación ofrecida por el SENA. |
| Competencia | Resultado de aprendizaje esperado dentro de un programa. |
| RAP | Resultado de Aprendizaje asociado a una competencia. |
| Ficha | Grupo de aprendices pertenecientes a una oferta de formación. |
| Ambiente | Espacio físico o virtual donde se desarrolla la formación. |
| Horario | Planificación temporal de las sesiones de formación. |
| Asignación | Asociación entre instructor, ambiente, ficha y sesión. |
| Conflicto | Inconsistencia detectada durante la planificación de horarios. |
| Alerta | Notificación generada por una condición que requiere atención. |
| Auditoría | Registro permanente de las operaciones realizadas en el sistema. |