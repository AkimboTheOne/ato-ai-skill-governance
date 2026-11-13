# Simplificar (Simplify)

Tras eliminar lo innecesario, favorece comportamiento explícito, contratos claros, razonamiento local, flujos deterministas y estado legible por personas. Prefiere modularidad monolítica, Markdown, memoria local, interfaces sencillas y herramientas directas cuando resuelvan el problema. Evita magia, indirección excesiva, distribución prematura y abstracciones que oculten la operación.

Comprueba que la solución sea proporcional al problema, mantenible bajo presión y comprensible, observable y auditable por personas. Mantén visibles decisiones, entradas, salidas y efectos secundarios; conserva control y capacidad de anulación humana. El agente decide medios dentro del alcance delegado, mientras la persona retiene autoridad final y aprobaciones reservadas. No conviertas una recomendación en aprobación ni amplíes permisos. Evalúa costo operativo y carga cognitiva, no sofisticación.

## Distribución de instrucciones

Para cualquier skill, mantén en `SKILL.md` propósito, flujo esencial, restricciones compartidas y enlaces con condiciones claras de lectura. Divide instrucciones extensas en unidades enfocadas y atómicas según su dominio o modo de uso; carga solo las pertinentes. Evita referencias vacías, contenido duplicado y capas de navegación innecesarias. No impongas a otras skills las cinco categorías de esta skill.

## Herramientas, contexto y memoria

Usa herramientas directas y la cadena mínima con un final definido; no elijas herramientas por suposición. Carga solo contexto pertinente y trazable; evita volcados, redundancia y expansión que aumente ambigüedad o superficie de alucinación.

Prefiere memoria local, legible y de solo lectura por defecto. No escribas memoria sin intención explícita, propósito, procedencia y alcance claros. Evita mutaciones ocultas y crecimiento ilimitado. Para precedencia, separación entre memoria local, global y canónica, y promoción con aprobación humana, consulta [memory/README.md](../memory/README.md). No conviertas una preferencia local o información confidencial en doctrina compartida.
