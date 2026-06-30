# Cross-Cutting

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Aspectos Transversales

## Propósito

Este documento define los aspectos transversales (Cross-Cutting Concerns) que aplican a todos los microservicios del Sistema de Gestión de Horarios SENA (SGH SENA).

Estos lineamientos garantizan consistencia técnica, seguridad, trazabilidad, observabilidad y mantenibilidad durante todo el ciclo de vida del sistema, independientemente del dominio funcional al que pertenezca cada servicio.

---

# Objetivos

- Estandarizar el comportamiento común de todos los microservicios.
- Garantizar la seguridad de la plataforma.
- Facilitar la observabilidad del sistema.
- Centralizar las políticas de auditoría.
- Uniformar el manejo de errores.
- Mejorar la mantenibilidad del software.
- Simplificar las tareas de operación y monitoreo.

---

# Seguridad

La seguridad es un componente transversal administrado por el módulo IAM.

Todos los microservicios deben delegar los procesos de autenticación y autorización al servicio correspondiente.

Las políticas de seguridad incluyen:

- Autenticación centralizada.
- Autorización basada en roles y permisos.
- Validación de identidad mediante tokens.
- Control de acceso a recursos.
- Expiración y renovación de sesiones.
- Protección de endpoints.
- Comunicación segura entre servicios.

---

# Autenticación

Todo usuario deberá autenticarse antes de acceder a funcionalidades protegidas.

Las solicitudes autenticadas deberán incluir el token de acceso correspondiente para validar la identidad del usuario.

Los servicios únicamente procesarán solicitudes cuya autenticación haya sido validada correctamente.

---

# Autorización

Cada operación del sistema deberá validar previamente los permisos del usuario autenticado.

Las autorizaciones estarán determinadas por:

- Rol.
- Permisos asignados.
- Estado del usuario.
- Restricciones funcionales propias del dominio.

---

# Auditoría

Todas las operaciones relevantes deberán generar registros de auditoría.

Como mínimo deberán registrarse:

- Usuario responsable.
- Fecha y hora.
- Servicio involucrado.
- Operación ejecutada.
- Recurso afectado.
- Resultado de la operación.

La información será administrada por el microservicio **Audit**.

---

# Logging

Todos los servicios deberán generar registros estructurados para facilitar el diagnóstico de incidentes.

Los eventos registrados incluirán, cuando aplique:

- Inicio de operaciones.
- Finalización de procesos.
- Errores.
- Advertencias.
- Eventos de negocio.
- Eventos de infraestructura.

No deberán registrarse credenciales, contraseñas ni información sensible.

---

# Observabilidad

La plataforma deberá proporcionar mecanismos que permitan conocer el estado operativo de los servicios.

Los componentes mínimos de observabilidad incluyen:

- Logs.
- Métricas.
- Estado de disponibilidad.
- Monitoreo de recursos.
- Alertas operativas.
- Trazabilidad de solicitudes.

---

# Manejo de errores

Todos los microservicios deberán implementar un mecanismo uniforme para el manejo de excepciones.

Las respuestas de error deberán:

- Utilizar códigos HTTP adecuados.
- Presentar mensajes claros.
- Evitar exponer información interna.
- Facilitar el diagnóstico por parte del cliente.

---

# Validaciones

Las validaciones deberán realizarse en la capa de aplicación antes de ejecutar cualquier regla de negocio.

Las validaciones comprenden:

- Datos obligatorios.
- Formatos válidos.
- Reglas de negocio.
- Integridad de referencias.
- Restricciones funcionales.

---

# Configuración

La configuración deberá mantenerse separada del código fuente.

Cada ambiente administrará su propia configuración mediante variables externas.

Entre ellas:

- Credenciales.
- Conexiones.
- Parámetros.
- Configuración de seguridad.
- Configuración de servicios externos.

---

# Comunicación entre servicios

Los microservicios se comunicarán exclusivamente mediante APIs REST.

No se permitirá:

- Acceso directo a bases de datos de otros servicios.
- Dependencias sobre implementaciones internas.
- Compartición de modelos de persistencia.

Toda integración deberá realizarse mediante contratos claramente definidos.

---

# Persistencia

Cada servicio administra su propia base de datos.

Las reglas generales son:

- Una base de datos por servicio.
- Independencia del modelo de datos.
- Migraciones independientes.
- Sin consultas cruzadas entre dominios.

---

# Trazabilidad

Cada solicitud deberá poder rastrearse a lo largo de su ciclo de vida.

La trazabilidad deberá permitir identificar:

- Usuario.
- Solicitud.
- Servicio ejecutado.
- Operación realizada.
- Fecha y hora.
- Resultado obtenido.

---

# Rendimiento

Todos los servicios deberán diseñarse considerando:

- Baja latencia.
- Uso eficiente de recursos.
- Escalabilidad horizontal.
- Respuesta consistente bajo carga.
- Optimización de consultas.

---

# Disponibilidad

La arquitectura debe minimizar puntos únicos de falla.

Cada microservicio podrá evolucionar, mantenerse y desplegarse sin afectar el funcionamiento del resto de la plataforma.

---

# Documentación

Todos los microservicios deberán mantener actualizada su documentación técnica, incluyendo:

- Endpoints.
- Casos de uso.
- Modelos de datos.
- Configuración.
- Dependencias.
- Cambios relevantes.

---

# Principios transversales

Todos los componentes del SGH SENA deberán cumplir los siguientes principios:

- Security by Design.
- API First.
- Clean Architecture.
- Domain-Driven Design.
- Alta cohesión.
- Bajo acoplamiento.
- Responsabilidad única.
- Independencia de despliegue.
- Independencia de datos.
- Observabilidad.
- Trazabilidad.
- Escalabilidad.

---

# Relación con la documentación

Los aspectos definidos en este documento complementan la arquitectura general del proyecto:

- **overview.md** define la estructura arquitectónica del sistema.
- **deployment.md** establece la estrategia de despliegue e infraestructura.
- **decisions/** documenta las decisiones arquitectónicas mediante ADR.

Este documento establece las políticas comunes que todos los microservicios deben adoptar para garantizar un comportamiento uniforme en toda la plataforma.