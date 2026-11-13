# Plan de Pull Request

## Título propuesto

Refactorizar la gobernanza de skills y aclarar los límites de autoridad

## Rama y destino

- Rama: `codex/skill-governance-refactor`
- Base: `master`

## Resumen

Refactoriza la skill de gobernanza para usar un punto de entrada conciso y cinco referencias por categoría, conservando las instrucciones esenciales y la carga progresiva. Aclara que el control del agente es una delegación limitada por el objetivo, alcance y permisos recibidos, mientras la persona conserva autoridad final y las aprobaciones exigidas por las políticas. La adaptación de interfaz para Codex permanece separada de la doctrina portable.

## Cambios incluidos

- Consolida las instrucciones detalladas en `references/` y simplifica `SKILL.md` como punto de entrada y router.
- Alinea metadatos, documentación, charters y memoria con la estructura actual del skill y su orientación agnóstica respecto al agente.
- Define los límites de control agéntico y autoridad humana en la doctrina y en los artefactos normativos.
- Añade `TODO.md` con el plan futuro para evaluaciones estáticas y de inferencia; la suite de evaluación todavía no está implementada.

## Validación y revisión

- `git diff --check` sin errores.
- Enlaces locales Markdown comprobados.
- Revisión documental del orden de gobernanza, distribución de instrucciones y autorización humana.
- No hay pruebas de comportamiento del modelo ni validación de runtime en este cambio.

## Riesgos y límites

- Las instrucciones documentan gobernanza, pero no implementan enforcement en runtime.
- `TODO.md` propone una evaluación con modelo local; sus resultados futuros serán indicativos y no una garantía de cumplimiento.
- No se afirma que otros agentes seleccionen automáticamente el skill; cada plataforma puede necesitar su propio adaptador.

## Checklist antes de abrir el PR

- [ ] Revisar el diff completo contra `master`.
- [ ] Confirmar que metadatos de Codex y enlaces entre referencias siguen válidos.
- [ ] Mantener explícito que el plan de evaluación de `TODO.md` no forma parte de la implementación realizada.
