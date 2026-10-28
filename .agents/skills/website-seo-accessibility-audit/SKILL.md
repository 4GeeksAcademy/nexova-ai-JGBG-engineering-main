---
name: website-seo-accessibility-audit
description: "Audita el SEO técnico básico y la accesibilidad de la web de Nexova. Úsala cuando se solicite revisar títulos, metadescripciones, HTML semántico, enlaces, imágenes, etiquetas de formularios o navegación por teclado en uis/website/."
---

# Auditoría SEO y accesibilidad de la web

## Objetivo

Auditar de forma reproducible el SEO técnico básico y la accesibilidad de la web corporativa existente, sin modificar código, configuración, dependencias ni datos.

## Cuándo usarla

Usa esta skill cuando se solicite auditar o revisar SEO o accesibilidad de `uis/website/`. Su alcance predeterminado incluye la landing y el formulario de registro de talento. No extiendas la revisión a otras aplicaciones ni a una URL pública sin autorización.

## Entradas

- La raíz del repositorio y el alcance autorizado. Por defecto, `uis/website/**`.
- Las instrucciones del repositorio: `AGENTS.md`, `memory-bank/projectbrief.md`, `memory-bank/techContext.md` y `memory-bank/progress.md`.
- La documentación del sitio: `BRIEFING.md` y `uis/website/README.md`.
- Los archivos existentes pertinentes: `index.html`, `application.html`, `validation.js`, `src/input.css`, `dist/styles.css` y `package.json`.
- Para comprobaciones en navegador: un navegador y una URL local o pública ya disponible y autorizada. Si no están disponibles, registra la comprobación como pendiente; no instales herramientas ni inicies servicios para completar la auditoría.

## Procedimiento de solo lectura

1. Confirma el alcance autorizado y lee las instrucciones y documentación de entrada. Registra cualquier limitación del entorno.
2. Comprueba en `package.json` y el README qué herramientas están documentadas o configuradas. No supongas que una herramienta está disponible por estar mencionada como recomendación.
3. Inspecciona `index.html` y `application.html` y registra evidencia con ruta y número de línea cuando sea posible:
   - Idioma del documento, título y metadescripción.
   - Uso de elementos semánticos, landmarks y jerarquía de encabezados.
   - Enlaces: texto descriptivo, destino y estado de los destinos locales que puedan comprobarse sin acceso externo.
   - Imágenes: presencia y adecuación contextual de `alt`; distingue imágenes decorativas.
   - JSON-LD u otros metadatos estructurados presentes, sin afirmar que se hayan validado contra servicios externos.
4. Inspecciona el formulario y `validation.js` para comprobar asociaciones entre `label`, `id` y controles, agrupación de campos, nombres accesibles declarados, mensajes de error, estados ARIA y referencias entre errores y campos. Distingue lo que el código declara de lo que se percibe al usarlo.
5. Comprueba navegación por teclado, orden y visibilidad del foco solo en un navegador disponible y sobre una URL autorizada. No infieras el resultado a partir del HTML o CSS. No envíes datos reales.
6. Ejecuta Lighthouse, axe u otras herramientas únicamente si están instaladas o disponibles y su uso está autorizado. Registra nombre, versión si se conoce, método y resultado. No instales dependencias, no ejecutes builds que puedan regenerar archivos y no trates `npm test` como una suite automatizada: el README lo identifica como placeholder.
7. Clasifica cada comprobación como `verificada estáticamente`, `verificada en navegador`, `pendiente`, `no verificable` o `no aplicable`. Si faltan herramientas, URL o evidencia, indica el motivo sin convertirlo en un hallazgo confirmado.
8. Emite el informe sin corregir hallazgos ni modificar archivos.

## Gravedad

- **Alta:** la evidencia muestra una barrera que impide acceder a contenido esencial, navegar o completar una tarea principal, o una condición que puede impedir que la página sea indexada.
- **Media:** un problema comprobado afecta significativamente la comprensión, navegación, interpretación del contenido o presentación en buscadores, sin bloquear por completo la tarea principal.
- **Baja:** una mejora comprobada que no bloquea la tarea ni impide interpretar el contenido.
- **Informativa:** observación sin defecto confirmado o recomendación preventiva; no la presentes como incumplimiento.

Asigna gravedad solo con evidencia observada. No inventes puntuaciones, umbrales de conformidad ni garantías de posicionamiento.

## Criterios de aceptación

- El informe cubre `index.html` y `application.html` y registra el resultado de cada categoría aplicable: estructura semántica, título, metadescripción, enlaces, imágenes y `alt`, etiquetas de formulario y navegación por teclado.
- Cada hallazgo incluye una ruta y línea, o el método y entorno de la comprobación en navegador. Sin evidencia suficiente, queda como pendiente o no verificable, no como defecto confirmado.
- Cada hallazgo confirmado incluye gravedad, impacto y recomendación; toda categoría revisada tiene un estado explícito.
- El informe separa comprobaciones estáticas de las realizadas en navegador y enumera las pendientes con su motivo.
- Solo declara herramientas, comandos y resultados que se hayan observado durante esta ejecución.
- No se modifican archivos, dependencias, configuración ni datos durante la auditoría.

## Salida

Entrega un informe Markdown que incluya:

- Alcance, fecha de revisión, entorno y archivos inspeccionados.
- Resumen breve de resultados y limitaciones.
- Hallazgos con identificador, categoría, gravedad, estado, evidencia (`ruta:línea` cuando sea posible), impacto y recomendación.
- Una lista separada de comprobaciones realizadas y pendientes o no verificables, con su motivo.
- Herramientas, comandos y resultados solo cuando realmente se hayan utilizado.

No declares conformidad global, certificación WCAG, puntuación Lighthouse ni validación de Schema.org salvo que una comprobación apropiada se haya ejecutado y su resultado esté disponible. La skill informa; no repara.
