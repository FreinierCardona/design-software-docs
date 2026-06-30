# Migration Strategy

> Estado: 🟢 Completo | Última actualización: 2026-06-29
> Autor: Equipo de Arquitectura
> Equipo: Arquitectura / Base de Datos

---

# Objetivo

Este documento define la estrategia de versionamiento y migración de los esquemas de base de datos utilizados por el Sistema de Gestión de Horarios SENA (SGH SENA).

Su propósito es garantizar que la evolución del modelo de datos sea controlada, trazable y compatible con la arquitectura basada en microservicios, evitando pérdidas de información o interrupciones del servicio.

---

# Alcance

Esta estrategia aplica a:

- todos los microservicios;
- todos los esquemas PostgreSQL;
- cambios estructurales del modelo de datos;
- cambios sobre índices;
- restricciones;
- vistas;
- funciones;
- procedimientos almacenados;
- datos de referencia cuando requieran versionamiento.

No aplica a datos transaccionales propios de la operación diaria del sistema.

---

# Principios

Las migraciones deberán cumplir los siguientes principios:

- Versionadas.
- Repetibles.
- Auditables.
- Automatizadas.
- Compatibles con CI/CD.
- Reversibles cuando sea posible.
- Independientes entre microservicios.
- Sin intervención manual en ambientes productivos.

---

# Arquitectura de migraciones

Cada microservicio administra exclusivamente sus propias migraciones.

No existen migraciones compartidas entre servicios.

```text
Microservicio A
    ├── V1
    ├── V2
    ├── V3

Microservicio B
    ├── V1
    ├── V2

Microservicio C
    ├── V1
```

Cada servicio mantiene su historial de versiones de forma independiente.

---

# Estrategia de versionamiento

Las migraciones serán secuenciales e incrementales.

Ejemplo:

```
V1__initial_schema.sql

V2__create_tables.sql

V3__add_indexes.sql

V4__add_constraints.sql

V5__modify_schedule_table.sql
```

Una migración nunca debe modificarse después de haber sido ejecutada en un entorno compartido.

Si es necesario realizar un cambio adicional, deberá crearse una nueva versión.

---

# Tipos de migraciones

Las migraciones pueden incluir:

## Creación

- tablas
- índices
- restricciones
- vistas
- funciones

---

## Modificación

- agregar columnas
- cambiar restricciones
- crear índices
- modificar tipos compatibles

---

## Eliminación

Solo cuando:

- no exista dependencia funcional;
- haya aprobación arquitectónica;
- exista respaldo de información;
- el cambio esté documentado.

---

# Compatibilidad

Las migraciones deberán mantener compatibilidad hacia atrás cuando existan varias versiones del sistema desplegadas simultáneamente.

Siempre que sea posible:

- agregar antes de eliminar;
- mantener columnas obsoletas temporalmente;
- realizar migraciones en múltiples fases.

---

# Flujo de cambios

Todo cambio seguirá el siguiente proceso:

```text
Cambio funcional

        │

        ▼

Actualización del modelo de datos

        │

        ▼

Revisión arquitectónica

        │

        ▼

Creación de migración

        │

        ▼

Pruebas locales

        │

        ▼

Integración Continua

        │

        ▼

QA

        │

        ▼

Producción
```

---

# Integración con Git

Las migraciones forman parte del código fuente.

Cada Pull Request que modifique la persistencia deberá incluir:

- actualización del modelo de datos;
- migración correspondiente;
- documentación actualizada;
- revisión técnica.

No se aceptarán cambios directos sobre bases de datos compartidas.

---

# Integración con CI/CD

Durante el despliegue:

1. validar versión actual;
2. ejecutar migraciones pendientes;
3. verificar consistencia;
4. registrar auditoría;
5. iniciar la aplicación.

Si una migración falla:

- detener el despliegue;
- registrar el error;
- impedir la publicación parcial del servicio.

---

# Buenas prácticas

Las migraciones deberán:

- ser pequeñas;
- tener un único propósito;
- ser idempotentes cuando aplique;
- evitar bloqueos prolongados;
- minimizar tiempos de indisponibilidad;
- documentar cambios relevantes.

---

# Cambios permitidos

Son considerados seguros:

- crear tablas;
- agregar columnas opcionales;
- crear índices;
- crear vistas;
- agregar restricciones compatibles.

---

# Cambios de alto impacto

Requieren revisión arquitectónica:

- eliminación de tablas;
- eliminación de columnas;
- cambio de claves primarias;
- modificación de relaciones;
- particionamiento;
- cambios masivos de datos.

---

# Rollback

Cuando sea técnicamente viable, cada migración deberá contar con una estrategia de reversión.

Si un rollback no es posible, deberá documentarse claramente y justificarse en la revisión arquitectónica.

---

# Auditoría

Toda migración deberá registrar:

- versión;
- fecha de ejecución;
- servicio afectado;
- autor;
- resultado;
- tiempo de ejecución.

Esto permitirá mantener la trazabilidad completa del esquema de datos.

---

# Relación con otros documentos

Este documento complementa:

- `models.md`, donde se describe la arquitectura de datos.
- `data-dictionary.md`, donde se documentan entidades y atributos.
- `09-microservices`, donde cada servicio mantiene sus migraciones específicas.
- ADR relacionados con persistencia y evolución del modelo de datos.

---

# Conclusión

La estrategia de migraciones del SGH SENA garantiza una evolución controlada del esquema de datos, manteniendo la independencia de los microservicios, la trazabilidad de los cambios y la estabilidad de los ambientes de desarrollo, pruebas y producción.