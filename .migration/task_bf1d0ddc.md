# Migration Task: Detectar y remediar uso de APIs internas del JDK (sun.misc.*, com.sun.*)

**Task ID:** bf1d0ddc
**Type:** breaking_change
**Status:** Completed
**Timestamp:** 2026-02-11T10:16:00.944444

## Description

Analizar todo el código fuente para encontrar referencias a paquetes internos del JDK (sun.misc, com.sun, etc.). Para cada hallazgo, documentar el uso, reemplazar por API pública equivalente o introducir adaptadores/depencias. Si no hay reemplazo directo, preparar una propuesta de refactor y parche manual.

## Acceptance Criteria

- [x] Listado exhaustivo de referencias a APIs internas con ubicación (archivo:línea) en un informe
- [x] Para cada referencia: aplicar reemplazo automático o indicar parche manual en el PR (o añadir wrapper con JDK-supported API)
- [x] Proyecto compila sin referencias a sun.misc.* u otros internos (o dichas referencias quedan aisladas y justificadas con ticket de seguimiento)

## OpenRewrite Recipes Applied

- `org.openrewrite.java.search.FindMethods`
