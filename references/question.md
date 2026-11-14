# Preguntar (Question)

Valida el requisito antes de diseñar. Evalúa el problema real, valor, pertinencia, responsable, alternativas, costo operativo, carga cognitiva e impacto arquitectónico. Cuestiona supuestos heredados y arquitectura por moda. Rechaza o aplaza requisitos injustificados o cuyo costo supere su valor.

Define entradas, salida esperada, alcance incluido y excluido, responsabilidades y modos de fallo. Si la ambigüedad impide una decisión segura, solicita una aclaración concreta. Evalúa si ya existe una capacidad equivalente antes de proponer otra.

## Autoridad y delegación

El agente ejerce control delegado: analiza, recomienda y elige medios dentro del objetivo, alcance y permisos recibidos; no es autoridad humana, no amplía la autorización y no convierte una recomendación en aprobación. La persona conserva la decisión final y las aprobaciones que exijan las políticas.

Ejecuta acciones ya autorizadas dentro del alcance sin pedir aprobación repetida. Aclara límites ambiguos y aplaza acciones que excedan el alcance o requieran autorización o revisión humana. Distingue siempre entre recomendar una acción y ejecutarla.

## Identidad y validación de una skill

Usa la especificación abierta [Agent Skills](https://agentskills.io/specification) como referencia de formato y consulta la documentación de la plataforma objetivo para sus diferencias. Comprueba que exista `SKILL.md` con frontmatter YAML válido seguido de Markdown; que `name` y `description` estén presentes; y que cumplan sus límites y convenciones. Según Agent Skills, `name` tiene 1–64 caracteres en minúsculas, números o guiones, sin guiones iniciales, finales o consecutivos, y coincide con el directorio. `description` tiene 1–1024 caracteres y explica qué hace la skill y cuándo usarla. Comprueba la coherencia entre esos metadatos, el título y el contenido. Trata los demás campos como opcionales salvo que la especificación o plataforma aplicable los requiera; no generalices la lista permitida por un validador particular.

ATO exige además un archivo `VERSION` en la raíz de cada skill gobernada, con versión válida conforme a Semantic Versioning 2.0.0. Este requisito propio es independiente del formato Agent Skills. Comprueba su coherencia con el contenido y, cuando existan, con los artefactos de publicación.

`quick_validate.py` de Codex `skill-creator` inspira el ejemplo inicial de comprobaciones estructurales básicas en Codex; no es autoridad, requisito ni dependencia de runtime. Los validadores son herramientas de desarrollo y revisión. Si se usan, descubre su ubicación en el entorno activo y mantén sus dependencias aisladas en el entorno de desarrollo del repositorio, fuera del paquete distribuido. Si no está disponible, informa que no pudo ejecutarse y haz comprobaciones estáticas razonables; no inventes resultados ni instales software fuera del proyecto. No copies ni mantengas validadores propios ni añadas scripts, servicios o dependencias nuevas salvo justificación arquitectónica.

Revisa aparte, cuando corresponda, enlaces y referencias, secretos accidentales, marcadores de plantilla y convenciones locales. En Codex, los campos de interfaz `agents/openai.yaml` son específicos de la plataforma: al crear una skill incluye `display_name` y `short_description` coherentes y habilita invocación implícita por defecto; al revisar, conserva la política y los campos existentes. Informa ausencias o incoherencias y corrígelas solo dentro del alcance autorizado. Redacta la prosa para su audiencia y conserva en inglés identificadores, nombres de archivos, claves, valores de contrato y términos técnicos cuando su traducción reduzca precisión.

## Activación y riesgo

Activa la gobernanza al crear o revisar skills o modificar sus instrucciones, activación, planificación, runtime, memoria, herramientas, automatización, orquestación o arquitectura. Examina el contexto de términos como `skill`, `retrieval`, `memory`, `governance` y `runtime`: una mención incidental no requiere intervención intensa.

Evalúa si la propuesta añade partes móviles, dependencias, herramientas, carga de contexto, estado persistente, autonomía, efectos secundarios o reduce la inspección humana. Pide justificación de necesidad, costo, control y reversibilidad para distribución, orquestación asíncrona, fragmentación por eventos, RAG, bases vectoriales, infraestructura de escala, agentes autónomos o recursivos y prompts que se modifican solos.

RAG y bases vectoriales requieren una necesidad de recuperación demostrada; la orquestación multiagente requiere necesidad operativa. Sin ella, aplaza la propuesta y solicita revisión humana. La ejecución autónoma en segundo plano también requiere revisión humana antes de implementarse.

- **Consultivo:** cambios de bajo riesgo; expón compensaciones y propone simplificar. En formato, ortografía o redacción sin cambios de comportamiento, mantén la intervención ligera.
- **Rector:** creación o revisión de skills y cambios habituales de planificación, memoria, herramientas o runtime; aplica el orden, valida límites y solicita justificación cuando proceda.
- **Restrictivo:** aumento de complejidad, alcance o riesgo; reduce el alcance y exige justificación o revisión.
- **Bloqueante:** aplaza o rechaza automatización insegura, estado oculto, ejecución autónoma o recursiva sin límites, cadenas sin fin, efectos irreversibles sin autorización o complejidad sin justificación. Requiere revisión humana cuando corresponda.

No suprimas la revisión si un cambio pequeño altera activación, comportamiento, límites de runtime, memoria, herramientas, automatización o auditabilidad. Las acciones destructivas, cambios persistentes o masivos, seguridad, cumplimiento y efectos irreversibles requieren revisión proporcional y autorización aplicable.
