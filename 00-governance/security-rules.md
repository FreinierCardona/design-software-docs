# Seguridad Documental

> Estado: 🟢 Aprobado |
> Última actualización: 2026-06-23 |
> Autor: Equipo de Arquitectura |
> Equipo: Sistema de Gestión de Horarios SENA

---

# Objetivo

Definir las reglas de seguridad aplicables a toda la documentación almacenada en el repositorio del Sistema de Gestión de Horarios SENA.

Estas reglas buscan prevenir:

* Exposición de información sensible.
* Filtración de credenciales.
* Divulgación de datos personales.
* Publicación accidental de información interna.
* Riesgos de seguridad derivados de documentación incorrecta.

---

# Alcance

Aplica a:

* Documentos Markdown.
* Diagramas.
* ADRs.
* Contratos API.
* Modelos de datos.
* Capturas de pantalla.
* Mockups.
* Archivos adjuntos.
* Recursos visuales.
* Ejemplos de código.
* Archivos de configuración documentados.

---

# Principio general

> Ningún documento del repositorio debe contener información que pueda comprometer la seguridad del proyecto, la privacidad de los usuarios o la operación de los sistemas asociados.

---

# Información prohibida

La siguiente información no puede almacenarse bajo ninguna circunstancia dentro del repositorio.

## Credenciales y secretos

Prohibido publicar:

* Contraseñas.
* Tokens de acceso.
* JWT reales.
* API Keys.
* Secret Keys.
* Client Secrets.
* Llaves privadas.
* Certificados productivos.
* Credenciales de bases de datos.
* Credenciales de servicios externos.

Ejemplos prohibidos:

```text
Bearer eyJhbGciOi...
postgres://admin:password123@host
AWS_SECRET_ACCESS_KEY=XXXXXX
```

---

## Archivos sensibles

No subir:

```text
.env
.env.local
.env.prod
.pem
.key
.p12
.pfx
.jks
.kdbx
```

Tampoco:

* Backups de producción.
* Exportaciones de bases de datos reales.
* Archivos de configuración con secretos.

---

## Datos personales

No documentar información real de:

* Aprendices.
* Instructores.
* Administrativos.
* Coordinadores.
* Empresas.
* Usuarios finales.

Prohibido publicar:

* Nombres completos reales.
* Correos electrónicos reales.
* Teléfonos.
* Direcciones.
* Documentos de identidad.
* Información laboral privada.
* Datos académicos identificables.

---

## Infraestructura interna

No publicar:

* Direcciones IP privadas.
* DNS internos.
* Nombres reales de servidores.
* Configuraciones internas de red.
* Rutas privadas.
* Topologías de red productivas.

Ejemplos prohibidos:

```text
10.10.15.25
172.16.10.1
db-prod-sena.internal
vpn.sena.local
```

---

## Información operativa sensible

No documentar:

* Procedimientos para evadir controles de seguridad.
* Métodos de acceso privilegiado.
* Configuraciones administrativas productivas.
* Procedimientos de recuperación con credenciales reales.
* Información clasificada como confidencial.

---

# Valores seguros para ejemplos

Toda documentación debe utilizar datos ficticios.

| Caso                | Valor recomendado                        |
| ------------------- | ---------------------------------------- |
| Correo electrónico  | `usuario@example.com`                    |
| URL                 | `https://example.com/api`                |
| Token               | `TOKEN_DE_EJEMPLO`                       |
| JWT                 | `JWT_DE_EJEMPLO`                         |
| UUID                | `00000000-0000-0000-0000-000000000000`   |
| Documento           | `1234567890` (indicando que es ficticio) |
| Empresa             | `Empresa Ejemplo SAS`                    |
| Servicio            | `scheduling-service`                     |
| Centro de formación | `Centro de Formación Ejemplo`            |

---

# Seguridad en diagramas

Antes de publicar diagramas verificar que no existan:

* Contraseñas.
* Tokens.
* URLs privadas.
* Nombres reales de usuarios.
* Direcciones IP internas.
* Configuraciones sensibles.

---

# Seguridad en capturas de pantalla

## Verificaciones obligatorias

Antes de subir una captura:

* [ ] No contiene nombres reales.
* [ ] No contiene correos reales.
* [ ] No contiene documentos reales.
* [ ] No contiene sesiones activas.
* [ ] No contiene tokens.
* [ ] No contiene credenciales.
* [ ] No contiene información confidencial.

---

## Ubicación permitida

Las capturas deben almacenarse únicamente en:

```text
assets/images/
```

---

## Reglas

* Utilizar únicamente imágenes necesarias.
* Recortar información irrelevante.
* Difuminar datos sensibles cuando aplique.
* Evitar capturas de entornos productivos.

---

# Seguridad en contratos API

Los contratos API deben:

* Utilizar datos ficticios.
* Utilizar identificadores ficticios.
* Utilizar ejemplos seguros.

Ejemplo:

```json
{
  "id": "00000000-0000-0000-0000-000000000000",
  "email": "usuario@example.com"
}
```

Nunca:

```json
{
  "id": "1023948756",
  "email": "usuario@sena.edu.co"
}
```

---

# Gestión de incidentes documentales

## Si se detecta una filtración

Acciones inmediatas:

1. Detener la propagación del dato expuesto.
2. No crear nuevos commits que repliquen la información.
3. Informar al responsable del repositorio.
4. Informar al equipo de arquitectura.
5. Evaluar impacto.
6. Eliminar o reemplazar la información comprometida.
7. Rotar credenciales si aplica.
8. Analizar necesidad de limpieza de historial Git.

---

## Prioridad de respuesta

Cuando exista una credencial comprometida:

```text
Rotar primero
↓
Mitigar impacto
↓
Notificar
↓
Documentar incidente
```

Nunca esperar aprobación para rotar una credencial comprometida.

---

# Responsabilidades

## Autor del documento

Responsable de:

* Revisar el contenido antes del Pull Request.
* Verificar cumplimiento de estas reglas.
* Eliminar información sensible detectada.

---

## Revisor

Responsable de:

* Validar el cumplimiento de la política.
* Rechazar contenido inseguro.
* Solicitar correcciones cuando aplique.

---

## Equipo de Arquitectura

Responsable de:

* Mantener esta política.
* Resolver dudas de seguridad documental.
* Aprobar excepciones justificadas.

---

# Checklist de seguridad

Antes de realizar un Pull Request:

* [ ] No existen contraseñas.
* [ ] No existen tokens reales.
* [ ] No existen llaves privadas.
* [ ] No existen datos personales reales.
* [ ] No existen URLs privadas.
* [ ] No existen IPs internas.
* [ ] No existen capturas comprometidas.
* [ ] Los ejemplos utilizan valores ficticios.
* [ ] Los diagramas cumplen la política de seguridad.

---

# Relación con el proceso documental

Todo documento deberá cumplir esta política antes de considerarse:

* Ready (Definition of Ready).
* Done (Definition of Done).

El incumplimiento de esta política es motivo suficiente para rechazar un Pull Request.

---

# Referencias

* `definition-of-ready.md`
* `definition-of-done.md`
* `documentation-rules.md`
* `git-conventions.md`

---

# Regla general

> La seguridad tiene prioridad sobre la documentación. Si existe duda sobre la publicación de una información, deberá asumirse que no puede publicarse hasta ser validada por el equipo de arquitectura.
