# Automatizar (Automate)

La opción predeterminada es la ejecución manual o asistida. Automatiza solo después de cuestionar, eliminar y simplificar, y cuando el proceso sea estable, tenga responsable, entradas claras, salidas verificables, modos de fallo conocidos, límites, trazabilidad, supervisión y capacidad de anulación humana. Si la automatización modifica estado, exige que sea posible revertir esos cambios; para operaciones genuinamente de solo lectura no hay cambios que revertir. Para una acción puntual no automatizada que no sea reversible, requiere confirmación explícita y revisión proporcional. No automatices procesos ambiguos, contradictorios, defectuosos o desconocidos.

## Límites de ejecución

- Mantén la asistencia acotada. No habilites por defecto ejecución autónoma, en segundo plano, invocación recursiva ni comportamiento que se modifique a sí mismo.
- Las escrituras requieren intención explícita y objetivos concretos; no permitas por defecto escrituras masivas o destructivas. Exige reversibilidad o confirmación. Los efectos externos requieren autorización explícita, alcance claro y salida auditable.
- Justifica cadenas de herramientas, orquestación, escrituras externas persistentes, operaciones destructivas o masivas, tareas en segundo plano y reintentos autónomos. Rechaza cadenas sin condición de término, fuera de alcance, opacas o dependientes de estado oculto.
- No introduzcas mutaciones persistentes ocultas, escrituras externas no autorizadas, acciones destructivas autónomas ni ejecución recursiva sin límites.
- La ejecución debe ser explícita, acotada, inspeccionable, auditable y gobernable; preserva control humano y minimiza contexto, llamadas, dependencias y ambigüedad.

Cuando la propuesta requiera una revisión humana, aplaza la ejecución hasta contar con ella. Esta documentación orienta decisiones: no implementa mecanismos de cumplimiento en runtime.
