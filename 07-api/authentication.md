# Authentication and Authorization

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Este documento define la estrategia de autenticación y autorización del Sistema de Gestión de Horarios SENA (SGH SENA).

Su objetivo es establecer un mecanismo uniforme y seguro para controlar el acceso a las APIs, proteger la información del sistema y garantizar que cada usuario únicamente pueda ejecutar las operaciones autorizadas según su rol y permisos.

Todas las APIs del proyecto deberán implementar estas directrices.

---

# Arquitectura de seguridad

La autenticación y autorización del sistema estará centralizada en el microservicio **IAM (Identity and Access Management)**.

Este servicio será responsable de:

- Gestión de usuarios.
- Gestión de roles.
- Gestión de permisos.
- Inicio y cierre de sesión.
- Emisión de tokens.
- Validación de credenciales.
- Renovación de sesiones.
- Revocación de accesos.

Ningún otro microservicio administrará usuarios o credenciales.

---

# Flujo de autenticación

El proceso general será el siguiente:

1. El usuario envía sus credenciales al servicio IAM.
2. IAM valida la identidad del usuario.
3. Si la autenticación es exitosa, se genera un Access Token.
4. El cliente almacena el token.
5. Cada solicitud posterior incluirá el token.
6. Los microservicios validarán el token antes de ejecutar cualquier operación protegida.

---

# Mecanismo de autenticación

El sistema utilizará autenticación basada en:

- JWT (JSON Web Token)

Los tokens serán emitidos únicamente por el microservicio IAM.

---

# Esquema de autorización

La autorización seguirá un modelo **RBAC (Role Based Access Control)**.

Cada usuario podrá tener uno o varios roles.

Cada rol dispondrá de un conjunto de permisos que determinarán las operaciones autorizadas dentro del sistema.

Ejemplo:

| Rol | Permisos |
|------|-----------|
| Administrador | Acceso total |
| Coordinador Académico | Gestión de programación académica |
| Instructor | Consulta y gestión de sus horarios |
| Aprendiz | Consulta de horarios asignados |
| Administrador de Ambientes | Gestión de ambientes y reservas |

---

# Envío del token

Todas las solicitudes autenticadas deberán incluir el encabezado HTTP:

```
Authorization: Bearer <token>
```

Ejemplo:

```
Authorization: Bearer eyJhbGciOiJIUzI1NiIsInR5cCI...
```

---

# Endpoints públicos

Las siguientes operaciones podrán estar disponibles sin autenticación, según la configuración del sistema:

- Inicio de sesión.
- Renovación de token.
- Verificación del estado del servicio.

Todos los demás endpoints requerirán autenticación.

---

# Validación del token

Antes de procesar cualquier solicitud protegida, cada microservicio deberá validar:

- Integridad del token.
- Firma digital.
- Fecha de expiración.
- Emisor autorizado.
- Audiencia válida.
- Estado del usuario.
- Permisos requeridos.

Las solicitudes con tokens inválidos deberán rechazarse inmediatamente.

---

# Expiración de sesiones

Los Access Token tendrán un tiempo de vida limitado.

Una vez expirados, el cliente deberá solicitar un nuevo token mediante el mecanismo definido por IAM.

No se permitirá el uso de tokens expirados.

---

# Comunicación entre microservicios

Las comunicaciones internas entre microservicios deberán realizarse mediante mecanismos autenticados.

Cada servicio deberá validar la identidad del servicio consumidor antes de procesar solicitudes internas.

No se permitirán llamadas internas anónimas.

---

# Seguridad del transporte

Todas las APIs deberán operar exclusivamente mediante HTTPS.

No se permitirá el intercambio de credenciales ni tokens sobre conexiones no cifradas.

---

# Manejo de credenciales

Las contraseñas deberán:

- Almacenarse cifradas utilizando algoritmos seguros.
- Nunca almacenarse en texto plano.
- Nunca registrarse en logs.
- Nunca enviarse por parámetros de URL.

---

# Manejo de errores de autenticación

| Código HTTP | Descripción |
|-------------|-------------|
| 401 Unauthorized | Usuario no autenticado o token inválido |
| 403 Forbidden | Usuario autenticado sin permisos suficientes |

---

# Principio de mínimo privilegio

Todo usuario dispondrá únicamente de los permisos estrictamente necesarios para desempeñar sus funciones.

Los permisos adicionales deberán asignarse mediante roles administrados por el servicio IAM.

---

# Auditoría

Los eventos relacionados con autenticación y autorización deberán registrarse para fines de auditoría.

Entre ellos:

- Inicio de sesión.
- Cierre de sesión.
- Intentos fallidos de autenticación.
- Revocación de tokens.
- Cambios de roles.
- Cambios de permisos.
- Accesos denegados.

Los registros serán consumidos por el microservicio de Auditoría del SGH SENA.

---

# Buenas prácticas

Todos los equipos deberán cumplir las siguientes recomendaciones:

- No exponer credenciales en código fuente.
- No almacenar tokens en repositorios.
- Utilizar HTTPS en todos los ambientes.
- Validar siempre el token antes de ejecutar lógica de negocio.
- Aplicar autorización basada en roles y permisos.
- Registrar eventos relevantes para auditoría.
- Mantener la configuración de seguridad centralizada en IAM.

---

# Relación con la arquitectura

Esta estrategia aplica a todos los microservicios del SGH SENA y complementa la documentación de:

- Arquitectura de Microservicios.
- API Guidelines.
- Contratos OpenAPI.
- Modelo de Dominio.
- Microservicio IAM.
- Microservicio Audit.

Cualquier modificación a este documento deberá ser aprobada por el equipo de Arquitectura antes de su adopción en los servicios del sistema.