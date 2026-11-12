---
name: ato-ai-skill-governance
description: Gobierna la creación, modificación o revisión de skills antes de planificar cambios. También orienta decisiones sobre arquitectura, runtime, memoria, herramientas, automatización y orquestación; no se activa intensamente por menciones incidentales.
---

# ATO Skill Governance

Gobierna el diseño y la revisión de skills y sistemas de IA para reducir complejidad y preservar el control humano. Es una guía de decisión, no un motor de runtime. Complementa la creación de skills sin sustituir la tarea solicitada.

## Orden de decisión

Antes de planificar una tarea de creación, modificación o revisión de una skill, recorre este circuito en orden. La secuencia guía el razonamiento; la profundidad de cada paso depende del riesgo y del cambio. Reevalúa un paso si nueva información altera la decisión. Detente al resolver lo necesario; no fuerces aceleración ni automatización si no forman parte de la tarea. Consulta únicamente las referencias pertinentes:

1. **Preguntar:** valida necesidad, responsable y alcance; evalúa riesgo y justificación. Para identidad, activación o requisitos, lee [question.md](references/question.md).
2. **Eliminar:** busca duplicados, dependencias y pasos que puedan eliminarse o integrarse. Para decidir qué retirar, lee [eliminate.md](references/eliminate.md).
3. **Simplificar:** conserva un flujo explícito, acotado y auditable; distribuye los detalles solo cuando ayude. Para arquitectura, instrucciones, herramientas o memoria, lee [simplify.md](references/simplify.md).
4. **Acelerar:** comprueba la estabilidad antes de optimizar un cuello de botella. Si se propone optimización, lee [accelerate.md](references/accelerate.md).
5. **Automatizar:** solo considera automatizar un proceso estable, verificable y gobernable. Para automatización, ejecución o efectos secundarios, lee [automate.md](references/automate.md).

## Restricciones compartidas

- No optimices antes de eliminar y simplificar; no automatices procesos inestables o poco claros.
- No introduzcas estado persistente oculto. No amplíes el alcance ni ejecutes efectos externos sin autorización. Acota las escrituras y exige reversibilidad o confirmación explícita cuando corresponda.
- Exige justificación operativa para RAG, bases vectoriales, distribución, orquestación multiagente, agentes recursivos o frameworks. Rechaza cadenas sin fin y automatización insegura.
- Preserva visibilidad, auditabilidad, control y capacidad de anulación humana. Aplaza decisiones cuando el riesgo no esté justificado o requiera revisión humana.
- Para memoria, consulta [memory/README.md](memory/README.md). No promociones memoria local o global a la memoria canónica sin aprobación humana explícita.
- Cuando un aprendizaje pueda ser reutilizable, no confidencial y coherente con la doctrina, propone su promoción con evidencia y revisión humana; aplázala si es solo una preferencia local o carece de evidencia.
- Al crear o revisar una skill, verifica su nombre técnico, nombre descriptivo y descripción; para skills destinadas a Codex, verifica también `agents/openai.yaml`. Lee [question.md](references/question.md).
- Al gobernar otras skills, mantén en su `SKILL.md` las instrucciones y límites esenciales; distribuye los detalles extensos en unidades enfocadas y enlazadas cuando sea útil. Cada skill elige categorías adecuadas a su dominio; no debe copiar las cinco de esta skill. Lee [simplify.md](references/simplify.md).

## Activación e intervención

Esta skill debe considerarse automáticamente cuando la tarea implique crear, modificar o revisar una skill, y antes de planificar su implementación. También aplica a cambios de arquitectura, runtime, memoria, herramientas, automatización u orquestación. Ajusta la profundidad al riesgo: consultiva y ligera para cambios editoriales sin efecto conductual; rectora para diseño y revisión; restrictiva ante complejidad o riesgo creciente; bloqueante ante automatización insegura, estado oculto o efectos irreversibles sin autorización o justificación. Una mención incidental no activa por sí sola una revisión profunda. Para los criterios de activación y riesgo, lee [question.md](references/question.md).

Aplica las restricciones solo dentro del alcance y autorización de la tarea. La revisión identifica hallazgos; corrígelos solo si el usuario autorizó cambios. `AGENTS.md` es una referencia local del proyecto, no una dependencia para usar esta skill.

`must` indica obligación; `should`, comportamiento predeterminado salvo excepción documentada; `may`, opción. Evoluciona primero claridad y doctrina, después activación y políticas; no añadas código antes de estabilizar el modelo operativo ni runtime antes de aclarar activación y aplicación de políticas.
