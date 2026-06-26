# Documentación de Microservicios

> Estado: 🟢 Aprobado |
> Última actualización: 2026-06-23 |
> Autor: Equipo de Arquitectura |
> Equipo: Sistema de Gestión de Horarios SENA |

---

# Objetivo

Definir las reglas, estándares y criterios para la creación, mantenimiento y evolución de la documentación de los microservicios del Sistema de Gestión de Horarios SENA.

Este documento garantiza:

* Consistencia documental.
* Trazabilidad arquitectónica.
* Alineación con los bounded contexts.
* Control sobre la creación de nuevos servicios.
* Transferencia de conocimiento entre equipos.

---

# Alcance

Aplica a todos los microservicios del proyecto, incluyendo:

* IAM
* Reference Data
* Academic Management
* Infrastructure
* Scheduling
* Actors
* Document
* Monitoring
* Audit

Y cualquier microservicio futuro aprobado mediante los mecanismos oficiales de arquitectura.

---

# Principios generales

## Un microservicio debe existir antes de documentarse

No crear carpetas en:

```text
09-microservices/services/
```

si el servicio:

* No existe en un repositorio oficial.
* No posee aprobación arquitectónica.
* No tiene bounded context definido.
* No tiene una ADR aprobada.

---

## Prohibición de servicios ficticios

No está permitido:

* Crear microservicios para completar estructura.
* Crear carpetas vacías.
* Documentar servicios hipotéticos.
* Anticipar servicios no aprobados.

Cualquier Pull Request que incumpla esta regla será rechazado.

---

# Requisito de aprobación

Antes de crear la carpeta de un microservicio debe existir alguno de los siguientes artefactos:

## Opción 1 - ADR aprobada

Ubicación:

```text
05-architecture/decisions/records/
```

Ejemplo:

```text
ADR-012-scheduling-service.md
```

---

## Opción 2 - Decisión formal registrada

Ubicación:

```text
15-project-control/open-questions.md
```

Estado requerido:

```text
RESUELTA
```

---

# Ubicación oficial

Cada servicio se documenta en:

```text
09-microservices/services/<service-name>/
```

Ejemplo:

```text
09-microservices/services/scheduling-service/
```

---

# Convención de nombres

La carpeta debe coincidir exactamente con:

* Nombre del repositorio.
* Nombre registrado en el catálogo de servicios.
* Nombre utilizado en arquitectura.

Ejemplo:

```text
scheduling-service
```

No utilizar:

```text
scheduler
horarios
microservicio-horarios
servicio1
```

si no corresponden al nombre oficial.

---

# Flujo de creación

## Paso 1 - Verificar catálogo

Revisar:

```text
09-microservices/service-catalog.md
```

Validar que el servicio no exista previamente.

---

## Paso 2 - Verificar aprobación

Validar existencia de:

* ADR aprobada.
* O decisión formal resuelta.

---

## Paso 3 - Crear estructura

```bash
cp -r 09-microservices/_template/ \
09-microservices/services/<service-name>/
```

Ejemplo:

```bash
cp -r 09-microservices/_template/ \
09-microservices/services/scheduling-service/
```

---

## Paso 4 - Completar documentación

Completar todos los archivos mínimos requeridos.

---

## Paso 5 - Registrar servicio

Agregar registro en:

```text
09-microservices/service-catalog.md
```

Ejemplo:

```markdown
| scheduling-service | Gestión de horarios académicos | Arquitectura | repo-url | 🟡 |
```

---

# Documentación mínima obligatoria

Cada servicio debe contener:

| Archivo         | Obligatorio |
| --------------- | ----------- |
| README.md       | Sí          |
| api-contract.md | Sí          |
| data-model.md   | Sí          |
| events.md       | Sí          |
| runbook.md      | Sí          |

---

# README.md

Debe incluir:

* Nombre del servicio.
* Descripción.
* Responsabilidad.
* Bounded Context.
* Owner.
* Repositorio.
* Dependencias.
* Tecnologías utilizadas.
* Enlaces relacionados.

---

# api-contract.md

Debe documentar:

* Endpoints.
* Métodos HTTP.
* Request.
* Response.
* Errores.
* Versionado.

---

# data-model.md

Debe incluir:

* Entidades principales.
* Relaciones.
* Responsabilidad transaccional.
* Límites del modelo.

Cada servicio es dueño exclusivo de su base de datos.

---

# events.md

Debe incluir:

## Eventos publicados

Ejemplo:

```text
ScheduleCreated
ScheduleUpdated
ScheduleCancelled
```

## Eventos consumidos

Ejemplo:

```text
InstructorAssigned
EnvironmentReserved
```

---

# runbook.md

Debe documentar:

* Despliegue.
* Configuración.
* Variables de entorno.
* Monitoreo.
* Rollback.
* Recuperación ante fallos.
* Troubleshooting.

---

# Estados mínimos requeridos

Antes del primer merge del repositorio del servicio:

| Documento       | Estado mínimo |
| --------------- | ------------- |
| README.md       | 🟡            |
| api-contract.md | 🟡            |

---

# Requisitos para producción

Antes de liberar el servicio a producción:

| Documento       | Estado requerido |
| --------------- | ---------------- |
| README.md       | 🟢               |
| api-contract.md | 🟢               |
| data-model.md   | 🟢               |
| events.md       | 🟢               |
| runbook.md      | 🟢               |

---

# Relación con OpenAPI

El contrato funcional vive en:

```text
09-microservices/services/<service>/api-contract.md
```

Los contratos OpenAPI viven en:

```text
07-api/contracts/openapi/
```

---

## Regla

Siempre que exista un archivo OpenAPI deberá existir referencia cruzada entre ambos documentos.

---

# Registro en el catálogo

Todo microservicio aprobado debe registrarse en:

```text
09-microservices/service-catalog.md
```

El catálogo es la fuente oficial de verdad para los servicios existentes.

---

# Convenciones Git

Creación de documentación:

```bash
git checkout develop
git pull origin develop

git checkout -b hu-xx-service-documentation
```

Commit:

```bash
git commit -m "docs(09-microservices): register scheduling service"
```

---

# Buenas prácticas

* Mantener documentación actualizada.
* Actualizar documentación junto al código.
* Evitar documentación duplicada.
* Mantener trazabilidad con ADRs.
* Mantener trazabilidad con decisiones arquitectónicas.
* Mantener consistencia con el catálogo de servicios.

---

# Referencias

* `service-catalog.md`
* `05-architecture/decisions/`
* `definition-of-ready.md`
* `definition-of-done.md`
* `documentation-rules.md`

---

# Regla general

> Ningún microservicio podrá considerarse parte oficial del Sistema de Gestión de Horarios SENA sin encontrarse registrado en el catálogo de servicios y cumplir las reglas definidas en este documento.
