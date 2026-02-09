# Migration Task: Detectar y mitigar accesos reflectivos problemáticos (añadir flags temporales y planificar migración)

**Task ID:** 79abd305
**Type:** breaking_change
**Status:** Completed
**Timestamp:** 2026-02-09T10:24:39.439862

## Description

Detectar llamadas reflectivas a miembros no públicos del JDK que fallan bajo la encapsulación fuerte. Como mitigación inmediata, actualizar scripts de CI / ejecución para incluir los flags JVM necesarios (--add-opens / --add-exports) documentando exactamente para qué módulos/tipos. Paralelamente, crear tareas para refactorizar código reflexivo hacia APIs soportadas.

## Acceptance Criteria

- [x] Todas las ubicaciones de acceso reflectivo a tipos JDK/internal identificadas y documentadas
- [x] CI local o pipeline actualizado con los flags JVM temporales necesarios para que el build y tests pasen con JDK 21
- [x] Plan de trabajo con tareas concretas para eliminar la necesidad de dichos flags (priorizadas por riesgo) creado y aprobado

## Steps Executed

1. Crear branch para cambios breaking
2. Identificar todos los usos de APIs afectadas
3. Aplicar recipes de OpenRewrite
4. Revisar cambios generados
5. Corregir casos no cubiertos por recipes
6. Ejecutar tests completos
7. Documentar cambios breaking
8. Verificar criterios de aceptación: Todas las ubicaciones de acceso reflectivo a tipos JDK/internal identificadas y documentadas, CI local o pipeline actualizado con los flags JVM temporales necesarios para que el build y tests pasen con JDK 21
9. Commit y push

## OpenRewrite Recipes

- `org.openrewrite.java.migrate.UpgradeToJava21`

## Manual Steps Required

- Revisar cambios generados antes de commit
- Verificar que no hay regresiones funcionales
- Documentar cambios breaking para el equipo
- Actualizar CHANGELOG si existe

## Warnings

⚠️ Este cambio puede afectar APIs públicas
⚠️ Verificar compatibilidad con clientes downstream
⚠️ Tarea crítica - requiere atención inmediata
