# Open Questions

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura, Gestión del Proyecto y Producto

## Propósito

Este documento registra las preguntas, incertidumbres y decisiones pendientes identificadas durante el desarrollo del Sistema de Gestión de Horarios SENA.

Su objetivo es mantener un seguimiento estructurado de aquellos temas que requieren análisis, validación o aprobación antes de continuar con su implementación, evitando que las decisiones queden únicamente en conversaciones informales o herramientas de mensajería.

Este registro forma parte de la gobernanza técnica y funcional del proyecto.

---

# Objetivos

Este documento permite:

- Registrar decisiones pendientes.
- Dar trazabilidad a dudas técnicas y funcionales.
- Asignar responsables para su resolución.
- Evitar pérdida de contexto durante el desarrollo.
- Facilitar la comunicación entre equipos.
- Relacionar las respuestas con la documentación oficial.

---

# Alcance

Las preguntas abiertas podrán estar relacionadas con:

- Arquitectura.
- Requisitos funcionales.
- Reglas de negocio.
- Modelado de datos.
- APIs.
- Integraciones.
- Infraestructura.
- Seguridad.
- UX/UI.
- Procesos del proyecto.

No deberán utilizarse para registrar tareas de desarrollo, incidencias, errores o actividades del backlog.

---

# Flujo de resolución

1. **Registrar**

   Cualquier integrante del proyecto podrá registrar una pregunta abierta cuando identifique una incertidumbre que pueda afectar el desarrollo o la toma de decisiones.

2. **Asignar**

   El equipo de Arquitectura, Gestión o Producto asignará un responsable y establecerá una prioridad para su análisis.

3. **Analizar**

   El responsable evaluará la situación, consultará los equipos involucrados y propondrá una respuesta o alternativa de solución.

4. **Resolver**

   Una vez exista una decisión aprobada, la pregunta cambiará al estado **RESUELTA**.

5. **Actualizar documentación**

   Cuando la respuesta modifique la arquitectura, requisitos o procesos del proyecto, deberán actualizarse los documentos correspondientes.

6. **Registrar historial**

   Las preguntas resueltas permanecerán documentadas para conservar la trazabilidad del proyecto.

---

# Cuándo registrar una pregunta

Debe registrarse una pregunta cuando:

- exista más de una alternativa válida;
- falte información para continuar un desarrollo;
- sea necesaria una decisión arquitectónica;
- exista incertidumbre sobre una regla de negocio;
- una integración requiera validación;
- un requisito necesite aclaración.

No deberá utilizarse para consultas operativas de corta duración.

---

# Prioridades

| Prioridad | Descripción |
|-----------|-------------|
| Alta | Bloquea el desarrollo o afecta decisiones importantes. |
| Media | Requiere respuesta antes de implementar una funcionalidad específica. |
| Baja | Puede resolverse posteriormente sin afectar el avance inmediato del proyecto. |

---

# Estados válidos

| Estado | Significado |
|--------|-------------|
| `ABIERTA` | La pregunta ha sido registrada y aún no ha sido asignada. |
| `EN REVISIÓN` | Se encuentra siendo analizada por el responsable asignado. |
| `RESUELTA` | Existe una respuesta aprobada y la documentación correspondiente ha sido actualizada cuando aplica. |
| `CANCELADA` | La pregunta dejó de ser aplicable y se conserva únicamente para mantener el historial. |

---

# Registro de preguntas

| ID | Pregunta | Área | Prioridad | Responsable | Fecha límite | Estado | Documento relacionado |
|----|----------|------|-----------|-------------|--------------|--------|-----------------------|

---

# Historial de preguntas resueltas

| ID | Pregunta | Área | Resolución | Documentación actualizada |
|----|----------|------|------------|---------------------------|

---

# Relación con otros documentos

Las respuestas registradas podrán generar cambios en:

- Product.
- Requirements.
- Architecture.
- ADR (Architecture Decision Records).
- Microservices.
- DevOps.
- Quality.
- UX/UI.
- Operaciones.

Cuando una respuesta implique una decisión arquitectónica permanente, deberá documentarse mediante un ADR.

---

# Mantenimiento

Este documento deberá mantenerse actualizado durante todo el ciclo de vida del proyecto.

Las preguntas no deberán eliminarse; una vez resueltas o canceladas pasarán al historial para conservar la trazabilidad de las decisiones tomadas.