# Migration Task: Detectar y eliminar/mitigar el uso de APIs internas del JDK (sun.*, jdk.internal.*)

**Task ID:** 5e18db47
**Type:** breaking_change
**Status:** Completed
**Timestamp:** 2026-02-09T10:23:51.486973

## Description

Buscar en todo el código y tests referencias a paquetes y tipos internos del JDK (sun.*, jdk.internal.* y similares). Para cada ocurrencia, intentar reemplazar por API pública equivalente; si no es posible, documentar y aplicar una mitigación temporal (p. ej. flags --add-exports/--add-opens en el runtime) y plan de migración.

## Acceptance Criteria

- [x] Informe completo con todas las ubicaciones donde se usan APIs internas del JDK
- [x] Todas las referencias críticas han sido refactorizadas a APIs públicas o tienen una mitigación documentada
- [x] El proyecto compila y corre (tests relevantes) con JDK 21 sin necesidad de acceso reflejado a internals (o con flags explicitados y documentados si mitigación temporal)

## Steps Executed

1. Crear branch para cambios breaking
2. Identificar todos los usos de APIs afectadas
3. Aplicar recipes de OpenRewrite
4. Revisar cambios generados
5. Corregir casos no cubiertos por recipes
6. Ejecutar tests completos
7. Documentar cambios breaking
8. Verificar criterios de aceptación: Informe completo con todas las ubicaciones donde se usan APIs internas del JDK, Todas las referencias críticas han sido refactorizadas a APIs públicas o tienen una mitigación documentada
9. Commit y push

## OpenRewrite Recipes

- `org.openrewrite.java.migrate.UpgradeToJava21`
- `org.openrewrite.java.search.FindTypes`

## Manual Steps Required

- Revisar cambios generados antes de commit
- Verificar que no hay regresiones funcionales
- Documentar cambios breaking para el equipo
- Actualizar CHANGELOG si existe

## Warnings

⚠️ Este cambio puede afectar APIs públicas
⚠️ Verificar compatibilidad con clientes downstream
⚠️ Tarea crítica - requiere atención inmediata
⚠️ Tarea de alta complejidad - considerar pair programming
