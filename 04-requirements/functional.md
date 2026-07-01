# Requisitos Funcionales

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Propósito

Este documento define los requisitos funcionales del Sistema de Gestión de Horarios SENA (SGH SENA), describiendo las capacidades que deberá ofrecer la plataforma para satisfacer las necesidades del negocio y de los diferentes actores del sistema.

Los requisitos aquí documentados representan las funcionalidades esperadas del producto y sirven como base para la construcción de historias de usuario, casos de uso, diseño de arquitectura, desarrollo y pruebas.

---

# Alcance

Los requisitos funcionales abarcan todos los módulos del SGH SENA, incluyendo:

- Gestión de identidad y acceso.
- Administración académica.
- Gestión de ambientes.
- Programación de horarios.
- Gestión de instructores.
- Gestión de aprendices.
- Gestión documental.
- Seguimiento.
- Auditoría.
- Configuración general del sistema.

---

# Convenciones

Todos los requisitos funcionales utilizan el prefijo:

RF-XXX

Ejemplo:

- RF-001
- RF-002
- RF-010

Cada requisito debe ser trazable hacia:

- Historia de Usuario
- Caso de Uso
- Pruebas
- Módulo funcional
- Componente arquitectónico

---

# Requisitos Funcionales

## Gestión de Identidad y Acceso (IAM)

### RF-001
El sistema deberá permitir el registro de usuarios autorizados.

### RF-002
El sistema deberá autenticar usuarios mediante credenciales seguras.

### RF-003
El sistema deberá administrar roles y permisos.

### RF-004
El sistema deberá controlar el acceso a funcionalidades según el rol asignado.

### RF-005
El sistema deberá administrar sesiones y tokens de autenticación.

---

## Administración Académica

### RF-006
El sistema deberá administrar programas de formación.

### RF-007
El sistema deberá gestionar competencias y Resultados de Aprendizaje (RAP).

### RF-008
El sistema deberá administrar fichas de formación.

### RF-009
El sistema deberá gestionar ofertas de formación.

### RF-010
El sistema deberá mantener la estructura académica actualizada.

---

## Gestión de Ambientes

### RF-011
El sistema deberá registrar ambientes de formación.

### RF-012
El sistema deberá administrar la disponibilidad de ambientes.

### RF-013
El sistema deberá gestionar reservas de ambientes.

### RF-014
El sistema deberá controlar mantenimientos programados.

### RF-015
El sistema deberá administrar el inventario asociado a cada ambiente.

---

## Programación de Horarios

### RF-016
El sistema deberá generar horarios académicos.

### RF-017
El sistema deberá asignar instructores a sesiones de formación.

### RF-018
El sistema deberá asignar ambientes disponibles.

### RF-019
El sistema deberá detectar conflictos de programación.

### RF-020
El sistema deberá impedir la generación de horarios inconsistentes.

### RF-021
El sistema deberá administrar franjas horarias.

### RF-022
El sistema deberá permitir modificaciones controladas de horarios.

---

## Gestión de Actores

### RF-023
El sistema deberá administrar instructores.

### RF-024
El sistema deberá administrar aprendices.

### RF-025
El sistema deberá administrar empresas vinculadas a etapa productiva.

### RF-026
El sistema deberá registrar la información académica de los actores.

### RF-027
El sistema deberá mantener historial de asignaciones.

---

## Gestión Documental

### RF-028
El sistema deberá almacenar documentos institucionales.

### RF-029
El sistema deberá administrar versiones de documentos.

### RF-030
El sistema deberá gestionar plantillas institucionales.

---

## Seguimiento

### RF-031
El sistema deberá generar indicadores (KPI).

### RF-032
El sistema deberá emitir alertas operativas.

### RF-033
El sistema deberá registrar planes de mejoramiento.

### RF-034
El sistema deberá generar notificaciones.

### RF-035
El sistema deberá realizar seguimiento a las actividades académicas.

---

## Auditoría

### RF-036
El sistema deberá registrar todas las operaciones críticas.

### RF-037
El sistema deberá mantener un historial inalterable de auditoría.

### RF-038
El sistema deberá permitir la consulta de eventos auditados.

---

## Configuración

### RF-039
El sistema deberá administrar parámetros generales.

### RF-040
El sistema deberá administrar catálogos institucionales.

### RF-041
El sistema deberá administrar estados del sistema.

### RF-042
El sistema deberá administrar centros de formación y macroregiones.

---

# Reglas Generales

Todos los requisitos funcionales deberán cumplir las siguientes reglas:

- Ser verificables.
- Ser medibles.
- Tener una fuente de negocio.
- Mantener trazabilidad.
- Ser independientes de la implementación tecnológica.
- Estar asociados a uno o más casos de prueba.
- Relacionarse con una o más historias de usuario.

---

# Relación con otros documentos

| Documento | Relación |
|------------|----------|
| Product Vision | Define el propósito del producto. |
| Product Backlog | Descompone los requisitos en trabajo planificable. |
| User Stories | Describe las necesidades del usuario. |
| Domain Model | Define las entidades involucradas. |
| Casos de Uso | Describe el comportamiento funcional. |
| Arquitectura | Define la implementación técnica. |
| Matriz de Trazabilidad | Relaciona requisitos con desarrollo y pruebas. |

---

# Observaciones

Los requisitos funcionales representan el comportamiento esperado del sistema a nivel de negocio. Durante el desarrollo del proyecto podrán ampliarse, descomponerse o refinarse mediante historias de usuario, siempre conservando su identificador para mantener la trazabilidad documental.