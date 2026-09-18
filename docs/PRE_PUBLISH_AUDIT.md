# Auditoría previa a publicación

## Orden

1. Ejecutar `scripts/validate_publication.py`.
2. Revisar manualmente cada coincidencia de secreto o ruta privada.
3. Escanear el historial Git si ya existe.
4. Confirmar que no se incluyeron datos de la prueba ni pesos sin licencia.
5. Ejecutar tests desde una instalación limpia.
6. Revisar README, licencia y contacto de seguridad.
7. Crear tag de selección sólo después de la revisión.

## Criterio de bloqueo

Un hallazgo de token, video, base de datos, peso grande o documento confidencial
bloquea el `push` hasta retirarlo y comprobar que no quedó en el historial.
