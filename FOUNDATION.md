# FOUNDATION.md

# Fundamentos de ingeniería

## Propósito

Este documento define principios fundamentales de ingeniería para:

- skills de IA;
- agentes;
- copilotos;
- sistemas de automatización;
- runtimes de orquestación;
- sistemas de memoria;
- y flujos de desarrollo asistidos por IA.

Estos principios existen para:

- minimizar la complejidad innecesaria;
- preservar la claridad operativa;
- reducir la desviación arquitectónica;
- y evitar que la automatización amplifique el caos.

---

## Doctrina central

> No automatices, distribuyas, abstraigas, optimices ni orquestes algo que antes no se haya cuestionado, eliminado, simplificado y comprendido.

La complejidad es un riesgo salvo que se justifique explícitamente.

---

## Orden de ingeniería

El orden es obligatorio.

### 1. Preguntar (Question)

Cada requisito debe:

- tener una persona responsable;
- tener una razón;
- resolver un problema real;
- justificar su costo operativo.

Cuestiona:

- supuestos heredados;
- patrones heredados;
- abstracciones innecesarias;
- buenas prácticas aplicadas sin contexto.

Si nadie puede explicar por qué existe algo, considera eliminarlo.

---

### 2. Eliminar (Eliminate)

Elimina:

- procesos redundantes;
- lógica duplicada;
- dependencias innecesarias;
- herramientas sin uso;
- arquitectura prematura.

La complejidad genera:

- costo de mantenimiento;
- costo de depuración;
- costo cognitivo;
- riesgo operativo.

Prefiere eliminar antes que ampliar.

---

### 3. Simplificar (Simplify)

Simplifica solo después de eliminar.

Prioriza:

- sistemas explícitos;
- estructuras legibles;
- razonamiento local;
- memoria auditable por personas;
- comportamiento determinista.

Evita:

- estado oculto;
- comportamiento mágico;
- indirection innecesaria;
- capas de frameworks;
- orquestación sin necesidad.

Un sistema que las personas no pueden comprender fácilmente no se puede gobernar de forma segura.

---

### 4. Acelerar (Accelerate)

Acelera solo sistemas estables.

La velocidad sin claridad amplifica los defectos.

Optimiza:

- ciclos de retroalimentación;
- ciclos de entrega;
- fricción de despliegue;
- eficiencia de recuperación;
- rendimiento operativo.

No aceleres:

- la ambigüedad;
- la arquitectura inestable;
- las responsabilidades fragmentadas;
- los flujos inconsistentes.

---

### 5. Automatizar (Automate)

La automatización es el último paso.

La automatización amplifica:

- la claridad;
- o el caos.

No automatices:

- procesos defectuosos;
- flujos contradictorios;
- responsabilidades indefinidas;
- arquitectura inestable.

La IA no reemplaza la disciplina de ingeniería.

La amplifica.

---

## Valores predeterminados de ingeniería

### Preferir

- modularidad monolítica antes de distribuir;
- Markdown antes que formatos personalizados;
- memoria local antes que memoria distribuida;
- contratos explícitos antes que comportamiento implícito;
- flujos deterministas antes que ciclos autónomos;
- herramientas sencillas antes que plataformas de orquestación;
- sistemas legibles por personas antes que sistemas opacos.

### Evitar por defecto

- microservicios prematuros;
- sistemas recursivos de agentes;
- orquestación innecesaria;
- proliferación de frameworks;
- estado mutable oculto;
- abstracción excesiva;
- cadenas de herramientas sin necesidad operativa;
- complejidad distribuida sin beneficio medible.

---

## Gobernanza humana

Todos los sistemas deberían seguir siendo:

- inspeccionables;
- reversibles;
- auditables;
- comprensibles para las personas.

El control agéntico es una delegación acotada: el agente puede analizar, recomendar y elegir cómo realizar el trabajo dentro del objetivo, alcance y permisos recibidos. Esa delegación no equivale a autoridad humana ni amplía la autorización. El agente no debe presentar una recomendación como aprobación ni atribuirse decisiones reservadas a una persona.

Los operadores humanos deben conservar:

- control;
- capacidad de anulación;
- visibilidad arquitectónica;
- y autoridad final sobre decisiones y aprobaciones que las políticas reserven a las personas.

El agente puede ejecutar acciones ya autorizadas dentro del alcance solicitado sin pedir aprobación repetida. Debe aclarar límites ambiguos y aplazar una acción cuando exceda el alcance o una política exija autorización o revisión humana. No reduzcas controles humanos para acelerar o automatizar.

Si solo la IA comprende el sistema, la gobernanza ha fallado.

---

## Restricciones de sistemas de IA

Los sistemas de IA deben:

- minimizar el contexto innecesario;
- minimizar las superficies de alucinación;
- minimizar la ambigüedad operativa;
- minimizar la proliferación de dependencias.

Cada capacidad añadida aumenta:

- la carga cognitiva;
- la complejidad de runtime;
- la superficie de fallo;
- la carga de mantenimiento.

Las capacidades deben seguir justificándose con el tiempo.

---

## Gobernanza de la complejidad

El objetivo no es el minimalismo.

El objetivo es la complejidad controlada.

Algunos sistemas requieren legítimamente:

- distribución;
- orquestación;
- ejecución asíncrona;
- sistemas de recuperación;
- infraestructura avanzada.

Cuando se introduzca complejidad, debe ser:

- explícita;
- justificada;
- medible;
- mantenible;
- reversible.

---

## Principios operativos

Antes de añadir algo, pregunta:

- ¿Esto ya existe?
- ¿Se puede eliminar?
- ¿Se puede integrar?
- ¿Se puede simplificar?
- ¿Es necesario en la operación?
- ¿Reduce o aumenta la carga cognitiva?
- ¿Las personas pueden auditarlo fácilmente?

---

## Advertencia arquitectónica

La mayoría de los sistemas de IA fallan porque:

- automatizan el desorden;
- distribuyen la ambigüedad;
- optimizan soluciones temporales;
- y escalan la complejidad más rápido que la comprensión.

La sofisticación no es calidad arquitectónica.

La claridad sí lo es.

---

## Principio final

> La mejor arquitectura de IA no es la más avanzada.
>
> Es la que preserva la claridad y minimiza la complejidad innecesaria.
