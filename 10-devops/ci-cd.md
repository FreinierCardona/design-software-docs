# CI/CD

> Estado: 🟢 Completo | Última actualización: 2026-06-30
> Autor: Equipo DevOps
> Equipo: DevOps e Infraestructura

## Propósito

Este documento describe la estrategia de Integración Continua (Continuous Integration) y Entrega Continua (Continuous Delivery) adoptada por el Sistema de Gestión de Horarios SENA.

Su objetivo es definir el flujo mediante el cual los cambios realizados al código fuente son integrados, validados, construidos y promovidos entre los diferentes ambientes del proyecto, garantizando trazabilidad, calidad y estabilidad durante todo el ciclo de vida del software.

---

# Objetivos

La estrategia CI/CD busca:

- Automatizar el proceso de integración del software.
- Detectar errores tempranamente.
- Garantizar la calidad antes de cada despliegue.
- Reducir riesgos durante la liberación de nuevas versiones.
- Estandarizar el proceso de entrega.
- Facilitar la trazabilidad de los cambios.
- Asegurar la repetibilidad de los procesos.

---

# Alcance

La documentación comprende:

- Flujo general de integración.
- Estrategia de despliegue.
- Controles automáticos de calidad.
- Promoción entre ambientes.
- Gestión de versiones.
- Buenas prácticas operativas.

No incluye configuraciones específicas de herramientas, archivos de automatización, scripts de infraestructura ni información sensible.

---

# Flujo de integración

Todo cambio desarrollado deberá seguir el flujo definido por la estrategia de ramas del proyecto.

De manera general, el proceso comprende:

1. Desarrollo de la funcionalidad.
2. Validación local.
3. Integración mediante control de versiones.
4. Ejecución automática de validaciones.
5. Construcción del artefacto.
6. Despliegue al ambiente correspondiente.
7. Validación antes de su promoción al siguiente ambiente.

Cada etapa deberá completarse satisfactoriamente antes de continuar con la siguiente.

---

# Controles de calidad

La canalización de integración continua deberá ejecutar automáticamente, cuando corresponda:

- Validación de la compilación.
- Resolución de dependencias.
- Análisis estático de código.
- Ejecución de pruebas automatizadas.
- Verificación de estándares de calidad.
- Validación de seguridad.
- Generación de artefactos.
- Publicación de resultados.

Los controles aplicados podrán evolucionar conforme avance el proyecto.

---

# Promoción entre ambientes

La promoción de una versión deberá realizarse de forma progresiva respetando la estrategia definida para el proyecto.

El flujo de promoción será:

```
Desarrollo
      │
      ▼
QA
      │
      ▼
Staging
      │
      ▼
Producción
```

Cada transición requerirá la aprobación de los criterios de calidad establecidos para el ambiente correspondiente.

---

# Gestión de versiones

Cada versión liberada deberá:

- encontrarse identificada de forma única;
- mantener trazabilidad con los cambios realizados;
- poder relacionarse con su correspondiente versión del código fuente;
- conservar un historial verificable de despliegues.

---

# Estrategia de despliegue

El proceso de despliegue deberá garantizar:

- consistencia entre ambientes;
- automatización siempre que sea posible;
- capacidad de recuperación ante fallos;
- mínimo impacto sobre la disponibilidad del sistema;
- trazabilidad completa de las liberaciones.

Las estrategias específicas de despliegue serán documentadas por el equipo de DevOps cuando sean implementadas.

---

# Responsabilidades

| Equipo | Responsabilidad |
|---------|-----------------|
| Desarrollo | Integrar cambios y garantizar que cumplan los estándares definidos. |
| QA | Validar funcionalmente las versiones candidatas. |
| Arquitectura | Verificar el cumplimiento de los lineamientos arquitectónicos. |
| DevOps | Administrar y mantener los procesos de integración y despliegue. |

---

# Trazabilidad

Cada ejecución del proceso de CI/CD deberá permitir identificar:

- versión del software;
- origen del cambio;
- rama utilizada;
- ambiente de destino;
- resultado de las validaciones;
- fecha de ejecución;
- historial de despliegues.

---

# Buenas prácticas

La estrategia de CI/CD deberá:

- automatizar todas las validaciones posibles;
- mantener procesos reproducibles;
- evitar despliegues manuales no documentados;
- impedir la promoción de versiones que no cumplan los controles de calidad;
- mantener registros de todas las ejecuciones;
- evolucionar junto con la arquitectura del proyecto.

---

# Relación con otros documentos

Este documento complementa:

- `README.md` de DevOps.
- `local-setup.md`.
- `environments.md`.
- Estrategia de ramas.
- Arquitectura del sistema.
- Documentación de microservicios.
- ADR relacionados.

---

# Mantenimiento

La documentación de CI/CD deberá actualizarse cuando exista alguno de los siguientes cambios:

- modificación del flujo de integración;
- incorporación de nuevos controles de calidad;
- actualización de la estrategia de despliegue;
- cambios en la estrategia de ramas;
- incorporación de nuevas herramientas de automatización;
- modificación del proceso de liberación.

Toda actualización deberá mantenerse alineada con la arquitectura, la estrategia DevOps y la gobernanza del Sistema de Gestión de Horarios SENA.