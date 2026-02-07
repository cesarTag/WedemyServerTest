# Migration Task: Actualizar y estabilizar suites de test (flaky tests, versiones de frameworks de test)

**Task ID:** 2300ca0f
**Type:** test
**Status:** Completed
**Timestamp:** 2026-02-07T13:56:16.516552

## Description

Actualizar versiones de JUnit/Mockito/Mockk/etc. si es necesario, corregir tests frágiles que fallen bajo Java 17 y ajustar timeouts/condiciones. Asegurar que la cobertura crítica se mantiene.

## Acceptance Criteria

- [x] Frameworks de testing actualizados a versiones compatibles con Java 17
- [x] Tests unitarios e integración clave pasan en CI con JDK 17
- [x] Listado y corrección de tests flaky (minimizar falsos positivos/negativos)

## Steps Executed

1. Crear branch para actualización de tests
2. Identificar tests afectados por la migración
3. Actualizar imports y APIs en tests
4. Actualizar mocks y fixtures si es necesario
5. Ejecutar suite completa de tests
6. Verificar cobertura
7. Verificar criterios de aceptación: Frameworks de testing actualizados a versiones compatibles con Java 17, Tests unitarios e integración clave pasan en CI con JDK 17
8. Commit y push

## Manual Steps Required

- Revisar cambios generados antes de commit
- Verificar que no hay regresiones funcionales
- Todos los cambios deben hacerse manualmente

## Warnings

⚠️ Tarea de alta complejidad - considerar pair programming
