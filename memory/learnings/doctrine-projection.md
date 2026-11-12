# Proyección de la doctrina

## Aprendizaje

Una skill debe tener una doctrina compartida. Sus artefactos operativos —como `SKILL.md`, referencias temáticas, políticas de memoria y, cuando existan, archivos locales de instrucciones o adaptadores de plataforma— proyectan esa doctrina para sus contextos de uso. La forma concreta depende de la arquitectura de la skill; no se requieren archivos YAML ni listas de revisión separados.

Pueden especializar la aplicación de la doctrina en un contexto, pero no deben introducir doctrinas en competencia ni requerir reglas de precedencia para resolver conflictos doctrinales.

Si los artefactos parecen contradecirse, resuelve el problema alineándolos de nuevo con la doctrina compartida y acotando el artefacto contextual.

## Evidencia

Este aprendizaje surgió al revisar `ato-skill-governance`. Tratar `SKILL.md` y `AGENTS.md` como autoridades en competencia creó una cuestión de precedencia innecesaria. El mejor modelo mantiene `SKILL.md` autocontenido para el uso y la activación de la skill, mientras `AGENTS.md` se ocupa de las operaciones locales del repositorio.

## Notas de gobernanza

- Compatible con el orden requerido: Preguntar (Question), Eliminar (Eliminate), Simplificar (Simplify), Acelerar (Accelerate) y Automatizar (Automate).
- Reduce la ambigüedad sin añadir comportamiento en runtime, estado oculto, automatización ni orquestación.
- Mantiene la memoria doctrinal legible por personas y versionada junto con la skill canónica.
