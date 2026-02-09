# Migration Task: Eliminar o adaptar el uso de SecurityManager y APIs marcadas como 'deprecated for removal'

**Task ID:** 77df13ee
**Type:** breaking_change
**Status:** Completed
**Timestamp:** 2026-02-09T10:24:10.559309

## Description

Identificar instancias de SecurityManager, SecurityManager.setSecurityManager, AccessController/Policy o cualquier API marcada como 'deprecated for removal' entre Java 17 y 21. Refactorizar la lógica de seguridad para que no dependa del SecurityManager o documentar la estrategia de reemplazo (p. ej. controles explícitos, comprobaciones de permisos a nivel de aplicación).

## Acceptance Criteria

- [x] Listado de usos de SecurityManager y APIs 'deprecated for removal' encontrado en el código y tests
- [x] Las instancias críticas han sido refactorizadas o encapsuladas de forma que no dependan del SecurityManager
- [x] El proyecto compila y los tests relacionados con seguridad pasan con JDK 21

## Steps Executed

1. Crear branch para cambios breaking
2. Identificar todos los usos de APIs afectadas
3. Aplicar recipes de OpenRewrite
4. Revisar cambios generados
5. Corregir casos no cubiertos por recipes
6. Ejecutar tests completos
7. Documentar cambios breaking
8. Verificar criterios de aceptación: Listado de usos de SecurityManager y APIs 'deprecated for removal' encontrado en el código y tests, Las instancias críticas han sido refactorizadas o encapsuladas de forma que no dependan del SecurityManager
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
