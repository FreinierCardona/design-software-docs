# Entities and Rules

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Este documento describe las principales entidades del dominio del Sistema de Gestión de Horarios SENA, sus responsabilidades dentro del negocio y las reglas que garantizan la consistencia funcional del sistema.

Las entidades aquí descritas representan conceptos del negocio y no estructuras de base de datos.

---

# Entidades del dominio

## Usuario

Representa una persona autenticada dentro del sistema con acceso a una o varias funcionalidades según sus permisos.

### Responsabilidades

- Autenticarse.
- Acceder al sistema.
- Ejecutar operaciones autorizadas.

### Invariantes

- Debe encontrarse activo para acceder al sistema.
- Debe poseer al menos un rol asignado.

---

## Instructor

Representa al instructor responsable de impartir formación.

### Responsabilidades

- Impartir sesiones de formación.
- Tener disponibilidad horaria.
- Ser asignado a horarios.

### Invariantes

- No puede tener dos sesiones simultáneas.
- Debe pertenecer a un centro de formación.

---

## Aprendiz

Representa al estudiante perteneciente a una ficha de formación.

### Responsabilidades

- Participar en las sesiones programadas.
- Mantener relación con una ficha activa.

### Invariantes

- Solo puede pertenecer a una ficha activa al mismo tiempo.

---

## Programa

Representa un programa de formación del SENA.

### Responsabilidades

- Agrupar competencias.
- Servir como base para las ofertas de formación.

### Invariantes

- Debe contener al menos una competencia.

---

## Competencia

Define una capacidad o habilidad que debe desarrollar el aprendiz.

### Responsabilidades

- Agrupar resultados de aprendizaje.

### Invariantes

- Debe pertenecer a un único programa.

---

## RAP (Resultado de Aprendizaje)

Representa un resultado específico asociado a una competencia.

### Responsabilidades

- Definir los objetivos formativos de una competencia.

### Invariantes

- Debe pertenecer a una única competencia.

---

## Ficha

Representa un grupo académico de aprendices.

### Responsabilidades

- Agrupar aprendices.
- Asociarse a un programa.

### Invariantes

- Debe pertenecer a una única oferta vigente.

---

## Ambiente

Representa un espacio físico o virtual donde se desarrolla la formación.

### Responsabilidades

- Alojar sesiones de formación.
- Gestionar disponibilidad.

### Invariantes

- No puede ser reservado simultáneamente para dos sesiones.

---

## Horario

Representa la planificación completa de una ficha durante un periodo académico.

### Responsabilidades

- Organizar sesiones.
- Relacionar instructores y ambientes.

### Invariantes

- No puede contener conflictos de programación.

---

## Sesión de Clase

Representa una unidad de formación programada.

### Responsabilidades

- Definir fecha, hora y duración.
- Asociar instructor y ambiente.

### Invariantes

- Debe pertenecer a un único horario.

---

## Asignación

Representa la relación entre instructor, ambiente, ficha y sesión.

### Responsabilidades

- Consolidar la programación académica.

### Invariantes

- Solo puede existir una asignación válida para una misma sesión.

---

## Documento

Representa un archivo institucional administrado por el sistema.

### Responsabilidades

- Gestionar versiones.
- Servir como evidencia documental.

### Invariantes

- Siempre debe existir una versión vigente.

---

## Alerta

Representa una situación que requiere atención por parte del sistema o un usuario.

### Responsabilidades

- Notificar eventos relevantes.
- Facilitar el seguimiento operativo.

### Invariantes

- Toda alerta debe tener un estado.

---

## Registro de Auditoría

Representa el historial permanente de las operaciones realizadas.

### Responsabilidades

- Garantizar la trazabilidad.

### Invariantes

- No puede modificarse ni eliminarse.

---

# Reglas generales del negocio

## Gestión Académica

- Un programa puede contener múltiples competencias.
- Una competencia puede contener múltiples RAP.
- Una ficha pertenece únicamente a un programa de formación.
- Una oferta solo puede contener fichas activas.

---

## Gestión de Horarios

- Una sesión debe tener un instructor asignado.
- Una sesión debe tener un ambiente asignado.
- Ningún instructor puede impartir dos sesiones en el mismo horario.
- Ningún ambiente puede reservarse simultáneamente.
- Una ficha no puede tener sesiones superpuestas.

---

## Gestión de Ambientes

- Un ambiente fuera de servicio no puede ser reservado.
- Un mantenimiento bloquea automáticamente la disponibilidad del ambiente.
- La disponibilidad debe recalcularse después de cada reserva o mantenimiento.

---

## Gestión de Usuarios

- Todo usuario debe poseer al menos un rol.
- Los permisos son heredados por los roles.
- Un usuario inactivo no puede autenticarse.

---

## Gestión Documental

- Toda modificación genera una nueva versión del documento.
- Nunca se elimina el historial de versiones.

---

## Auditoría

- Toda operación relevante genera un registro de auditoría.
- Los registros son de solo lectura.

---

# Invariantes globales

Las siguientes reglas deben mantenerse en todo momento dentro del sistema:

- No pueden existir conflictos de horarios.
- No pueden existir reservas duplicadas de ambientes.
- Todo horario debe estar asociado a una ficha.
- Toda sesión debe tener instructor y ambiente.
- Todo usuario debe estar autenticado para ejecutar operaciones protegidas.
- Toda modificación relevante debe quedar registrada en auditoría.
- Ninguna entidad crítica puede quedar en un estado inconsistente.

---

# Lenguaje ubicuo

Para mantener consistencia entre los equipos de desarrollo, análisis y negocio, los términos definidos en `domain-map.md` constituyen el lenguaje ubicuo oficial del proyecto y deberán utilizarse en la documentación, el código y las discusiones funcionales.