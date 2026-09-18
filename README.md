# BermGuard — AI-assisted computer vision pipeline

Repositorio público curado para documentar una prueba técnica de seis días sobre
monitoreo de vehículos mineros y pretiles.

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

## Reproducibilidad

El código publicable debe poder ejecutarse con datos sintéticos o propios:

```bash
python -m venv .venv
python -m pip install -r requirements.txt
python -m pytest -q
python scripts/validate_publication.py
```

Los videos y modelos se inyectan fuera del repositorio mediante variables o rutas
locales documentadas. No se descargan datos privados durante las pruebas.

## Documentación

- [Plan de publicación](PUBLICATION_PLAN.md)
- [Ingeniería asistida por IA](AI_ASSISTED_ENGINEERING.md)
- [Mapa de procedencia](docs/PROVENANCE_MAP.md)
- [Limitaciones y honestidad experimental](docs/LIMITATIONS.md)
- [Auditoría antes del primer commit](docs/PRE_PUBLISH_AUDIT.md)

## Licencia

La licencia del repositorio debe decidirse después de revisar los términos de la
prueba, Ultralytics/YOLO, SAM-2 y los checkpoints. Hasta cerrar esa revisión, el
repositorio debe permanecer privado.
