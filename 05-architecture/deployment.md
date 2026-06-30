# Deployment

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Estrategia de Despliegue

## Propósito

Este documento describe la estrategia de despliegue del Sistema de Gestión de Horarios SENA (SGH SENA), definiendo los ambientes, la topología de infraestructura, el ciclo de promoción entre entornos y las responsabilidades para la publicación de los diferentes microservicios.

El objetivo es garantizar despliegues controlados, repetibles y trazables durante todo el ciclo de vida del software.

---

# Objetivos

- Estandarizar el proceso de despliegue.
- Garantizar la separación entre ambientes.
- Permitir despliegues independientes por microservicio.
- Reducir riesgos durante la liberación de versiones.
- Facilitar la automatización mediante pipelines CI/CD.
- Mantener la disponibilidad y estabilidad del sistema.

---

# Arquitectura de despliegue

La solución está compuesta por múltiples microservicios desplegados de manera independiente.

Cada servicio posee:

- Aplicación independiente.
- Base de datos propia.
- Configuración propia.
- Versionamiento independiente.
- Escalabilidad independiente.

La comunicación entre servicios se realiza mediante APIs REST utilizando contratos previamente definidos.

---

# Ambientes

El proyecto dispone de cuatro ambientes principales.

| Ambiente | Propósito |
|----------|-----------|
| Develop | Desarrollo e integración continua de nuevas funcionalidades. |
| QA | Validación funcional, técnica e integración antes de la liberación. |
| Staging | Simulación del ambiente de producción para pruebas finales. |
| Production | Ambiente utilizado por los usuarios finales. |

Cada ambiente mantiene configuraciones independientes para garantizar el aislamiento entre etapas del ciclo de desarrollo.

---

# Flujo de promoción

El ciclo de promoción sigue el siguiente flujo:

```
Develop
      │
      ▼
QA
      │
      ▼
Staging
      │
      ▼
Production
```

Cada promoción requiere la aprobación correspondiente según el proceso definido por el equipo del proyecto.

---

# Estrategia de ramas

El despliegue está alineado con la estrategia Git del proyecto.

| Rama | Ambiente asociado |
|------|-------------------|
| develop | Desarrollo |
| qa | Calidad |
| staging | Preproducción |
| main | Producción |

Las ramas de funcionalidades (`feature/*`), correcciones (`hotfix/*`) y documentación (`docs/*`) se integran primero en `develop`, siguiendo posteriormente el flujo de promoción hasta producción.

---

# Componentes desplegados

Cada uno de los siguientes módulos constituye un microservicio desplegable de manera independiente.

| Servicio |
|-----------|
| IAM |
| Reference Data |
| Academic Management |
| Training Environment |
| Scheduling |
| Actors |
| Document Management |
| Monitoring |
| Audit |

Cada servicio mantiene independencia funcional y tecnológica respecto a los demás.

---

# Configuración

La configuración de cada ambiente se administra externamente al código fuente.

Incluye, entre otros:

- Variables de entorno.
- Cadenas de conexión.
- Credenciales.
- Configuración de seguridad.
- Parámetros de ejecución.
- Configuración de logging.
- Configuración de monitoreo.

La configuración nunca debe almacenarse dentro del código del proyecto.

---

# Base de datos

Cada microservicio administra su propia base de datos.

Durante el despliegue se deben ejecutar las migraciones correspondientes para mantener sincronizado el esquema de datos con la versión del servicio desplegado.

No se permite el acceso directo entre bases de datos pertenecientes a distintos microservicios.

---

# Automatización

El proceso de despliegue debe ser automatizado mediante pipelines de Integración Continua y Entrega Continua (CI/CD).

Las actividades automatizadas incluyen:

- Compilación.
- Ejecución de pruebas.
- Análisis de calidad.
- Empaquetado.
- Publicación de artefactos.
- Despliegue por ambiente.
- Verificaciones posteriores al despliegue.

---

# Versionamiento

Cada microservicio mantiene un versionamiento independiente.

Las nuevas versiones deben:

- Ser trazables.
- Estar asociadas a una rama.
- Estar relacionadas con una historia de usuario.
- Contar con registro de cambios.
- Haber superado las pruebas correspondientes.

---

# Disponibilidad

El despliegue debe minimizar la indisponibilidad del sistema.

Siempre que sea posible, las nuevas versiones deberán publicarse de forma independiente para evitar afectar otros servicios del ecosistema.

---

# Monitoreo posterior al despliegue

Después de cada liberación deberán verificarse como mínimo:

- Estado del servicio.
- Disponibilidad de la API.
- Conectividad con la base de datos.
- Registro de errores.
- Auditoría.
- Consumo de recursos.
- Alertas del sistema.
- Correcto funcionamiento de las integraciones.

---

# Recuperación

Ante una falla durante el despliegue deberá existir un procedimiento de reversión que permita restaurar la última versión estable del servicio afectado sin comprometer el funcionamiento de los demás microservicios.

---

# Relación con la arquitectura

La estrategia de despliegue implementa los principios definidos en la arquitectura general del proyecto:

- Despliegue independiente por microservicio.
- Base de datos por servicio.
- Escalabilidad horizontal.
- Desacoplamiento entre dominios.
- Automatización mediante CI/CD.
- Separación estricta de ambientes.
- Trazabilidad durante todo el ciclo de liberación.