# Matriz de Trazabilidad

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Propósito

La matriz de trazabilidad permite establecer la relación entre los diferentes artefactos del proyecto, garantizando que cada necesidad del negocio pueda rastrearse desde su definición hasta su implementación, validación y despliegue.

Este documento facilita el control de cambios, el seguimiento del desarrollo, la validación funcional y la verificación de cobertura durante todo el ciclo de vida del Sistema de Gestión de Horarios SENA (SGH SENA).

---

# Objetivos

La matriz de trazabilidad permite:

- Relacionar requisitos funcionales y no funcionales.
- Asociar requisitos con historias de usuario.
- Vincular historias con el Product Backlog.
- Relacionar requisitos con módulos funcionales.
- Asociar funcionalidades con casos de uso.
- Relacionar requisitos con componentes de arquitectura.
- Garantizar cobertura de pruebas.
- Facilitar auditorías del proyecto.
- Controlar el impacto de cambios futuros.

---

# Alcance

La trazabilidad aplica para todos los elementos del proyecto:

- Requisitos funcionales.
- Requisitos no funcionales.
- Historias de usuario.
- Product Backlog.
- Casos de uso.
- Arquitectura.
- Microservicios.
- APIs.
- Base de datos.
- Pruebas.
- Documentación.
- Versiones del software.

---

# Flujo de Trazabilidad

Todo requisito deberá seguir el siguiente flujo:

```
Necesidad del negocio
        │
        ▼
Requisito (RF / RNF)
        │
        ▼
Historia de Usuario (HU)
        │
        ▼
Product Backlog
        │
        ▼
Caso de Uso
        │
        ▼
Diseño / Arquitectura
        │
        ▼
Implementación
        │
        ▼
Pruebas
        │
        ▼
Liberación
```

---

# Identificadores

Cada elemento del proyecto utiliza un identificador único.

| Elemento | Prefijo |
|----------|----------|
| Requisito Funcional | RF |
| Requisito No Funcional | RNF |
| Historia de Usuario | HU |
| Caso de Uso | CU |
| API | API |
| Microservicio | MS |
| Prueba | TP |
| ADR | ADR |

---

# Matriz de Relación

| Requisito | Historia | Módulo | Microservicio | Caso de Uso | Prueba |
|------------|-----------|--------------------|----------------------|-------------|-----------|
| RF-001 | HU-001 | IAM | IAM Service | CU-001 | TP-001 |
| RF-006 | HU-020 | Academic Management | Academic Service | CU-008 | TP-014 |
| RF-011 | HU-035 | Training Environment | Environment Service | CU-015 | TP-023 |
| RF-016 | HU-050 | Scheduling | Scheduling Service | CU-025 | TP-040 |
| RF-023 | HU-071 | Actors | Actors Service | CU-031 | TP-052 |
| RF-028 | HU-090 | Document | Document Service | CU-041 | TP-070 |
| RF-031 | HU-105 | Monitoring | Monitoring Service | CU-049 | TP-082 |
| RF-036 | HU-120 | Audit | Audit Service | CU-055 | TP-095 |
| RNF-004 | HU-002 | IAM | IAM Service | CU-002 | TP-003 |
| RNF-029 | HU-121 | Audit | Audit Service | CU-056 | TP-097 |

> **Nota:** La matriz se ampliará progresivamente conforme evolucionen las historias de usuario, los casos de uso y las pruebas del proyecto.

---

# Cobertura Esperada

Todo requisito deberá cumplir las siguientes relaciones mínimas.

| Elemento | Debe relacionarse con |
|----------|------------------------|
| RF | HU, CU, Microservicio y Prueba |
| RNF | Arquitectura, Microservicio y Prueba |
| HU | RF o RNF |
| Caso de Uso | HU |
| API | Microservicio |
| Microservicio | Módulo |
| Prueba | RF, RNF o HU |

---

# Gestión de Cambios

Toda modificación realizada sobre un requisito deberá actualizar como mínimo:

- Historia de Usuario correspondiente.
- Product Backlog.
- Casos de Uso afectados.
- Arquitectura.
- Diagramas.
- APIs.
- Modelo de Datos.
- Casos de Prueba.
- Documentación relacionada.

Ningún cambio funcional deberá implementarse sin actualizar previamente su trazabilidad.

---

# Responsabilidades

| Rol | Responsabilidad |
|------|-----------------|
| Product Owner | Aprobar cambios funcionales. |
| Arquitecto de Software | Validar impacto arquitectónico. |
| Scrum Master | Garantizar trazabilidad durante el Sprint. |
| Desarrolladores | Implementar requisitos aprobados. |
| QA | Validar cobertura mediante pruebas. |

---

# Beneficios

La matriz de trazabilidad permite:

- Conocer el origen de cada funcionalidad.
- Identificar rápidamente el impacto de cambios.
- Evitar requisitos sin implementación.
- Evitar código sin respaldo funcional.
- Garantizar cobertura de pruebas.
- Facilitar auditorías técnicas.
- Mantener sincronizada toda la documentación.

---

# Relación con otros documentos

| Documento | Relación |
|------------|----------|
| Functional Requirements | Fuente principal de los RF. |
| Non Functional Requirements | Fuente principal de los RNF. |
| User Stories | Implementación funcional de los requisitos. |
| Product Backlog | Planificación del desarrollo. |
| Casos de Uso | Comportamiento esperado del sistema. |
| Arquitectura | Implementación técnica. |
| ADR | Decisiones arquitectónicas. |
| Plan de Pruebas | Validación del cumplimiento de requisitos. |

---

# Observaciones

La matriz de trazabilidad es un documento vivo. Deberá mantenerse actualizada durante toda la ejecución del proyecto para asegurar que cada requisito tenga una implementación verificable, una prueba asociada y una relación directa con los objetivos del negocio y la arquitectura del Sistema de Gestión de Horarios SENA.