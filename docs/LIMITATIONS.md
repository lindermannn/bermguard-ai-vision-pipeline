# Limitaciones que deben permanecer visibles

- La altura y las distancias de Método 2 son estimaciones si no existe
  calibración externa defendible.
- SAM-2 propaga una indicación; no reemplaza un detector entrenado del pretil.
- Las máscaras aceptadas desde propagación no equivalen automáticamente a verdad
  humana.
- La validación con frames del mismo video no mide generalización a otra cámara.
- Los videos sintéticos sirven para probar contratos, no para declarar precisión
  real en faena.
- La transición día/noche no debe confundirse con un movimiento de cámara.
- La ausencia de evidencia debe producir N/D, no una alerta falsa ni un verde
  tranquilizador.
