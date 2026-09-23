# Plan de publicación en GitHub

## Objetivo

Presentar en una selección técnica una demostración verificable de seis días de
trabajo con visión computacional, IA asistida, MCP, automatización de pipelines y
validación, sin publicar material confidencial de la prueba.

## Estado de publicación

La publicación del repositorio curado está autorizada y el repositorio ya es
público. Esta versión contiene documentación y el verificador de publicación;
la entrega, el código del pipeline, los tests, videos, pesos y el archivo
histórico siguen fuera. Antes de cada actualización pública se ejecuta
`validate_publication.py` y se revisa el diff y el historial afectado.

## Material que podría publicarse tras revisión específica

- Código propio de geometría, tracking, fusión y validación.
- Configuraciones de ejemplo sin rutas personales.
- Tests y fixtures sintéticos.
- Diagramas y gráficos generados sin frames de la faena.
- Hashes, conteos y resultados agregados.
- Documentación de decisiones y limitaciones.

## Material excluido

- Los cuatro videos originales o capturas que los hagan identificables.
- Exportaciones completas de Label Studio y bases SQLite.
- Máscaras de la faena, salvo ejemplos completamente anonimizados.
- Pesos `.pt`, `.pth`, `.onnx` o `.safetensors` sin autorización y revisión de licencia.
- Entornos `.venv`, cachés y archivos de configuración local.
- Tokens, claves, cookies, bases de datos y rutas de usuario.
- El ZIP enviado como artefacto de selección.
- Prompts o documentos que reproduzcan el enunciado confidencial completo.

## Estructura de ramas propuesta para futuras ampliaciones

```text
main              versión publicable y reproducible
release/selection versión preparada para enviar a reclutadores
work/*            cambios experimentales, nunca datos privados
```

## Historia de commits sugerida para futuras ampliaciones

```text
docs: define project scope and responsible disclosure
feat: add geometry and temporal tracking contracts
feat: add segmentation and temporal-memory adapters
test: add deterministic synthetic fixtures
docs: document AI-assisted engineering and MCP workflow
chore: add reproducible validation and publication audit
docs: prepare selection release
```

## Narrativa para la selección

El valor del trabajo no es únicamente haber conectado YOLO-seg y SAM-2. La
narrativa debe mostrar que se construyó un sistema verificable:

- se convirtió una petición ambigua en contratos y etapas reproducibles;
- se separaron datos observados de estimaciones temporales;
- se detectaron y corrigieron errores de geometría y tracking;
- se usó anotación asistida sin confundir propuestas con verdad de terreno;
- se automatizaron empaquetado, pruebas, hashes y validaciones;
- se documentaron las limitaciones en lugar de inventar precisión.

## Checklist antes de futuras ampliaciones públicas

- [ ] El repositorio no contiene videos, pesos, secretos ni rutas personales.
- [ ] `validate_publication.py` termina con código 0.
- [ ] Si se añade código ejecutable, sus tests pasan en un entorno limpio.
- [ ] Cada gráfico tiene origen y limitación documentados.
- [ ] Si se añaden dependencias, modelos o pesos, sus licencias y permisos de distribución están revisados.
- [ ] Si se añade código ejecutable, el README explica instalación y ejecución sintética.
- [ ] El historial no contiene un secreto borrado posteriormente.
- [ ] Se hizo revisión final como si el reclutador no conociera el contexto.
