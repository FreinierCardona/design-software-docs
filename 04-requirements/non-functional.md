# Requisitos No Funcionales

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

# Propósito

Este documento define los requisitos no funcionales (RNF) del Sistema de Gestión de Horarios SENA (SGH SENA), estableciendo los atributos de calidad que deberá cumplir la solución durante todo su ciclo de vida.

Estos requisitos garantizan que el sistema no solamente funcione correctamente, sino que además sea seguro, confiable, mantenible, escalable y disponible para los diferentes centros de formación del SENA.

---

# Alcance

Los requisitos no funcionales aplican a todos los componentes del sistema:

- Backend
- Frontend Web
- Aplicación móvil
- Microservicios
- Bases de datos
- APIs
- Infraestructura
- Seguridad
- Integraciones
- Procesos de despliegue

---

# Convenciones

Todos los requisitos no funcionales utilizan el prefijo:

RNF-XXX

Ejemplo:

- RNF-001
- RNF-015
- RNF-030

Cada requisito deberá ser verificable mediante pruebas técnicas o métricas objetivas.

---

# Requisitos No Funcionales

## Seguridad

### RNF-001
El sistema deberá autenticar todos los usuarios mediante mecanismos seguros.

### RNF-002
Toda comunicación deberá realizarse mediante HTTPS/TLS.

### RNF-003
Las contraseñas deberán almacenarse utilizando algoritmos de hash seguros.

### RNF-004
El sistema deberá implementar autorización basada en roles y permisos (RBAC).

### RNF-005
Todas las operaciones críticas deberán registrarse en auditoría.

### RNF-006
Los tokens de autenticación deberán poseer tiempo de expiración configurable.

---

## Disponibilidad

### RNF-007
El sistema deberá estar disponible al menos el 99.5% del tiempo anual.

### RNF-008
Los servicios deberán recuperarse automáticamente ante fallos controlados.

### RNF-009
Las tareas de mantenimiento deberán minimizar la indisponibilidad del sistema.

---

## Rendimiento

### RNF-010
Las consultas habituales deberán responder en menos de 2 segundos.

### RNF-011
La generación de horarios deberá completarse en tiempos aceptables según la cantidad de información procesada.

### RNF-012
Las APIs deberán soportar múltiples solicitudes concurrentes sin degradación significativa del servicio.

---

## Escalabilidad

### RNF-013
La arquitectura deberá permitir el crecimiento independiente de cada microservicio.

### RNF-014
Los servicios deberán soportar escalamiento horizontal.

### RNF-015
La solución deberá permitir incorporar nuevos módulos sin afectar los existentes.

---

## Confiabilidad

### RNF-016
La información almacenada deberá mantener integridad durante toda su vida útil.

### RNF-017
Las transacciones críticas deberán garantizar consistencia de los datos.

### RNF-018
El sistema deberá prevenir pérdida de información ante fallos inesperados.

---

## Mantenibilidad

### RNF-019
La solución deberá seguir una arquitectura modular basada en microservicios.

### RNF-020
Cada servicio deberá mantener independencia funcional y de datos.

### RNF-021
El código deberá seguir estándares de desarrollo definidos por el proyecto.

### RNF-022
Toda funcionalidad deberá estar documentada.

---

## Compatibilidad

### RNF-023
El sistema deberá ser compatible con los navegadores modernos.

### RNF-024
La aplicación móvil deberá operar sobre versiones soportadas de Android.

### RNF-025
Las APIs deberán seguir principios REST.

---

## Usabilidad

### RNF-026
La interfaz deberá ser intuitiva y consistente para todos los usuarios.

### RNF-027
Las acciones críticas deberán proporcionar mensajes claros al usuario.

### RNF-028
El sistema deberá minimizar la cantidad de pasos necesarios para realizar tareas frecuentes.

---

## Auditoría

### RNF-029
Todas las operaciones relevantes deberán quedar registradas con fecha, hora y usuario.

### RNF-030
Los registros de auditoría no podrán modificarse por usuarios finales.

---

## Disponibilidad de Datos

### RNF-031
Cada microservicio deberá administrar su propia base de datos.

### RNF-032
Los datos deberán respaldarse periódicamente.

### RNF-033
Los mecanismos de recuperación deberán permitir restaurar la información ante incidentes.

---

## Observabilidad

### RNF-034
El sistema deberá generar registros (logs) estructurados.

### RNF-035
Los servicios deberán exponer métricas para monitoreo.

### RNF-036
Los errores deberán poder rastrearse mediante identificadores de correlación.

---

## Configuración

### RNF-037
Los parámetros del sistema deberán ser configurables sin modificar el código fuente.

### RNF-038
Los ambientes de Desarrollo, QA, Staging y Producción deberán mantener configuraciones independientes.

---

## Calidad del Software

### RNF-039
Todo componente deberá contar con pruebas automatizadas cuando sea posible.

### RNF-040
Cada cambio deberá ser trazable mediante control de versiones.

### RNF-041
La documentación deberá mantenerse sincronizada con la evolución del sistema.

### RNF-042
El sistema deberá seguir los principios de Clean Architecture y separación por módulos.

---

# Métricas de Calidad

| Atributo | Objetivo |
|----------|----------|
| Disponibilidad | ≥ 99.5% |
| Tiempo de respuesta promedio | ≤ 2 segundos |
| Comunicación | HTTPS |
| Arquitectura | Microservicios |
| Autenticación | JWT/OAuth2 según implementación |
| Auditoría | Obligatoria |
| Escalabilidad | Horizontal |
| Base de datos | Independiente por servicio |
| Versionamiento | Git + GitFlow del proyecto |
| Documentación | Obligatoria para todos los módulos |

---

# Relación con otros documentos

| Documento | Relación |
|------------|----------|
| Requisitos Funcionales | Define el comportamiento del sistema. |
| Arquitectura de Software | Implementa los atributos de calidad definidos. |
| ADR | Documenta las decisiones técnicas. |
| Modelo de Dominio | Define las entidades del negocio. |
| Plan de Pruebas | Valida el cumplimiento de los RNF. |
| Matriz de Trazabilidad | Relaciona requisitos, implementación y pruebas. |

---

# Observaciones

Los requisitos no funcionales constituyen restricciones y atributos de calidad aplicables a toda la plataforma. Cualquier modificación arquitectónica deberá preservar el cumplimiento de estos requisitos y mantener la trazabilidad con las decisiones técnicas y los casos de prueba correspondientes.