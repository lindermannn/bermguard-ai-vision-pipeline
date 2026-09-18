# Resumen para selección técnica

## Versión corta

En seis días convertí una prueba de visión computacional en un pipeline modular y
verificable para vehículos mineros y pretiles. Integré YOLO-seg, SAM-2, tracking
temporal y geometría de cámara; construí contratos, pruebas sintéticas, auditorías
de integridad y un ejecutor Docker reproducible. Usé IA y MCP para acelerar la
exploración y automatización, manteniendo validación humana y trazabilidad de las
decisiones.

## Evidencia que debe acompañar el repositorio

- Diagrama del pipeline.
- Un fixture sintético reproducible.
- Un reporte de tests.
- Un ejemplo de salida N/D sin calibración.
- Un gráfico de trayectoria o distancia sin frames privados.
- Un registro de limitaciones y decisiones descartadas.

## Preguntas que el repositorio debe responder

1. ¿Qué ocurre si no existe una máscara del pretil? — Se publica N/D con motivo.
2. ¿Qué ocurre durante una oclusión? — El tracker predice durante un TTL y separa
   observación de predicción.
3. ¿Cómo se evita inventar metros? — La geometría exige un modelo válido y deja
   la distancia en píxeles o N/D cuando corresponde.
4. ¿Cómo se comprobó el trabajo? — Tests deterministas, Docker, hashes y revisión
   visual; no sólo una demo.
5. ¿Qué parte fue IA? — Exploración y automatización asistidas, con revisión y
   evidencia antes de aceptar cualquier resultado.
