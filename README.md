# BermGuard — AI-assisted computer vision pipeline

Repositorio público curado para documentar una prueba técnica de seis días sobre
monitoreo de vehículos mineros y pretiles. La publicación de esta selección de
documentos está autorizada; la implementación entregada para la prueba sigue
fuera de este repositorio.

El proyecto combina segmentación, propagación temporal de máscaras, tracking,
geometría de cámara, validación reproducible y automatización asistida por IA.
Los datos originales de la prueba, los videos completos, los checkpoints grandes,
las credenciales y los entornos locales no forman parte de este repositorio.

## Pipeline

```text
YOLO-seg → vehículos individuales
SAM-2 → máscara del pretil y propagación temporal
Tracker → identidad persistente
Geometría → posición y distancia estimada
Fusión → salida por frame y diagnósticos
Validación → contratos, tests, hashes y limitaciones
```

## Qué demuestra

- Integración de modelos de visión en un ejecutor genérico para cualquier nombre de video.
- Separación explícita entre observación, estimación temporal, referencia histórica y N/D.
- Tracker con asociación global, oclusiones, detecciones faltantes y cambios de cámara.
- Estimación geométrica conservadora: no publica metros cuando la calibración no es defendible.
- Validación con fixtures sintéticos, revisión visual y auditoría SHA-256.
- Uso de IA y MCP como herramientas de aceleración, manteniendo revisión humana y evidencia.

## Estado y alcance

Este repositorio documenta infraestructura y decisiones de ingeniería. No pretende
presentar los videos de la prueba ni sus datos privados como un dataset público.
Las distancias de Método 2 son estimaciones basadas en referencias dimensionales y
un FOV supuesto cuando no existe una calibración externa; el sistema debe reportar
la limitación explícitamente.

## Qué se puede verificar aquí

Este repositorio contiene documentación y un verificador de publicación. No
incluye el pipeline ejecutable, los tests de la implementación, los modelos ni
los videos de la prueba. La comprobación local disponible es:

```bash
python scripts/validate_publication.py
```

El resultado esperado es `PUBLICATION_AUDIT_OK`. Este control busca artefactos
privados, rutas absolutas y cadenas similares a secretos en los archivos
publicados; no reproduce ni valida el desempeño del sistema de visión.

## Documentación

- [Plan de publicación](PUBLICATION_PLAN.md)
- [Ingeniería asistida por IA](AI_ASSISTED_ENGINEERING.md)
- [Mapa de procedencia](docs/PROVENANCE_MAP.md)
- [Limitaciones y honestidad experimental](docs/LIMITATIONS.md)
- [Auditoría antes del primer commit](docs/PRE_PUBLISH_AUDIT.md)

## Publicación y licencia

La publicación de este repositorio documental curado está autorizada. No se
publican pesos, videos, datasets ni código de terceros. No se ha añadido una
licencia de reutilización al contenido; la autorización de publicación no
equivale a conceder permisos de reutilización del proyecto o de la entrega.
