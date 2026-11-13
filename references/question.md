# Preguntar (Question)

Valida el requisito antes de diseñar. Evalúa el problema real, valor, pertinencia, responsable, alternativas, costo operativo, carga cognitiva e impacto arquitectónico. Cuestiona supuestos heredados y arquitectura por moda. Rechaza o aplaza requisitos injustificados o cuyo costo supere su valor.

Define entradas, salida esperada, alcance incluido y excluido, responsabilidades y modos de fallo. Si la ambigüedad impide una decisión segura, solicita una aclaración concreta. Evalúa si ya existe una capacidad equivalente antes de proponer otra.

## Autoridad y delegación

El agente ejerce control delegado: analiza, recomienda y elige medios dentro del objetivo, alcance y permisos recibidos; no es autoridad humana, no amplía la autorización y no convierte una recomendación en aprobación. La persona conserva la decisión final y las aprobaciones que exijan las políticas.

Ejecuta acciones ya autorizadas dentro del alcance sin pedir aprobación repetida. Aclara límites ambiguos y aplaza acciones que excedan el alcance o requieran autorización o revisión humana. Distingue siempre entre recomendar una acción y ejecutarla.

## Identidad de una skill

Al crear o revisar una skill, verifica que:

- `name` de `SKILL.md` identifique la capacidad, cumpla el formato aplicable y coincida con el directorio.
- El título de `SKILL.md` sea legible, refleje el propósito y sea coherente con el nombre técnico.
- `description` explique qué hace y cuándo usarla; no sustituye a los nombres.
- Para la plataforma objetivo, verifica sus metadatos de interfaz solo cuando sean parte del alcance. En la implementación Codex de este repositorio, `agents/openai.yaml` puede incluir `interface.display_name` e `interface.short_description`, coherentes con el título, la capacidad y la descripción; conserva su política y otros campos existentes. Este archivo es específico de OpenAI, no un requisito portable.

En una revisión informa las ausencias o incoherencias; corrígelas solo dentro del alcance autorizado. Redacta la prosa para su audiencia y conserva en inglés identificadores, nombres de archivos, claves, valores de contrato y términos técnicos cuando su traducción reduzca precisión.

En esta implementación Codex, al crear una skill incluye `agents/openai.yaml` con esos campos y habilita la selección automática por defecto, salvo solicitud explícita de deshabilitarla. Al revisar una skill existente, preserva la política de invocación de la plataforma objetivo; informa faltantes y corrígelos solo si la tarea autoriza cambios. Para otros agentes, no asumas este archivo ni estos campos: usa su mecanismo de descubrimiento si se solicita o está documentado.

## Activación y riesgo

Activa la gobernanza al crear o revisar skills o modificar sus instrucciones, activación, planificación, runtime, memoria, herramientas, automatización, orquestación o arquitectura. Examina el contexto de términos como `skill`, `retrieval`, `memory`, `governance` y `runtime`: una mención incidental no requiere intervención intensa.

Evalúa si la propuesta añade partes móviles, dependencias, herramientas, carga de contexto, estado persistente, autonomía, efectos secundarios o reduce la inspección humana. Pide justificación de necesidad, costo, control y reversibilidad para distribución, orquestación asíncrona, fragmentación por eventos, RAG, bases vectoriales, infraestructura de escala, agentes autónomos o recursivos y prompts que se modifican solos.

RAG y bases vectoriales requieren una necesidad de recuperación demostrada; la orquestación multiagente requiere necesidad operativa. Sin ella, aplaza la propuesta y solicita revisión humana. La ejecución autónoma en segundo plano también requiere revisión humana antes de implementarse.

- **Consultivo:** cambios de bajo riesgo; expón compensaciones y propone simplificar. En formato, ortografía o redacción sin cambios de comportamiento, mantén la intervención ligera.
- **Rector:** creación o revisión de skills y cambios habituales de planificación, memoria, herramientas o runtime; aplica el orden, valida límites y solicita justificación cuando proceda.
- **Restrictivo:** aumento de complejidad, alcance o riesgo; reduce el alcance y exige justificación o revisión.
- **Bloqueante:** aplaza o rechaza automatización insegura, estado oculto, ejecución autónoma o recursiva sin límites, cadenas sin fin, efectos irreversibles sin autorización o complejidad sin justificación. Requiere revisión humana cuando corresponda.

No suprimas la revisión si un cambio pequeño altera activación, comportamiento, límites de runtime, memoria, herramientas, automatización o auditabilidad. Las acciones destructivas, cambios persistentes o masivos, seguridad, cumplimiento y efectos irreversibles requieren revisión proporcional y autorización aplicable.
