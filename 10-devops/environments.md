# Environments

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps e Infraestructura

## Propósito

Este documento describe la estrategia de ambientes utilizada por el Sistema de Gestión de Horarios SENA.

Su objetivo es establecer el propósito, alcance y reglas de utilización de cada ambiente disponible durante el ciclo de vida del software, garantizando un proceso de desarrollo, validación y despliegue controlado, reproducible y alineado con la arquitectura del proyecto.

---

# Objetivos

La documentación de ambientes permite:

- Definir claramente el propósito de cada entorno.
- Establecer responsabilidades sobre su utilización.
- Reducir riesgos durante los despliegues.
- Garantizar una progresión controlada de los cambios.
- Facilitar la validación antes de llegar a producción.
- Mantener consistencia entre todos los equipos.

---

# Estrategia de ambientes

El proyecto organiza sus ambientes de manera progresiva, permitiendo que cada cambio atraviese diferentes niveles de validación antes de ser liberado.

La promoción entre ambientes deberá respetar el flujo definido por la estrategia de ramas y los controles de calidad establecidos para el proyecto.

---

# Ambientes del proyecto

| Ambiente | Propósito | Rama asociada | Acceso |
|----------|-----------|---------------|--------|
| Desarrollo | Integración continua de nuevas funcionalidades y cambios en construcción. | `develop` | Equipo de Desarrollo |
| QA | Validación técnica, pruebas funcionales e integración entre componentes. | `qa` | Desarrollo y QA |
| Staging | Simulación del entorno de producción para validaciones finales. | `staging` | Arquitectura, QA y DevOps |
| Producción | Ambiente oficial utilizado por los usuarios finales. | `main` | DevOps |

---

# Flujo de promoción

Todo cambio deberá seguir el siguiente recorrido:

```
Desarrollo
      │
      ▼
QA
      │
      ▼
Staging
      │
      ▼
Producción
```

Cada transición deberá cumplir los criterios de calidad definidos para el proyecto antes de continuar hacia el siguiente ambiente.

---

# Responsabilidades

Cada ambiente posee un objetivo específico y deberá utilizarse únicamente para las actividades correspondientes.

| Ambiente | Actividades permitidas |
|----------|------------------------|
| Desarrollo | Construcción de funcionalidades, integración y pruebas iniciales. |
| QA | Validación funcional, integración y verificación de requisitos. |
| Staging | Validación previa a producción y pruebas de aceptación. |
| Producción | Operación oficial del sistema y atención de incidencias. |

---

# Reglas generales

Todos los ambientes deberán cumplir los siguientes lineamientos:

- Mantener una configuración consistente con la arquitectura del proyecto.
- Utilizar únicamente versiones controladas del software.
- Registrar los despliegues realizados.
- Permitir la trazabilidad entre versiones y cambios.
- Respetar la estrategia oficial de ramas.
- Evitar modificaciones manuales no documentadas.

---

# Gestión de configuración

Cada ambiente podrá disponer de configuraciones particulares cuando sean necesarias para su propósito.

Estas diferencias deberán:

- encontrarse documentadas;
- mantenerse bajo control de versiones cuando corresponda;
- no afectar el comportamiento funcional esperado del sistema;
- respetar los estándares de seguridad establecidos.

---

# Seguridad

La administración de los ambientes deberá garantizar que:

- las credenciales sean independientes para cada entorno;
- los datos sensibles permanezcan protegidos;
- el acceso se otorgue únicamente a personal autorizado;
- las configuraciones críticas sean auditables.

---

# Relación con la estrategia de ramas

La estrategia de ambientes está alineada con el modelo de ramas definido para el proyecto.

Cada ambiente recibe cambios únicamente desde la rama correspondiente, siguiendo el flujo de promoción establecido por la gobernanza del desarrollo.

Las políticas relacionadas con creación de ramas, integración de cambios y liberación de versiones se documentan en la sección de gobernanza del proyecto.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de DevOps.
- `local-setup.md`.
- `ci-cd.md`.
- Estrategia de ramas.
- Arquitectura del sistema.
- Documentación de despliegue.
- ADR relacionados.

---

# Mantenimiento

La documentación de ambientes deberá actualizarse cuando ocurra alguno de los siguientes cambios:

- incorporación de nuevos ambientes;
- modificación del flujo de promoción;
- cambios en la estrategia de despliegue;
- actualización de la estrategia de ramas;
- modificación de responsabilidades operativas.

Toda actualización deberá mantenerse alineada con la arquitectura y las políticas de gobernanza del Sistema de Gestión de Horarios SENA.