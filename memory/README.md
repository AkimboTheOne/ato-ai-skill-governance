# Modelo de memoria operativa

## Propósito

Esta carpeta define cómo se debe gestionar la memoria de gobernanza de esta skill.

La skill debe distinguir entre:

1. **memoria de la skill**: memoria permanente sobre la propia skill de gobernanza;
2. **memoria de instalación**: memoria local creada al aplicar la skill en un usuario, proyecto, repositorio, organización o entorno de agentes concreto;
3. **memoria global del usuario**: preferencias o contexto del usuario que no pertenecen a un único repositorio.

Mezclar estos tipos de memoria produce desviaciones de gobernanza.

---

## Límites de memoria

### Memoria de la skill

La memoria de la skill pertenece a este repositorio.

Registra:

- la evolución de la doctrina;
- decisiones de gobernanza;
- patrones arquitectónicos rechazados;
- cambios de madurez;
- aprendizajes de revisión;
- cambios en la política de activación;
- cambios en la política de runtime;
- y lecciones aplicables a todas las instalaciones de la skill.

La memoria de la skill es memoria del producto.

Debe versionarse junto con la skill.

---

### Memoria de instalación

La memoria de instalación pertenece al entorno que consume la skill.

Registra:

- decisiones específicas del proyecto;
- preferencias del usuario;
- restricciones locales;
- excepciones locales;
- instancias revisadas de la skill;
- resultados de gobernanza específicos del repositorio;
- postura de riesgo propia de la organización;
- y compensaciones contextuales.

La memoria de instalación es contexto operativo.

No debe incorporarse al repositorio canónico de la skill salvo que se convierta en un aprendizaje generalizable.

---

### Memoria global del usuario

La memoria global del usuario pertenece al entorno del agente o producto que consume la skill, no a este repositorio ni a un repositorio consumidor. En Codex corresponde a la memoria global del usuario de Codex.

Registra preferencias y contexto generales que no corresponden a un repositorio, organización o instancia de la skill concretos.

La memoria global del usuario es contexto de respaldo.

No debe prevalecer sobre la memoria local de instalación del repositorio activo.

---

## Regla predeterminada

> El repositorio canónico de la skill almacena conocimiento de gobernanza reutilizable.
>
> La instalación almacena el historial operativo local.
>
> La memoria global del usuario almacena preferencias generales solo cuando no existe una decisión más específica en la memoria local del repositorio.

---

## Precedencia de memoria

Cuando la plataforma disponga de estas capas de memoria, al aplicar esta skill en un repositorio se debe leer la memoria en este orden:

1. **Memoria local de instalación del repositorio**, en `.ato-skill-governance/`.
2. **Memoria global del usuario**, en el entorno del agente que consume la skill (por ejemplo, Codex).
3. **Memoria canónica de la skill**, en `memory/`.

La memoria local de instalación del repositorio tiene prioridad para las decisiones sobre el repositorio activo.

La memoria global del usuario puede orientar valores predeterminados, pero no debe anular decisiones explícitas locales.

La memoria canónica de la skill gobierna la doctrina reutilizable. No debe almacenar preferencias específicas del repositorio o usuario, decisiones confidenciales de la organización ni excepciones locales.

---

## Estructura reservada para la memoria del repositorio

El repositorio canónico de la skill puede usar esta estructura cuando exista memoria de la skill real y reutilizable:

```text
memory/
├── README.md
├── decisions/
├── learnings/
├── rejected-patterns/
├── evolution/
└── installation-template/
```

Estos directorios son puntos de extensión reservados; no es obligatorio crearlos vacíos. No los crees hasta que exista contenido auditable que justifique su presencia.

---

## Estructura de la memoria de instalación

Un repositorio consumidor puede crear:

```text
.ato-skill-governance/
├── decisions/
├── reviews/
├── exceptions/
├── maturity/
└── context.md
```

Esta memoria local pertenece a la instalación.

Debe ser legible por personas, auditable y eliminable sin romper la skill canónica.

---

## Regla de promoción

Un aprendizaje de una instalación local puede promoverse a la memoria canónica de la skill solo si:

- es reutilizable entre instalaciones;
- no depende de contexto privado;
- no es específico del usuario;
- no es confidencial de la organización;
- y concuerda con la doctrina central.

La promoción debe ser explícita.

No incorpores contexto local a la skill de forma silenciosa.

El agente puede detectar aprendizajes, evaluar su generalización y preparar una recomendación o borrador dentro de la tarea autorizada. No tiene autoridad para aprobar ni aplicar la promoción por sí mismo; la aprobación humana explícita es necesaria antes de modificar la memoria canónica.

---

## Propuesta de promoción doctrinal

La skill debería recomendar una promoción cuando detecte una doctrina nueva que sea:

- reutilizable entre instalaciones;
- compatible con la doctrina central;
- útil para la gobernanza futura de skills;
- respaldada por contexto concreto o uso repetido;
- no confidencial;
- no específica del usuario;
- y no sea solo una preferencia local del proyecto.

Esto es autogestión controlada, no mutación automática.

Al recomendar la promoción, la skill debe proporcionar:

- la doctrina propuesta;
- la evidencia o el contexto que la motivó;
- su compatibilidad con la doctrina central;
- los riesgos o compensaciones;
- el destino canónico sugerido;
- y un borrador que una persona pueda revisar.

El borrador no debe aplicarse a la memoria canónica sin aprobación humana explícita.

Rechaza la promoción si la propuesta:

- contradice el orden `Question -> Eliminate -> Simplify -> Accelerate -> Automate`;
- introduce memoria oculta u opaca;
- promueve la automatización antes de la estabilidad del proceso;
- amplía el comportamiento en runtime sin gobernanza;
- añade complejidad injustificada;
- o convierte una preferencia local en doctrina general.

---

## Antipatrones

Evita:

- almacenar contexto del usuario en la memoria canónica de la skill;
- almacenar decisiones de la organización en la skill reutilizable;
- tratar excepciones de instalación como doctrina;
- permitir que desviaciones locales reescriban principios globales;
- permitir que la memoria global del usuario prevalezca sobre las decisiones locales del repositorio;
- escribir propuestas de promoción directamente en la memoria canónica sin revisión;
- ocultar la memoria de gobernanza en estado opaco de runtime.

---

## Principio final

> La memoria de la skill gobierna el producto.
>
> La memoria de instalación gobierna la aplicación local del producto.
