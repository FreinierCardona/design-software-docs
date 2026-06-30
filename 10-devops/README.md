# DevOps

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps e Infraestructura

## Propósito

Esta sección centraliza la documentación relacionada con las prácticas DevOps del Sistema de Gestión de Horarios SENA.

Su objetivo es documentar los procesos necesarios para preparar entornos de desarrollo, administrar los ambientes del proyecto, automatizar la integración y el despliegue continuo, y establecer los lineamientos operativos que garanticen una entrega de software consistente y confiable.

La documentación aquí contenida constituye la referencia oficial para la operación del ciclo de vida de desarrollo e implementación del sistema.

---

# Objetivos

Esta documentación permite:

- Estandarizar la preparación del entorno de desarrollo.
- Documentar el flujo de integración y despliegue continuo.
- Definir el propósito de cada ambiente.
- Facilitar la incorporación de nuevos integrantes.
- Garantizar la reproducibilidad de los procesos.
- Mantener consistencia entre desarrollo, pruebas y producción.

---

# Alcance

La documentación DevOps comprende:

- Preparación del entorno local.
- Gestión de ambientes.
- Integración continua (CI).
- Despliegue continuo (CD).
- Estrategias de despliegue.
- Controles automáticos de calidad.
- Buenas prácticas operativas.

No documenta configuraciones específicas de infraestructura, scripts internos ni información sensible.

---

# Organización

```text
10-devops/
│
├── README.md
├── local-setup.md
├── ci-cd.md
└── environments.md
```

---

# Principios

Las prácticas DevOps del proyecto se fundamentan en los siguientes principios:

- Automatización.
- Reproducibilidad.
- Integración continua.
- Entrega continua.
- Calidad desde el origen.
- Trazabilidad.
- Seguridad.
- Observabilidad.
- Versionamiento controlado.

---

# Flujo general

El ciclo de vida del software contempla de forma general:

1. Preparación del entorno local.
2. Desarrollo de funcionalidades.
3. Validación mediante controles automáticos.
4. Integración continua.
5. Despliegue hacia ambientes de prueba.
6. Validación funcional.
7. Liberación hacia producción.

Cada etapa deberá respetar las políticas de calidad y gobernanza definidas para el proyecto.

---

# Relación con la arquitectura

La documentación DevOps complementa:

- Arquitectura del sistema.
- Documentación de microservicios.
- Estrategia de ramas.
- ADR.
- Observabilidad.
- Seguridad.
- Gobernanza del proyecto.

---

# Archivos relacionados

| Archivo | Descripción | Estado |
|----------|-------------|--------|
| local-setup.md | Preparación y configuración del entorno local de desarrollo. | 🟢 |
| ci-cd.md | Estrategia de integración continua, despliegue continuo y controles automatizados. | 🟢 |
| environments.md | Definición de ambientes, propósito, responsabilidades y reglas de utilización. | 🟢 |

---

# Mantenimiento

La documentación de esta sección deberá actualizarse cada vez que se modifique alguno de los siguientes aspectos:

- Flujo de desarrollo.
- Estrategia de despliegue.
- Ambientes.
- Automatizaciones.
- Herramientas DevOps.
- Políticas operativas.

Toda actualización deberá mantenerse alineada con la arquitectura y las prácticas definidas para el Sistema de Gestión de Horarios SENA.