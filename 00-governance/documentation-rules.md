# Reglas de Documentación

> Estado: 🟢 Aprobado |
> Última actualización: 2026-06-23 |
> Autor: Equipo de Arquitectura |
> Equipo: Sistema de Gestión de Horarios SENA |

---

# Objetivo

Definir las reglas y estándares para la creación, organización, mantenimiento y evolución de la documentación oficial del proyecto.

Estas reglas buscan garantizar:

* Consistencia entre documentos.
* Facilidad de navegación.
* Trazabilidad de cambios.
* Calidad documental.
* Escalabilidad del repositorio.
* Transferencia efectiva de conocimiento entre integrantes del equipo.

---

# Alcance

Estas reglas aplican a:

* Arquitectura.
* Reglas de negocio.
* Historias de usuario.
* Modelos de datos.
* APIs.
* Diagramas.
* ADRs.
* Microservicios.
* Infraestructura.
* Seguridad.
* Gobernanza.
* Cualquier otro documento almacenado dentro del repositorio.

---

# Convenciones de nombres

## Archivos

Todos los archivos Markdown deben utilizar:

```text
kebab-case.md
```

### Correcto

```text
data-model.md
api-contract.md
business-rules.md
microservice-catalog.md
```

### Incorrecto

```text
DataModel.md
data_model.md
Documento Final.md
archivo1.md
```

### Reglas

* Utilizar únicamente letras minúsculas.
* Separar palabras mediante guiones (`-`).
* No utilizar espacios.
* No utilizar caracteres especiales.
* El nombre debe describir claramente el contenido.

---

## Carpetas

Las carpetas raíz del repositorio utilizan el formato:

```text
NN-nombre-seccion
```

### Ejemplos

```text
00-governance
01-product
05-architecture
08-uml
09-microservices
```

### Reglas

* No crear carpetas raíz sin aprobación del equipo de arquitectura.
* Toda carpeta debe contener un `README.md`.
* Los nombres deben ser descriptivos y permanentes.
* No utilizar carpetas temporales.

### Prohibido

```text
otros
temp
misc
pruebas
nueva-carpeta
```

---

# Estructura mínima obligatoria

Todo documento debe iniciar con la siguiente estructura:

```markdown
# Título descriptivo

> Estado: 🔴 Borrador
> Última actualización: YYYY-MM-DD
> Autor: Nombre o Equipo Responsable

---

# Objetivo

# Alcance

# Contenido

# Referencias
```

---

# Estados documentales

| Estado         | Descripción                               |
| -------------- | ----------------------------------------- |
| 🔴 Borrador    | Documento en construcción inicial.        |
| 🟡 En revisión | Documento sometido a validación.          |
| 🟢 Aprobado    | Documento validado y considerado oficial. |
| ⚫ Obsoleto     | Documento reemplazado o retirado.         |

---

# Gestión de documentos obsoletos

## Documento reemplazado

Cuando un documento sea sustituido:

```markdown
> Reemplazado por: [nuevo-documento.md](../ruta)
```

Reglas:

* Mantener el documento original.
* Cambiar estado a ⚫ Obsoleto.
* Mantener trazabilidad histórica.

---

## Documento eliminado por reestructuración

Acciones requeridas:

1. Mover a:

```text
99-archive/deprecated/
```

2. Registrar movimiento en:

```text
CHANGELOG.md
```

3. Actualizar enlaces afectados.

---

## ADR obsoleta

Las ADRs nunca deben eliminarse.

Acciones requeridas:

* Mantener en su ubicación original.
* Cambiar estado a Obsoleto.
* Referenciar la ADR que la reemplaza.

Ejemplo:

```markdown
> Reemplazada por: ADR-015-service-boundaries.md
```

---

# Índices obligatorios

Todo documento nuevo debe estar registrado en su índice correspondiente.

| Tipo                  | Ubicación                  |
| --------------------- | -------------------------- |
| Documentación general | README de la sección       |
| ADRs                  | architecture/decisions     |
| Diagramas             | diagram-index.md           |
| Microservicios        | service-catalog.md         |
| APIs                  | api-catalog.md (si aplica) |

---

# Creación de documentos

## Documento nuevo

Antes de crear un documento:

1. Verificar que no exista documentación equivalente.
2. Identificar la sección correcta.
3. Crear el archivo siguiendo la plantilla oficial.
4. Registrar el documento en el índice correspondiente.
5. Validar mediante Definition of Ready.
6. Crear Pull Request.

---

## Carpeta nueva

Una carpeta nueva solamente podrá crearse cuando:

* Agrupe múltiples documentos relacionados.
* Posea una responsabilidad clara.
* Facilite la navegación del repositorio.
* Tenga crecimiento previsto.

No crear carpetas para almacenar un único documento.

---

# Diagramas y recursos visuales

## Ubicaciones oficiales

| Recurso                | Ubicación                  |
| ---------------------- | -------------------------- |
| PlantUML / fuentes UML | `08-uml/diagrams/source/`  |
| Exportaciones SVG      | `08-uml/diagrams/exports/` |
| Imágenes generales     | `assets/images/`           |
| Logos                  | `assets/logos/`            |

---

## Reglas para diagramas

* Todo diagrama debe poseer fuente editable.
* SVG es el formato preferido.
* No subir únicamente exportaciones.
* Todo diagrama debe registrarse en:

```text
08-uml/diagram-index.md
```

* Los diagramas utilizados por arquitectura deben estar enlazados desde los documentos correspondientes.

---

# Flujo documental

Todo documento deberá seguir el siguiente flujo:

```text
Borrador
   ↓
Ready
   ↓
Pull Request
   ↓
Revisión
   ↓
Aprobado
```

Validado mediante:

* Definition of Ready
* Definition of Done

---

# Estrategia de ramas

La documentación deberá respetar la estrategia oficial del proyecto:

```text
main      → Producción
staging   → Preproducción
qa        → Validación funcional y técnica
develop   → Desarrollo e integración
```

Ningún documento deberá llegar a `main` sin haber pasado previamente por los procesos de revisión definidos para `develop`, `qa` y `staging`.

---

# Errores comunes

| Error                    | Impacto                     | Acción Correctiva     |
| ------------------------ | --------------------------- | --------------------- |
| Documento sin índice     | Invisible para el equipo    | Registrar en README   |
| Enlaces rotos            | Navegación incorrecta       | Corregir referencias  |
| Diagramas sin fuente     | Difícil mantenimiento       | Subir fuente editable |
| Contenido duplicado      | Múltiples fuentes de verdad | Consolidar documento  |
| Carpetas genéricas       | Desorganización             | Reestructurar         |
| Eliminación de historial | Pérdida de trazabilidad     | Archivar o deprecar   |

---

# Referencias

* `definition-of-ready.md`
* `definition-of-done.md`
* `git-conventions.md`
* `security-rules.md`

---

# Regla general

> Todo documento almacenado en este repositorio se considera documentación oficial del Sistema de Gestión de Horarios SENA y deberá cumplir obligatoriamente las reglas definidas en este documento.
