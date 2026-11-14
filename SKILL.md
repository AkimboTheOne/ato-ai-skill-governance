---
name: ato-ai-skill-governance
description: Gobierna la creación, modificación o revisión de skills antes de planificar cambios. También orienta decisiones sobre arquitectura, runtime, memoria, herramientas, automatización y orquestación; no se activa intensamente por menciones incidentales.
---

# ATO Skill Governance

Guía para diseñar y revisar skills y sistemas de IA con menos complejidad y control humano. Complementa la tarea; no es un motor de runtime.

## Orden de decisión

Antes de planificar una tarea gobernada por esta skill, sigue este orden y detente cuando la decisión esté resuelta. Ajusta la profundidad al riesgo y consulta solo la referencia pertinente:

1. **Preguntar:** valida necesidad, responsable, alcance y riesgo ([question.md](references/question.md)).
2. **Eliminar:** retira duplicados y pasos innecesarios ([eliminate.md](references/eliminate.md)).
3. **Simplificar:** conserva un diseño explícito y auditable ([simplify.md](references/simplify.md)).
4. **Acelerar:** optimiza solo un proceso estable ([accelerate.md](references/accelerate.md)).
5. **Automatizar:** automatiza solo un proceso estable y gobernable ([automate.md](references/automate.md)).

## Límites

- El control del agente es delegado: actúa dentro del objetivo, alcance y permisos; la persona conserva la decisión final, las aprobaciones y la capacidad de anulación. Ejecuta lo ya autorizado sin pedir aprobación repetida; aclara ambigüedades y no presentes recomendaciones como aprobaciones.
- No añadas estado oculto ni efectos externos fuera de autorización. Conserva auditabilidad, reversibilidad y control humano.
- Exige justificación para RAG, bases vectoriales, distribución, frameworks, orquestación multiagente o recursiva. Rechaza cadenas sin fin y automatización insegura.
- Para memoria y promoción doctrinal, sigue [memory/README.md](memory/README.md); no promociones memoria local a la canónica sin aprobación humana explícita.
- Al crear o revisar skills, valida identidad, estructura, SemVer y metadatos de plataforma según [question.md](references/question.md). Mantén en cada `SKILL.md` las instrucciones esenciales; distribuye detalles solo cuando mejore la claridad. No impongas estas cinco categorías a otras skills ([simplify.md](references/simplify.md)).

## Activación

Aplica esta gobernanza al crear, modificar o revisar skills, o al cambiar arquitectura, runtime, memoria, herramientas, automatización u orquestación. Una mención incidental o un cambio editorial sin efecto conductual requiere poca o ninguna intervención; aumenta la intervención con el riesgo y aplaza cambios inseguros o sujetos a aprobación humana. `AGENTS.md` rige este repositorio y no es requisito portable de la skill.

`must` indica obligación; `should`, valor predeterminado salvo excepción documentada; `may`, opción.
