---
name: ato-ai-skill-governance
description: Skill de gobernanza para diseñar, revisar y evolucionar skills de IA, reglas de planificación, políticas de runtime, semántica de activación, estrategia de memoria, uso de herramientas, preparación para la automatización, orquestación, RAG, bases de datos vectoriales, comportamiento multiagente y sistemas de IA gobernables por personas. Úsala antes de planificar la implementación cuando el trabajo pueda ampliar la arquitectura, el comportamiento en runtime, el estado oculto, las herramientas, la automatización o la complejidad operativa. Úsala al revisar AGENTS.md como referencia operativa local del proyecto, no como dependencia necesaria de la skill.
---

# ATO Skill Governance

## Descripción

Skill de gobernanza para diseñar, revisar y evolucionar skills de IA, reglas de planificación, políticas de runtime, semántica de activación y preparación para la automatización.

Mantiene el trabajo con skills estable, controlable, repetible, auditable y gobernable por personas. Es una capa de gobernanza, no un motor de runtime.

---

## Doctrina central

> No automatices, distribuyas, abstraigas, optimices ni orquestes algo que antes no se haya cuestionado, eliminado, simplificado y comprendido.

La complejidad es un costo operativo mientras no se justifique de forma continua.

---

## Orden obligatorio de ingeniería

Todo trabajo con skills debe seguir este orden:

1. Preguntar (Question)
2. Eliminar (Eliminate)
3. Simplificar (Simplify)
4. Acelerar (Accelerate)
5. Automatizar (Automate)

No optimices antes de simplificar.

No automatices antes de alcanzar estabilidad.

---

## Primitivas operativas

Usa estas acciones como comportamiento mecánico de la skill. Aplícalas en secuencia cuando corresponda y detente en cuanto se alcance la decisión necesaria.

### 1. Preguntar (Question)

- Aplícala cuando una solicitud, un supuesto, un límite o el resultado deseado no estén claros.
- Evalúa la necesidad, la responsabilidad, el problema real y el valor operativo esperado.
- Produce un requisito validado, una pregunta más acotada o una propuesta para eliminar algo.
- Detente cuando el requisito esté justificado o rechazado.

### 2. Eliminar (Eliminate)

- Aplícala después de entender el requisito.
- Evalúa duplicados, abstracciones sin uso, herramientas redundantes y orquestación innecesaria.
- Produce una decisión de eliminación o integración antes de proponer incorporaciones.
- Detente cuando el trabajo restante tenga el menor alcance viable.

### 3. Simplificar (Simplify)

- Aplícala después de eliminar lo innecesario.
- Evalúa si el flujo de trabajo es explícito, determinista, auditable y comprensible localmente.
- Produce una estructura, un contrato o una explicación más sencilla y con menos partes móviles.
- Detente cuando simplificar implique eliminar una capacidad necesaria.

### 4. Acotar el alcance (Bound Scope)

- Aplícala antes de planificar la implementación.
- Evalúa el comportamiento incluido y excluido, la responsabilidad y las superficies objetivo.
- Produce límites claros que eviten desviaciones, expansión accidental y aumento del alcance.
- Detente cuando el límite sea suficientemente explícito para guiar la ejecución.

### 5. Comprobar la estabilidad (Check Stability)

- Aplícala antes de acelerar o automatizar.
- Evalúa si el proceso, las entradas, las salidas y los modos de fallo son lo bastante estables.
- Produce un juicio de estabilidad y aplaza la aceleración si el flujo aún es ambiguo.
- Detente cuando la inestabilidad sea el riesgo dominante.

### 6. Evaluar el riesgo de gobernanza (Assess Governance Risk)

- Aplícala cuando se propongan estado oculto, autonomía, orquestación, efectos secundarios o ampliación de herramientas.
- Evalúa la auditabilidad, la reversibilidad, el control humano y la ambigüedad operativa.
- Produce un nivel de riesgo que determine si la intervención será consultiva, rectora, restrictiva o bloqueante.
- Detente si la solicitud conduce a estado oculto injustificado o automatización insegura.

### 7. Solicitar justificación (Request Justification)

- Aplícala cuando la propuesta aumente la complejidad, el alcance de runtime o el riesgo operativo.
- Evalúa si se justifican la necesidad, el costo y el modelo de control.
- Formula una solicitud concreta de justificación centrada en la necesidad y la reversibilidad.
- Detente cuando la justificación sea suficiente o el trabajo se aplace.

### 8. Elegir la intervención mínima (Choose the Minimum Intervention)

- Aplícala después de evaluar el riesgo.
- Evalúa la intervención menos intensa que preserve la claridad, la auditabilidad y la gobernanza humana.
- Elige el modo eficaz más moderado: consultivo, rector, restrictivo o bloqueante.
- Detente cuando la intervención elegida proteja suficientemente el sistema.

### 9. Preservar la auditabilidad (Preserve Auditability)

- Aplícala durante la planificación, la revisión y la definición de límites de runtime.
- Evalúa si las decisiones, entradas, salidas y efectos secundarios siguen siendo legibles y trazables para las personas.
- Produce contratos, restricciones y registros de decisión explícitos.
- Detente si el cambio ocultaría el comportamiento o volvería opaca la gobernanza.

### 10. Decidir la promoción o el aplazamiento (Decide Promotion or Deferral)

- Aplícala cuando un aprendizaje o patrón local pueda convertirse en doctrina reutilizable.
- Evalúa si es reutilizable, no confidencial y coherente con la doctrina central.
- Propón promoverlo o aplazarlo deliberadamente.
- Detente cuando la propuesta sea solo una preferencia local o carezca de evidencia.

---

## Lenguaje normativo

- `must` establece una restricción obligatoria.
- `should` establece un comportamiento predeterminado, salvo que exista una excepción documentada.
- `may` establece un comportamiento opcional.

Cuando un requisito entre en conflicto con un comportamiento predeterminado, prevalece la restricción obligatoria.

---

## Idioma y convenciones editoriales

El contenido de cada skill puede redactarse en el idioma más adecuado para su audiencia. No se exige que todas las skills del repositorio utilicen el mismo idioma.

Mantén en inglés las convenciones técnicas compartidas:

- nombres de archivos y directorios;
- nombres de campos de metadata, claves de front matter e identificadores;
- valores de contrato consumidos por herramientas;
- y keywords de industria establecidas.

La prosa y los textos descriptivos de la metadata, incluida la descripción de front matter, pueden redactarse en el idioma elegido para la skill. Conserva en inglés los términos técnicos establecidos cuando traducirlos reduzca la precisión o dificulte su reconocimiento.

---

## Cuándo usarla

Usa esta skill antes de planificar la implementación cuando una solicitud implique:

- crear, modificar o revisar una skill;
- cambiar `SKILL.md` o referencias operativas locales del proyecto;
- diseñar reglas de planificación;
- diseñar políticas de runtime;
- definir condiciones de activación;
- cambiar la estrategia de memoria;
- añadir herramientas;
- introducir automatización;
- introducir orquestación;
- evaluar RAG;
- evaluar bases de datos vectoriales;
- evaluar comportamiento multiagente;
- o ampliar la arquitectura.

Mantén la intervención ligera ante cambios de formato, correcciones ortográficas, mejoras menores de redacción y limpieza documental de bajo riesgo que no cambien el comportamiento, la activación, la política de runtime, la memoria, las herramientas, la automatización ni la arquitectura.

---

## Activación

Esta skill se activa como restricción de planificación y gobernanza antes de la ejecución.

Debe influir en el razonamiento antes de elegir detalles de implementación. Su función es cuestionar la necesidad, reducir la complejidad, preservar la auditabilidad y evitar la automatización prematura.

La activación debe ser proporcional. Detecta el riesgo de gobernanza, aplica la intervención mínima suficiente y mantén en marcha la tarea principal cuando el cambio no sea conductual o sea de bajo riesgo.

---

## Condiciones de activación automática

Actívala automáticamente cuando el trabajo afecte:

- `SKILL.md`;
- `AGENTS.md`;
- `planner-rules.yaml`;
- `runtime-policy.yaml`;
- `activation-policy.yaml`;
- charters de skills;
- listas de revisión;
- política de memoria;
- política de herramientas;
- orquestación;
- automatización;
- RAG;
- bases de datos vectoriales;
- sistemas multiagente;
- comportamiento recursivo de agentes;
- ejecución en segundo plano;
- estado persistente oculto;
- o efectos secundarios de runtime.

---

## Activación por palabras clave

La activación por palabras clave depende del contexto. Los términos generales deben motivar la revisión de la solicitud circundante, no una intervención intensa por sí solos.

Entre los términos generales de contexto se incluyen:

- `skill`;
- `activation`;
- `retrieval`;
- `memory`;
- `governance`;
- `auditability`;
- `human override`;
- y `runtime`.

Entre los activadores estructurales y restrictivos se incluyen:

- `SKILL.md`;
- `AGENTS.md`;
- `planner rules`;
- `runtime policy`;
- `activation conditions`;
- `memory policy`;
- `tool policy`;
- `automation`;
- `orchestration`;
- `multi-agent`;
- `RAG`;
- `vector database`;
- `persistent memory`;
- `background agent`;
- `recursive agent`;
- `tool chain`;
- `hidden persistent state`;
- `autonomous background execution`;
- `recursive orchestration`;
- y `automation before process stability`.

Usa [governance/activation-policy.yaml](governance/activation-policy.yaml) como taxonomía canónica de activadores.

La activación por palabras clave debe considerar el contexto. No la sobreactives ante menciones incidentales que no afecten el diseño de skills, la arquitectura, el comportamiento de runtime, la memoria, las herramientas o la automatización.

---

## Activación por comportamiento

Actívala cuando una solicitud:

- aumente el alcance arquitectónico;
- añada una parte móvil;
- añada o amplíe el uso de herramientas;
- introduzca estado oculto o persistente;
- reduzca la capacidad de inspección humana;
- automatice un proceso inestable;
- añada comportamiento recursivo o autónomo;
- aumente la carga de contexto;
- o dificulte la auditoría del comportamiento del sistema.

---

## Activación bloqueante

Pasa de orientación consultiva a orientación restrictiva o bloqueante cuando una solicitud proponga:

- efectos secundarios destructivos o irreversibles;
- estado persistente oculto;
- ejecución autónoma en segundo plano;
- orquestación recursiva;
- cadenas de herramientas sin una condición clara de finalización;
- RAG sin necesidad de recuperación demostrada;
- bases de datos vectoriales sin necesidad de recuperación demostrada;
- orquestación multiagente sin necesidad operativa;
- proliferación de frameworks;
- o automatización antes de que el proceso sea estable.

La orientación bloqueante debe requerir justificación explícita, revisión humana o aplazamiento antes de la implementación.

---

## Condiciones de supresión

Suprime la intervención de gobernanza, o mantenla ligera, cuando el trabajo se limite a:

- correcciones ortográficas;
- cambios de formato;
- mejoras sencillas de redacción;
- limpieza documental que no cambie el comportamiento;
- renombrados para mayor claridad sin cambio semántico;
- o revisión de contenido sin cambios en arquitectura, activación, comportamiento de runtime, memoria, herramientas ni automatización.

La supresión no aplica cuando un cambio aparentemente pequeño altere el comportamiento operativo, la semántica de activación, los límites de runtime o la gobernanza humana.

---

## Prioridad de activación

La prioridad alta corresponde al estado oculto, la ejecución autónoma, la ejecución en segundo plano, la orquestación recursiva, RAG, las bases de datos vectoriales, el comportamiento multiagente, los efectos secundarios destructivos, los efectos secundarios de runtime y las propuestas de automatización.

La prioridad media corresponde a la creación de skills, las mejoras de skills, los cambios en reglas de planificación o políticas de runtime, la estrategia de memoria, la ampliación de herramientas y la refactorización de arquitectura.

La prioridad baja corresponde al formato, la redacción y la limpieza documental de bajo riesgo.

La prioridad alta conduce a orientación restrictiva y puede volverse bloqueante ante automatización insegura, estado oculto, efectos irreversibles u orquestación sin límites. La prioridad media conduce a orientación rectora. La prioridad baja conduce a orientación consultiva o supresión.

---

## Modos de salida

### Consultivo

Úsalo para trabajo de bajo riesgo. Identifica compensaciones, sugiere simplificaciones y evita formalidades innecesarias.

### Rector

Úsalo para el diseño y la revisión habituales de skills. Aplica el orden obligatorio de ingeniería, valida los límites y preserva los artefactos canónicos.

### Restrictivo

Úsalo cuando aumenten la complejidad, el alcance o el riesgo de runtime. Requiere justificación, recomienda reducir el alcance y prioriza alternativas más sencillas.

### Bloqueante

Úsalo cuando la solicitud introduzca automatización insegura, estado oculto, efectos irreversibles, orquestación recursiva o complejidad sin límites, sin justificación operativa ni autorización explícitas.

---

## Responsabilidades

Esta skill se encarga de:

- aclarar el propósito y los límites de las skills;
- aplicar las primitivas operativas de forma mecánica y coherente;
- definir condiciones de activación;
- revisar políticas de planificación y runtime;
- identificar complejidad innecesaria;
- cuestionar la automatización prematura;
- preservar la auditabilidad humana;
- recomendar alternativas más sencillas;
- identificar propuestas de promoción doctrinal cuando aprendizajes locales puedan mejorar la doctrina canónica;
- y mantener coherentes los artefactos de gobernanza.

---

## Fuera de alcance

Esta skill no se encarga directamente de:

- ejecución específica de un dominio;
- automatización de flujos de negocio;
- integración con plataformas externas;
- operaciones de escritura autónomas;
- ejecución en segundo plano;
- orquestación multiagente;
- memoria persistente oculta;
- implementación de mecanismos de cumplimiento en runtime;
- infraestructura RAG;
- infraestructura de bases de datos vectoriales;
- ni plataformas de frameworks.

Otras skills o herramientas pueden admitir esas capacidades, pero esta skill gobierna si están justificadas.

---

## Restricciones obligatorias

- Preserva el orden obligatorio: Preguntar, Eliminar, Simplificar, Acelerar y Automatizar.
- No automatices flujos inestables o poco claros.
- No optimices antes de simplificar.
- No introduzcas estado persistente oculto.
- No introduzcas RAG, bases de datos vectoriales, agentes recursivos, orquestación multiagente ni sistemas basados en frameworks sin justificación operativa explícita.
- Preserva la visibilidad humana, la auditabilidad, la reversibilidad y la capacidad de anulación.
- Mantén el estado, las políticas y la memoria en formatos legibles por personas, salvo que exista una necesidad operativa más fuerte documentada.
- No promuevas memoria local o global a memoria canónica de la skill sin aprobación humana explícita.

---

## Gobernanza de runtime

El comportamiento en runtime debe seguir siendo:

- explícito;
- acotado;
- inspeccionable;
- auditable;
- reversible cuando sea posible, o confirmable de forma explícita cuando no lo sea;
- y gobernable por personas.

Esta skill no implementa mecanismos de cumplimiento en runtime. Gobierna si el comportamiento propuesto está justificado, acotado y es comprensible antes de implementarlo.

---

## Artefactos canónicos

Esta skill se apoya en estos artefactos canónicos:

- [README.md](README.md), para orientarse en el repositorio;
- [FOUNDATION.md](FOUNDATION.md), para consultar la doctrina de ingeniería reutilizable;
- [skill-charter.md](skill-charter.md), para consultar el charter concreto de esta skill;
- [governance/planner-rules.yaml](governance/planner-rules.yaml), para consultar heurísticas de planificación;
- [governance/runtime-policy.yaml](governance/runtime-policy.yaml), para consultar los límites de runtime;
- [governance/activation-policy.yaml](governance/activation-policy.yaml), para consultar la política de activación;
- [reviews/checklist.md](reviews/checklist.md), para consultar los criterios de revisión;
- [skills/templates/skill-charter.template.md](skills/templates/skill-charter.template.md), para consultar charters de futuras skills;
- [memory/README.md](memory/README.md), para consultar los límites y la precedencia de memoria, y el manejo de propuestas de promoción doctrinal;
- y [references/README.md](references/README.md), para consultar material de referencia gobernado.

Estos artefactos son proyecciones contextuales de la doctrina compartida en `FOUNDATION.md`. No deben introducir doctrinas en competencia.

`AGENTS.md` es una referencia operativa local del proyecto cuando está presente. Puede orientar el mantenimiento del repositorio, pero `SKILL.md` debe seguir siendo útil sin depender de él como artefacto canónico.

No se deben crear duplicados de políticas gobernadas en la raíz.

---

## Política de evolución

Esta skill debería evolucionar mediante:

1. mayor claridad;
2. menor ambigüedad;
3. semántica de activación más precisa;
4. mejora de los artefactos de gobernanza;
5. documentación de decisiones;
6. y solo después, evaluación de automatización.

No añadas código hasta que el modelo operativo basado en documentación sea estable.

No añadas comportamiento en runtime hasta que estén claras la activación y la aplicación de políticas.

---

## Criterio de calidad

Un buen resultado de esta skill reduce complejidad, aclara límites, mejora las decisiones, expone supuestos injustificados y preserva la gobernanza humana.

Un mal resultado añade formalidades, crea frameworks genéricos, oculta complejidad, abusa de YAML, introduce runtime antes de estabilizar la doctrina o hace que gobernar la skill sea más difícil que gobernar las skills que ayuda a diseñar.

---

## Principio final

> Una skill debe reducir la complejidad operativa más rápido de lo que crea complejidad arquitectónica.
