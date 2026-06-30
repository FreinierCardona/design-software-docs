# Architecture Decision Records (ADR)

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura | Equipo: Arquitectura de Software

## Propósito

Esta carpeta centraliza los **Architecture Decision Records (ADR)** del Sistema de Gestión de Horarios SENA (SGH SENA).

Un ADR documenta una decisión arquitectónica relevante, el contexto en el que fue tomada, las alternativas evaluadas, la decisión adoptada y sus consecuencias. Su objetivo es preservar la trazabilidad técnica del proyecto y facilitar la comprensión de la evolución de la arquitectura.

Los ADR forman parte de la documentación oficial del proyecto y deben mantenerse actualizados durante todo el ciclo de vida del software.

---

# ¿Cuándo crear un ADR?

Se debe crear un ADR cuando exista una decisión que afecte la arquitectura del sistema, por ejemplo:

- Selección de un patrón arquitectónico.
- Incorporación de una nueva tecnología.
- Cambios en la comunicación entre servicios.
- Modificación de la estrategia de despliegue.
- Cambios en la seguridad.
- Decisiones relacionadas con persistencia.
- Estrategias de integración.
- Cambios estructurales que afecten varios módulos.

No es necesario crear ADR para cambios menores de implementación o correcciones de código.

---

# Convenciones

- Formato del archivo:

```
ADR-NNN-titulo-corto.md
```

Ejemplo:

```
ADR-001-adoptar-microservicios.md
```

- La numeración es secuencial y nunca debe reutilizarse.
- El título debe escribirse en **kebab-case**.
- Todos los ADR se almacenan en la carpeta `records/`.
- Los ADR son permanentes y nunca deben eliminarse del repositorio.

---

# Estados

Los ADR pueden tener uno de los siguientes estados:

| Estado | Descripción |
|---------|-------------|
| PROPOSED | La decisión se encuentra en evaluación. |
| ACCEPTED | La decisión fue aprobada y hace parte de la arquitectura. |
| DEPRECATED | La decisión dejó de utilizarse y fue reemplazada por otra. |

Cuando un ADR quede obsoleto:

- Cambiar su estado a **DEPRECATED**.
- Agregar al inicio del documento la referencia al ADR que lo reemplaza.

Ejemplo:

```md
> Reemplazada por: ADR-005-nuevo-modelo-seguridad.md
```

---

# Plantilla

Todos los ADR deben generarse utilizando la plantilla oficial del proyecto.

Archivo:

```
_template-adr.md
```

Ejemplo:

```bash
cp 05-architecture/decisions/_template-adr.md \
05-architecture/decisions/records/ADR-NNN-titulo-corto.md
```

---

# Registro de ADR

Cada nuevo ADR debe agregarse al registro de esta documentación.

| ADR | Título | Estado |
|-----|--------|--------|

---

# Buenas prácticas

- Documentar únicamente decisiones arquitectónicas relevantes.
- Registrar el contexto que motivó la decisión.
- Justificar la alternativa seleccionada.
- Mantener la trazabilidad entre ADR relacionados.
- No modificar el historial de decisiones; utilizar el estado **DEPRECATED** cuando corresponda.
- Mantener el registro actualizado conforme se incorporen nuevos ADR.