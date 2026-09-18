# Ingeniería asistida por IA y MCP

## Principio

La IA se utilizó como acelerador de exploración, implementación, revisión y
documentación; las decisiones que afectan seguridad, métricas y reproducibilidad
se verificaron con código, fixtures, hashes o inspección humana.

## Usos concretos

| Área | Asistencia | Control aplicado |
|---|---|---|
| Arquitectura | Comparación de pipelines YOLO-seg/SAM-2/tracker | Contratos y límites explícitos |
| Geometría | Revisión de homografía, escala y perspectiva | Casos sintéticos y rechazo de extrapolación |
| Tracking | Propuestas de Hungarian, Kalman y ciclo de vida | Cruces, oclusiones y detecciones faltantes |
| Anotación | Propagación de máscaras con SAM-2 en Label Studio | Revisión humana y procedencia por máscara |
| Automatización | Generación de scripts de empaquetado y validación | Ejecución literal en Docker y hashes |
| Investigación | Búsqueda de referencias dimensionales y licencias | Fuentes registradas y supuestos declarados |
| MCP | Control de herramientas, navegador y sesiones de trabajo | Acciones acotadas, sin publicar credenciales |

## Reglas de seguridad

- Una respuesta de un agente no se considera evidencia por sí sola.
- Los resultados se validan contra archivos, comandos, tests o imágenes.
- Las propuestas de SAM-2 no se mezclan con máscaras humanas sin marcar su origen.
- No se publican datos privados para hacer la demo más convincente.
- Un resultado no concluyente se mantiene como N/D.

## Trabajo multiagente

Cuando se usaron agentes distintos, cada responsabilidad se documentó y el
resultado se integró sólo después de revisar interfaces, dependencias y pruebas.
Esto permite explicar qué aceleró la IA y qué permaneció bajo control humano.
