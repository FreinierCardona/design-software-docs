# Backup and Recovery

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps, Operaciones e Infraestructura

## Propósito

Este documento establece la estrategia de respaldo y recuperación del Sistema de Gestión de Horarios SENA.

Su objetivo es definir los lineamientos para proteger la información, garantizar la continuidad operativa y permitir la recuperación controlada de los servicios ante fallos, errores operativos, incidentes de seguridad o eventos que comprometan la disponibilidad del sistema.

La estrategia de respaldo y recuperación forma parte del plan general de continuidad operativa del proyecto y complementa los procesos de observabilidad, gestión de incidentes y operación de la plataforma.

---

# Objetivos

La estrategia busca:

- Proteger la información del sistema.
- Reducir el riesgo de pérdida de datos.
- Garantizar la recuperación de los servicios.
- Minimizar el tiempo de interrupción.
- Mantener la continuidad del negocio.
- Definir responsabilidades durante los procesos de recuperación.
- Verificar periódicamente la capacidad de restauración.

---

# Alcance

La estrategia aplica a los activos tecnológicos que soportan el Sistema de Gestión de Horarios SENA, incluyendo:

- Bases de datos.
- Configuraciones de los microservicios.
- Archivos de configuración.
- Artefactos de despliegue.
- Documentación crítica.
- Recursos necesarios para restablecer la operación.

No incluye información temporal, datos de prueba ni respaldos personales de los integrantes del proyecto.

---

# Principios

La estrategia de respaldo deberá fundamentarse en los siguientes principios:

- Disponibilidad.
- Integridad.
- Confidencialidad.
- Recuperación verificable.
- Automatización cuando sea posible.
- Trazabilidad.
- Continuidad operativa.
- Mejora continua.

---

# Estrategia de respaldos

Los respaldos deberán planificarse de acuerdo con la criticidad de los componentes y las necesidades operativas del sistema.

La estrategia deberá definir, como mínimo:

- información que requiere respaldo;
- frecuencia de ejecución;
- política de retención;
- ubicación de almacenamiento;
- mecanismos de protección;
- procedimientos generales de restauración.

Cada microservicio conservará independencia sobre sus datos, respetando la arquitectura distribuida del proyecto.

---

# Recuperación del servicio

Ante una pérdida de información o indisisponibilidad de un componente, el proceso de recuperación deberá contemplar las siguientes etapas:

1. Identificación del incidente.
2. Evaluación del impacto.
3. Selección del respaldo adecuado.
4. Restauración controlada.
5. Validación de la información recuperada.
6. Verificación de la operación del servicio.
7. Cierre y documentación del evento.

Toda recuperación deberá registrarse para garantizar su trazabilidad.

---

# Objetivos de recuperación

La estrategia deberá establecer objetivos medibles para la recuperación del sistema, incluyendo:

| Concepto | Descripción |
|----------|-------------|
| RPO (Recovery Point Objective) | Define la cantidad máxima de información que puede perderse de forma aceptable antes de una recuperación. |
| RTO (Recovery Time Objective) | Define el tiempo máximo esperado para restablecer un servicio después de un incidente. |

Los valores específicos para cada componente deberán definirse conforme a su criticidad y a los requerimientos operativos del proyecto.

---

# Validación de respaldos

La existencia de un respaldo no garantiza su utilidad.

Por esta razón, deberán realizarse verificaciones periódicas que permitan confirmar:

- integridad de la información respaldada;
- disponibilidad de los archivos de respaldo;
- capacidad de restauración;
- consistencia de los datos recuperados;
- cumplimiento de los objetivos definidos para la recuperación.

---

# Responsabilidades

| Equipo | Responsabilidad |
|---------|-----------------|
| DevOps | Definir y mantener la estrategia de respaldos y recuperación. |
| Operaciones | Supervisar la ejecución de respaldos y coordinar los procesos de restauración cuando sean necesarios. |
| Desarrollo | Apoyar la validación funcional después de una recuperación. |
| Arquitectura | Garantizar que la estrategia sea consistente con la arquitectura del sistema y la independencia de los microservicios. |

---

# Buenas prácticas

La estrategia de respaldo deberá:

- mantener copias actualizadas de la información crítica;
- proteger los respaldos frente a accesos no autorizados;
- documentar todos los procedimientos de recuperación;
- verificar periódicamente la restauración de los respaldos;
- evitar depender de un único mecanismo de almacenamiento;
- evolucionar conforme crezca la plataforma.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de Operaciones.
- `observability.md`.
- `incident-management.md`.
- `ci-cd.md`.
- `environments.md`.
- Documentación de microservicios.
- Arquitectura del sistema.
- ADR (Architecture Decision Records).

---

# Mantenimiento

La estrategia de respaldo y recuperación deberá actualizarse cuando ocurra alguno de los siguientes cambios:

- incorporación de nuevos microservicios;
- modificación de la arquitectura de datos;
- cambios en la infraestructura;
- actualización de los objetivos de recuperación;
- incorporación de nuevos mecanismos de respaldo;
- evolución de las políticas de continuidad operativa.

Toda actualización deberá mantenerse alineada con la arquitectura, la estrategia DevOps y las políticas de continuidad del Sistema de Gestión de Horarios SENA.