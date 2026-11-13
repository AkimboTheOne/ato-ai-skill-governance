# Plantilla de charter de skill

## Propósito

Este documento define la identidad operativa, los límites arquitectónicos, las restricciones de comportamiento y las expectativas de gobernanza de una skill.

Una skill debe ser:

- comprensible;
- acotada;
- mantenible;
- componible;
- y gobernable en la operación.

---

# Identidad de la skill

## Nombre técnico

`<skill-name>`

Debe coincidir con `name` en `SKILL.md` y con el directorio de la skill.

## Nombre descriptivo

`<nombre legible para personas>`

Debe reflejar el propósito de la skill y ser coherente con su nombre técnico y el título de `SKILL.md`. Si la plataforma objetivo define un campo de nombre visible, mantenlo coherente; en Codex, ese campo puede ser `interface.display_name` en `agents/openai.yaml`.

---

## Idioma y convenciones técnicas

Redacta el contenido en el idioma más adecuado para la audiencia de esta skill. El repositorio puede contener skills en distintos idiomas.

Mantén en inglés los nombres de archivos y directorios, los campos e identificadores de metadata, los valores de contrato consumidos por herramientas y las keywords de industria establecidas. La prosa y los textos descriptivos de metadata pueden usar el idioma elegido. Conserva en inglés los términos técnicos establecidos cuando su traducción reduzca la precisión o dificulte su reconocimiento.

---

## Propósito principal

Describe la única capacidad operativa que esta skill debe proporcionar.

El propósito debe ser:

- explícito;
- acotado;
- significativo en términos operativos.

Evita objetivos vagos.

Una skill debería resolver un problema concreto.

No debería convertirse en una plataforma generalista.

---

## Fuera de alcance

Define explícitamente lo que la skill NO hace.

Ejemplos:

- motor de orquestación;
- runtime autónomo;
- plataforma de flujos de trabajo;
- infraestructura distribuida;
- generación de código genérica;
- memoria persistente oculta.

Si los límites no están claros, la desviación del alcance será inevitable.

---

# Alcance operativo

## Responsabilidades

Enumera las responsabilidades que pertenecen directamente a la skill.

Las responsabilidades deberían ser:

- medibles;
- claras en términos operativos;
- explícitas.

Prefiere capacidades operativas concretas frente a intenciones abstractas.

---

## Fuera del alcance operativo

Enumera las responsabilidades excluidas intencionalmente.

Todo lo que no se incluya explícitamente debería quedar fuera del alcance por defecto.

---

# Restricciones de ingeniería

## Orden obligatorio de ingeniería

La skill siempre debe operar en este orden:

1. Preguntar (Question)
2. Eliminar (Eliminate)
3. Simplificar (Simplify)
4. Acelerar (Accelerate)
5. Automatizar (Automate)

No optimices antes de simplificar.

No automatices antes de alcanzar estabilidad operativa.

---

## Restricciones de complejidad

La skill debería priorizar:

- comportamiento explícito;
- flujos deterministas;
- memoria legible por personas;
- contexto acotado;
- interfaces sencillas;
- operaciones directas.

Evita:

- estado oculto;
- orquestación recursiva;
- abstracciones innecesarias;
- distribución prematura;
- arquitectura con exceso de orquestación.

---

## Valores arquitectónicos predeterminados

### Preferir

- Markdown y texto sin formato;
- estructuras legibles desde el filesystem;
- patrones de monolito modular;
- contratos explícitos;
- ejecución determinista;
- razonamiento local.

### Requieren justificación explícita

- bases de datos vectoriales;
- pipelines RAG;
- sistemas multiagente;
- memoria distribuida;
- orquestación asíncrona;
- comportamiento autónomo en segundo plano;
- estado persistente oculto.

---

# Límites de runtime

## Modelo de ejecución

Define si la skill es:

- asistencial;
- consultiva;
- determinista;
- de solo lectura;
- habilitada para escritura;
- interactiva;
- acotada;
- autónoma.

El comportamiento de ejecución debe ser explícito.

---

## Restricciones de escritura

Si existen operaciones de escritura:

- requieren intención explícita;
- requieren objetivos acotados;
- requieren auditabilidad;
- requieren reversibilidad siempre que sea posible.

La skill no debe mutar estado oculto en silencio.

---

## Restricciones de memoria

La memoria debería ser:

- inspeccionable;
- editable;
- auditable;
- comprensible en términos operativos.

Evita el crecimiento descontrolado de memoria.

Prefiere memoria local y legible por personas.

---

# Gobernanza humana

El agente ejerce control delegado: puede analizar, recomendar y elegir medios dentro del objetivo, alcance y permisos recibidos. No tiene autoridad humana ni puede ampliar la autorización o tratar una recomendación como aprobación. La persona conserva la decisión final y la capacidad de anulación.

El agente ejecuta acciones ya autorizadas dentro del alcance sin pedir aprobación repetida. Aclara los límites ambiguos y aplaza acciones que excedan el alcance o requieran autorización o revisión humana según las políticas aplicables.

Los operadores humanos deben conservar:

- visibilidad;
- capacidad de anulación;
- conocimiento de la ejecución;
- control arquitectónico.

Si las personas no pueden entender qué hace la skill y por qué, la gobernanza ha fallado.

---

# Política de herramientas

## Principios de uso de herramientas

La skill debería:

- minimizar el uso innecesario de herramientas;
- evitar cadenas recursivas de herramientas;
- preferir operaciones deterministas;
- minimizar la complejidad de orquestación.

El uso de herramientas debe mantenerse:

- acotado;
- explicable;
- justificado en términos operativos.

---

# Restricciones de planificación

Antes de introducir una capacidad nueva, pregunta:

- ¿Resuelve un problema real?
- ¿Se puede simplificar?
- ¿Se puede integrar en un comportamiento existente?
- ¿Aumenta la carga cognitiva?
- ¿La complejidad es proporcional al problema?
- ¿Las personas todavía pueden razonar sobre el sistema?
- ¿Introduce sofisticación sin necesidad?

---

# Filosofía ante fallos

La skill debería fallar de forma:

- explícita;
- predecible;
- observable;
- recuperable.

Evita:

- degradación silenciosa;
- reintentos ocultos;
- orquestación encubierta;
- comportamiento opaco en runtime.

La claridad operativa importa más que una fluidez artificial.

---

# Principios de observabilidad

La skill debería preservar:

- visibilidad de la ejecución;
- trazabilidad operativa;
- comportamiento explicable;
- razonamiento determinista cuando sea posible.

Un operador humano debería entender:

- qué ocurrió;
- por qué ocurrió;
- y qué cambió.

---

# Gobernanza de la complejidad

El objetivo no es el minimalismo.

El objetivo es la complejidad controlada.

La sofisticación sin valor operativo es deuda arquitectónica.

---

# Principio final

> Una skill debe reducir la complejidad operativa más rápido de lo que crea complejidad arquitectónica.
