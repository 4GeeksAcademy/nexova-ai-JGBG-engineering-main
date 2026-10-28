# Límites de datos del formulario de talento

**Ámbito previsto:** cambios en `uis/website/**`. La carga automática de reglas desde `.agents/rules/` no está verificada en este repositorio.

## Objetivo

Preservar el propósito y los límites documentados del formulario de registro de talento de Nexova.

## Reglas obligatorias

- Trata el formulario como parte de un sitio estático: el envío actual se simula en el navegador y no transmite ni almacena información.
- No añadas envío de datos, persistencia, analítica sobre candidatos ni integraciones con sistemas externos sin autorización explícita del desarrollador y requisitos de privacidad y arquitectura aprobados.
- No presentes el formulario como un sistema de recepción o almacenamiento real de candidaturas. Si se autoriza un cambio de comportamiento, documenta con precisión qué datos procesa y dónde se transmiten o almacenan.
- Usa únicamente datos sintéticos en ejemplos y comprobaciones. No incluyas información personal real de candidatos.
- Mantén el formulario orientado a profesionales que buscan oportunidades laborales; no lo conviertas en un formulario de captación de empresas.

## Verificación

- Comprueba el flujo y las validaciones del formulario conforme al README de `uis/website/`; no trates `npm test` como una suite automatizada, porque es un placeholder.
- Si un cambio autorizado incorpora transmisión o almacenamiento, verifica y documenta esos comportamientos antes de afirmar que están implementados.
