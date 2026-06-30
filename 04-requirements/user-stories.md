# Historias de Usuario

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Propósito

Este documento define la estructura, organización y gestión de las historias de usuario del Sistema de Gestión de Horarios SENA (SGH SENA).

Las historias de usuario representan las necesidades funcionales del negocio desde la perspectiva de los diferentes actores del sistema y constituyen la unidad principal de trabajo dentro del Product Backlog.

Cada historia deberá mantener trazabilidad con los requisitos funcionales, casos de uso, componentes de arquitectura y pruebas correspondientes.

---

# Objetivos

Las historias de usuario permiten:

- Describir funcionalidades desde la perspectiva del usuario.
- Dividir el producto en entregas incrementales.
- Facilitar la planificación de los Sprint.
- Priorizar funcionalidades según valor de negocio.
- Mantener trazabilidad durante el desarrollo.
- Servir como base para los criterios de aceptación y pruebas funcionales.

---

# Formato Estándar

Todas las historias de usuario deberán seguir la siguiente estructura:

```text
Como <actor>

Quiero <funcionalidad>

Para <beneficio de negocio>
```

Ejemplo:

```text
Como Coordinador Académico

Quiero generar horarios automáticamente

Para reducir el tiempo requerido en la programación académica.
```

---

# Estructura de una Historia

Cada historia deberá contener:

- Identificador (HU-XXX)
- Título
- Descripción
- Actor
- Prioridad
- Módulo
- Requisitos relacionados
- Criterios de aceptación
- Dependencias
- Estado
- Sprint asignado

---

# Identificadores

Las historias utilizan el siguiente formato:

```
HU-001
HU-002
HU-003
...
```

Los identificadores son únicos y permanentes.

---

# Actores del Sistema

Las historias podrán estar asociadas a los siguientes actores:

- Administrador del Sistema
- Coordinador Académico
- Instructor
- Aprendiz
- Personal Administrativo
- Responsable de Ambientes
- Equipo de Seguimiento
- Auditor
- Empresa vinculada a etapa productiva

---

# Clasificación por Módulos

Las historias de usuario se organizan de acuerdo con los módulos funcionales del proyecto.

| Módulo | Descripción |
|---------|-------------|
| IAM | Gestión de usuarios, autenticación, roles y permisos. |
| Reference Data | Administración de parámetros, catálogos, estados y centros de formación. |
| Academic Management | Gestión de programas, competencias, RAP, fichas y ofertas. |
| Training Environment | Administración de ambientes, reservas, disponibilidad e inventario. |
| Scheduling | Programación de horarios, sesiones, asignaciones y conflictos. |
| Actors | Gestión de instructores, aprendices, empresas y etapa productiva. |
| Document | Gestión documental, versiones y plantillas institucionales. |
| Monitoring | Seguimiento académico, indicadores, alertas y notificaciones. |
| Audit | Registro y consulta de auditoría del sistema. |

---

# Priorización

Las historias podrán clasificarse según su prioridad.

| Prioridad | Descripción |
|------------|-------------|
| Alta | Funcionalidad indispensable para el funcionamiento del sistema. |
| Media | Funcionalidad importante que aporta valor al negocio. |
| Baja | Funcionalidad complementaria o de mejora. |

---

# Criterios de Aceptación

Cada historia deberá definir criterios verificables que permitan validar su cumplimiento.

Ejemplo:

- El usuario autenticado puede acceder a la funcionalidad.
- La información se almacena correctamente.
- El sistema valida los datos obligatorios.
- Se registran los eventos de auditoría.
- La operación finaliza sin errores.

---

# Trazabilidad

Toda historia de usuario deberá relacionarse con:

- Uno o más requisitos funcionales (RF).
- Requisitos no funcionales cuando corresponda.
- Casos de uso.
- Módulo funcional.
- Microservicio.
- Casos de prueba.
- Sprint del Product Backlog.

---

# Flujo de Gestión

Las historias seguirán el siguiente ciclo de vida:

```
Propuesta
      │
      ▼
Refinamiento
      │
      ▼
Priorización
      │
      ▼
Planificación del Sprint
      │
      ▼
Desarrollo
      │
      ▼
Pruebas
      │
      ▼
Aceptación
      │
      ▼
Finalizada
```

---

# Relación con otros documentos

| Documento | Relación |
|------------|----------|
| Functional Requirements | Origen de las funcionalidades implementadas. |
| Non Functional Requirements | Restricciones y atributos de calidad asociados. |
| Product Backlog | Planificación y priorización de las historias. |
| Product Definition | Define la visión y objetivos del producto. |
| Casos de Uso | Describe el comportamiento esperado de cada historia. |
| Arquitectura | Implementación técnica de las funcionalidades. |
| Matriz de Trazabilidad | Relaciona historias con requisitos, pruebas y arquitectura. |

---

# Convenciones

Todas las historias deberán cumplir las siguientes reglas:

- Deben aportar valor al negocio.
- Deben ser independientes cuando sea posible.
- Deben ser negociables.
- Deben ser estimables.
- Deben ser pequeñas para ser implementadas en un Sprint.
- Deben ser verificables mediante criterios de aceptación.
- Deben mantener trazabilidad con el resto de la documentación.

---

# Observaciones

Las historias de usuario representan la unidad de trabajo del Product Backlog y evolucionarán durante el desarrollo del proyecto. Este documento define las reglas generales para su elaboración y gestión, mientras que el detalle de cada historia, su estado, prioridad y planificación se administra dentro del Product Backlog del proyecto.