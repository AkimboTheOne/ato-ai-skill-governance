# TODO: Evaluación local del skill sin modificarlo

## Objetivo

Añadir al proyecto un conjunto de validaciones estáticas y evaluaciones de inferencia que comprueben cómo un modelo aplica las instrucciones de gobernanza. Las pruebas serán externas al skill y estarán sujetas a `AGENTS.md`. Sus resultados podrán recomendar ajustes; nunca modificarán el skill automáticamente.

## Implementación

- [ ] Crear un runner ligero en Python estándar, casos de prueba estructurados y una rúbrica legible en `evals/`. El runner leerá el skill y las referencias; no tendrá herramientas para editarlos.
- [ ] Para inferencia, enviar los casos a un endpoint local compatible con la API de chat OpenAI. Configurar endpoint y modelo por variables de entorno. Usar el mismo modelo como candidato y juez, con llamadas separadas; marcar el posible sesgo de autoevaluación en el informe.
- [ ] Evaluar dos aspectos: selección de referencias pertinentes a partir de `SKILL.md` y aplicación de instrucciones con el material pertinente cargado. No presentar la selección automática real de Codex u otro agente como probada.
- [ ] Incluir escenarios de recomendación sin ejecución, acción dentro del alcance autorizado, acción externa o irreversible que requiere autorización, promoción de memoria, ambigüedad de alcance y mención incidental.
- [ ] Añadir a `AGENTS.md` cómo ejecutar y mantener la suite, cómo interpretar sus resultados y que las conclusiones solo pueden producir recomendaciones humanas. No cambiar archivos del skill.
- [ ] Imprimir resultados y guardarlos solo si se solicita una ruta de salida; no incorporar respuestas del modelo como snapshots de referencia.

## Criterios y validación

- [ ] Ejecutar validaciones estáticas offline para comprobar metadatos requeridos y enlaces locales.
- [ ] Ejecutar cada escenario de inferencia tres veces por defecto. Evaluar criterios observables —decisión, respeto al alcance, autorización y referencia elegida— con una rúbrica estructurada y evidencia textual, no coincidencia exacta de frases.
- [ ] Marcar como fallo cualquier incumplimiento de autorización en escenarios críticos. Informar tasa de aprobación por escenario y variación entre corridas; no convertir una puntuación del juez en probabilidad de exactitud.
- [ ] Validar el protocolo con el endpoint local configurado, comprobar resultados reproducibles del formato y confirmar que la ejecución no escribe en el skill. Si no hay endpoint disponible, las pruebas estáticas deben seguir funcionando y la suite debe explicar cómo habilitar la evaluación de inferencia.

## Supuestos

- El entorno que ejecute inferencias proporcionará un endpoint local compatible y el modelo; no se instalará ni descargará un runner durante esta implementación.
- El mismo modelo juzgará sus respuestas por preferencia del usuario. Las salidas serán indicativas y revisables por una persona, no una garantía formal de cumplimiento.
