# Dependencies

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura y Gestión del Proyecto

## Propósito

Este documento registra las dependencias identificadas durante el desarrollo del Sistema de Gestión de Horarios SENA.

Su objetivo es proporcionar visibilidad sobre las relaciones existentes entre módulos, microservicios, equipos, componentes externos y entregables, facilitando la planificación del trabajo, la identificación de bloqueos y la coordinación entre los diferentes participantes del proyecto.

Las dependencias documentadas permiten comprender qué elementos requieren estar disponibles antes de iniciar o completar una determinada actividad.

---

# Objetivos

La documentación de dependencias busca:

- Identificar relaciones entre componentes del proyecto.
- Reducir bloqueos durante el desarrollo.
- Facilitar la planificación técnica.
- Mejorar la coordinación entre equipos.
- Documentar dependencias externas.
- Mantener trazabilidad sobre las relaciones del sistema.

---

# Alcance

Este documento registra dependencias relacionadas con:

- Microservicios.
- Módulos funcionales.
- Equipos de trabajo.
- APIs.
- Integraciones.
- Servicios externos.
- Infraestructura.
- Entregables del proyecto.

No documenta dependencias de bibliotecas, frameworks o gestores de paquetes utilizados por el software.

---

# Clasificación

Las dependencias podrán clasificarse en las siguientes categorías.

| Tipo | Descripción |
|------|-------------|
| Funcional | Una funcionalidad requiere otra previamente implementada. |
| Técnica | Un componente depende de otro para su funcionamiento. |
| Arquitectónica | La relación surge por decisiones de arquitectura o diseño. |
| Externa | Depende de un sistema, proveedor o servicio ajeno al proyecto. |
| Organizacional | Requiere coordinación entre equipos o áreas. |

---

# Dependencias entre microservicios

Las relaciones entre microservicios deberán documentarse cuando un servicio consuma información, publique eventos o dependa de otro para completar un proceso de negocio.

Las dependencias deberán minimizarse para preservar el bajo acoplamiento propio de la arquitectura basada en microservicios.

Cuando sea posible, deberán preferirse mecanismos que reduzcan el acoplamiento entre servicios.

---

# Dependencias externas

Cuando el sistema dependa de plataformas, servicios o componentes externos, deberá registrarse la información necesaria para comprender el impacto de dicha dependencia sobre el proyecto.

Entre ellas podrán encontrarse:

- servicios institucionales;
- proveedores de autenticación;
- servicios de correo;
- plataformas de mensajería;
- servicios de almacenamiento;
- otras integraciones autorizadas.

---

# Dependencias organizacionales

Algunas actividades podrán depender del trabajo realizado por otros equipos del proyecto.

Estas dependencias deberán identificarse oportunamente para facilitar la coordinación entre:

- Producto.
- Arquitectura.
- Desarrollo.
- QA.
- DevOps.
- Operaciones.
- Soporte.

---

# Registro de dependencias

| ID | Dependencia | Tipo | Componentes involucrados | Impacto | Estado | Observaciones |
|----|-------------|------|--------------------------|---------|--------|---------------|

---

# Gestión de dependencias

Toda dependencia registrada deberá:

- tener un responsable identificado;
- mantenerse actualizada;
- revisarse periódicamente;
- eliminarse cuando deje de existir;
- documentar el impacto que genera sobre el proyecto.

---

# Buenas prácticas

Se recomienda:

- minimizar dependencias innecesarias;
- favorecer el desacoplamiento entre componentes;
- identificar dependencias desde las etapas de diseño;
- documentar oportunamente nuevas relaciones;
- revisar periódicamente el impacto de las dependencias existentes.

---

# Relación con otros documentos

Este documento complementa:

- `technical-backlog.md`
- `risks.md`
- `open-questions.md`
- Arquitectura.
- ADR (Architecture Decision Records).
- Microservicios.
- DevOps.

---

# Mantenimiento

El registro de dependencias deberá actualizarse cuando ocurra alguno de los siguientes eventos:

- incorporación de nuevos microservicios;
- creación de nuevas integraciones;
- modificación de la arquitectura;
- cambios en proveedores o servicios externos;
- aparición o eliminación de dependencias entre equipos;
- evolución del alcance del proyecto.

Toda actualización deberá mantenerse alineada con la arquitectura, la planificación y la estrategia de desarrollo del Sistema de Gestión de Horarios SENA.