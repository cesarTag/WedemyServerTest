# Migration Task: Migrar javax.* a jakarta.*

**Task ID:** 6c26cd43
**Type:** breaking_change
**Status:** Completed
**Timestamp:** 2026-02-18T11:40:37.121017

## Description

Actualizar imports y APIs de javax.* a jakarta.* (Jakarta EE)

## Acceptance Criteria

- [x] No hay imports de javax.* (excepto javax.sql, javax.crypto)
- [x] Código compila correctamente

## OpenRewrite Recipes Applied

- `org.openrewrite.java.migrate.jakarta.JavaxMigrationToJakarta`
