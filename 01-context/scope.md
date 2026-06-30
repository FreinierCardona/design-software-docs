# Alcance

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Sistema de Gestión de Horarios SENA |

## En alcance

El Sistema de Gestión de Horarios SENA (SGH SENA) tiene como finalidad administrar de manera centralizada la programación académica de los Centros de Formación del SENA, integrando los diferentes procesos y actores involucrados en la planeación, asignación, seguimiento y control de los horarios institucionales.

El alcance funcional del sistema comprende:

### Gestión de identidad y acceso

- Administración de usuarios.
- Administración de roles y permisos.
- Gestión de autenticación y autorización.
- Administración de sesiones activas.
- Gestión de tokens de acceso.
- Control de acceso basado en roles (RBAC).

### Gestión de datos maestros

- Administración de centros de formación.
- Administración de regionales y macroregiones.
- Gestión de catálogos institucionales.
- Administración de estados del sistema.
- Configuración de parámetros generales.

### Gestión académica

- Administración de programas de formación.
- Gestión de competencias.
- Gestión de Resultados de Aprendizaje (RAP).
- Administración de fichas.
- Gestión de ofertas de formación.
- Relación entre programas, competencias y fichas.

### Gestión de infraestructura

- Administración de ambientes de formación.
- Administración del inventario asociado a cada ambiente.
- Gestión de recursos físicos y tecnológicos.
- Registro de mantenimientos.
- Gestión de disponibilidad de ambientes.
- Administración de reservas.
- Control de traslados de recursos.
- Seguimiento de novedades relacionadas con infraestructura.

### Gestión de horarios

- Creación de horarios académicos.
- Administración de franjas horarias.
- Programación de sesiones de clase.
- Asignación de instructores.
- Asignación de ambientes.
- Asignación de fichas.
- Validación automática de conflictos.
- Gestión de modificaciones y reprogramaciones.
- Publicación de horarios.

### Gestión de actores

- Administración de instructores.
- Administración de aprendices.
- Gestión de empresas.
- Registro de etapa productiva.
- Seguimiento mediante bitácoras.

### Gestión documental

- Administración de documentos.
- Control de versiones.
- Gestión de plantillas institucionales.
- Asociación de documentos con procesos académicos.

### Seguimiento y monitoreo

- Gestión de indicadores (KPI).
- Generación de alertas.
- Administración de notificaciones.
- Seguimiento a procesos.
- Gestión de planes de mejoramiento.

### Auditoría

- Registro histórico de operaciones.
- Trazabilidad de cambios.
- Consulta de eventos de auditoría.
- Conservación del historial de modificaciones.

### Arquitectura

El sistema será desarrollado bajo una arquitectura basada en microservicios, donde cada dominio funcional implementará:

- Base de datos independiente.
- API propia.
- Lógica de negocio desacoplada.
- Implementación mediante Clean Architecture.
- Comunicación mediante contratos bien definidos.

---

# Fuera de alcance

El SGH SENA no contempla dentro del alcance actual las siguientes funcionalidades:

### Gestión académica institucional

- Matrícula de aprendices.
- Inscripción a programas de formación.
- Registro de calificaciones.
- Evaluación académica.
- Certificación de aprendices.
- Gestión curricular institucional.

### Gestión administrativa

- Nómina de funcionarios.
- Gestión financiera.
- Contabilidad.
- Presupuesto institucional.
- Tesorería.
- Compras institucionales.

### Gestión de talento humano

- Contratación de personal.
- Evaluación de desempeño laboral.
- Liquidación de contratos.
- Administración salarial.

### Infraestructura tecnológica

- Administración de servidores.
- Monitoreo de infraestructura TI.
- Gestión de redes.
- Administración de equipos informáticos institucionales.

### Integraciones externas

Durante la primera versión no se contempla integración directa con:

- SOFIA Plus.
- Plataformas ERP.
- Sistemas financieros.
- Sistemas de nómina.
- Plataformas gubernamentales.
- Directorios institucionales externos.

Estas integraciones podrán ser consideradas en futuras fases del proyecto.

---

# Supuestos

El proyecto parte de los siguientes supuestos funcionales y técnicos:

- Los usuarios serán previamente registrados por un administrador autorizado.
- Toda la información académica suministrada será válida y actualizada.
- Cada ficha pertenece a un único programa de formación.
- Cada instructor tendrá disponibilidad previamente definida.
- Cada ambiente dispondrá de una capacidad máxima registrada.
- Los recursos estarán asociados a un ambiente determinado.
- La infraestructura institucional será previamente parametrizada.
- Los datos maestros serán administrados antes de iniciar la programación académica.
- Cada microservicio será responsable exclusivamente de su propio dominio de negocio.
- Cada microservicio administrará de forma independiente su propia base de datos.
- La comunicación entre servicios utilizará contratos previamente definidos.
- Todas las operaciones relevantes serán registradas mediante auditoría.
- Los usuarios accederán únicamente según los permisos asignados por el módulo IAM.

---

# Restricciones

El desarrollo y funcionamiento del sistema estará sujeto a las siguientes restricciones:

### Institucionales

- Cumplimiento de la normativa vigente del SENA.
- Cumplimiento de lineamientos institucionales para programación académica.
- Respeto de la estructura organizacional del SENA.

### Funcionales

- Un ambiente no podrá estar asignado simultáneamente a más de una sesión.
- Un instructor no podrá impartir dos sesiones en el mismo horario.
- Una ficha no podrá asistir simultáneamente a diferentes sesiones.
- Un recurso reservado no podrá ser asignado a otra actividad durante el mismo intervalo.
- No podrán publicarse horarios con conflictos activos.

### Arquitectónicas

- Arquitectura basada en microservicios.
- Implementación mediante Clean Architecture.
- Base de datos independiente por microservicio.
- Bajo acoplamiento entre servicios.
- Alta cohesión dentro de cada dominio.
- Comunicación exclusivamente mediante APIs o mecanismos definidos por la arquitectura.

### Técnicas

- Todos los datos deberán ser auditables.
- El sistema deberá garantizar trazabilidad de las operaciones.
- Las reglas de negocio deberán implementarse en la capa de dominio.
- Las bases de datos no compartirán tablas entre microservicios.
- Los cambios deberán administrarse mediante control de versiones (Git).
- El desarrollo seguirá las convenciones definidas por la gobernanza del proyecto.

### Seguridad

- Acceso autenticado para todos los usuarios.
- Autorización basada en roles y permisos.
- Protección de la información institucional.
- Registro de eventos críticos de seguridad.
- Gestión segura de sesiones y credenciales.