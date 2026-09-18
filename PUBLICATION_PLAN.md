# Plan de publicación en GitHub

## Objetivo

Presentar en una selección técnica una demostración verificable de seis días de
trabajo con visión computacional, IA asistida, MCP, automatización de pipelines y
validación, sin publicar material confidencial de la prueba.

## Decisión de publicación

1. Crear primero un repositorio privado.
2. Publicar sólo código, documentación redactada, fixtures sintéticos y métricas
   que no permitan reconstruir los videos originales.
3. Mantener la entrega enviada y el archivo histórico fuera del repositorio público.
4. Hacer una revisión legal/licencias antes de volverlo público.
5. No hacer `push` hasta revisar el informe de `validate_publication.py`.

## Material permitido

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

## Estructura de ramas

```text
main              versión publicable y reproducible
release/selection versión preparada para enviar a reclutadores
work/*            cambios experimentales, nunca datos privados
```

## Historia de commits sugerida

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

## Checklist antes de `git push`

- [ ] El repositorio no contiene videos, pesos, secretos ni rutas personales.
- [ ] `validate_publication.py` termina con código 0.
- [ ] Tests pasan en un entorno limpio.
- [ ] Cada gráfico tiene origen y limitación documentados.
- [ ] Las licencias de Ultralytics, SAM-2 y modelos están revisadas.
- [ ] README explica instalación y una ejecución sintética.
- [ ] El historial no contiene un secreto borrado posteriormente.
- [ ] Se hizo revisión final como si el reclutador no conociera el contexto.
