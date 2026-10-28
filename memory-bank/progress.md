# Progreso del proyecto: Nexova Solutions

## Alcance y criterio de estado

Este documento registra el estado conocido del proyecto transversal de Ingeniería impulsada por IA de 4Geeks Academy y los siguientes pasos. La fecha de esta revisión es **2026-10-28**.

- **Documentado como implementado:** así lo describe un README; no implica que se haya validado de forma independiente.
- **Verificado:** existe un resultado de comprobación registrado.
- **Pendiente:** las fuentes identifican una comprobación o trabajo aún por hacer.
- **Propuesto / sin implementación acreditada:** aparece como objetivo o idea, pero las fuentes consultadas no prueban su implementación.
- **Por confirmar:** la evidencia permitida no basta para afirmar el estado.

No se registran fechas de entrega, porcentajes de avance ni resultados que no estén respaldados por las fuentes o por una verificación registrada.

## Documentación del banco de memoria

| Documento                     | Estado                                                                                                                 |
| ----------------------------- | ---------------------------------------------------------------------------------------------------------------------- |
| `memory-bank/projectbrief.md` | Existe. Resume el contexto de Nexova y delimita Marketing y Operaciones de Selección como las áreas elegidas.          |
| `memory-bank/techContext.md`  | Existe. Distingue configuración documentada, recomendaciones y decisiones técnicas no verificadas.                     |
| `memory-bank/progress.md`     | Este documento. Registra el estado y los próximos pasos; debe actualizarse cuando haya resultados nuevos comprobables. |

## Hito 1: web pública

**Documentado como implementado en `uis/website/README.md`, no validado aquí:**

- Landing corporativa con navegación, secciones del briefing, metadatos SEO y JSON-LD de Schema.org.
- Formulario separado de registro de talento con 11 campos y diseño responsive descrito como basado en Tailwind CSS.
- Validación en navegador, mensajes de error, estados ARIA, contador de comentarios, limpieza y simulación de envío.
- El sitio está en español. El formulario no transmite ni almacena información; muestra el mensaje de éxito definido en el briefing.

**Pendiente de ejecutar y registrar según el README de la web:**

- Pruebas funcionales de los 11 campos, reglas, mensajes, corrección de errores, limpieza y envío simulado.
- Revisión en navegador de la experiencia responsive y el flujo del formulario.
- Comprobaciones de accesibilidad con teclado y herramientas apropiadas.
- Auditoría Lighthouse o PageSpeed con resultados registrados; no hay una puntuación confirmada en las fuentes.
- Prueba de acceso a la URL pública de Codespaces.

El README indica que `npm test` es un placeholder y no ejecuta una suite automatizada real. Por tanto, la descripción de funcionalidades no equivale a pruebas aprobadas ni a un hito verificado.

## Infraestructura de agentes

| Elemento                                                  | Estado observado                                                                                                                                               |
| --------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `AGENTS.md` en la raíz                                    | Existe. Define la lectura inicial del banco de memoria, las protecciones del repositorio y el protocolo previo a cada commit.                                  |
| `.agents/rules/talent-form-data-boundaries.md`            | Existe. Establece límites para el flujo simulado del formulario de talento y el tratamiento de datos. Su activación automática está **NO VERIFICADA**.         |
| `.agents/skills/website-seo-accessibility-audit/SKILL.md` | Existe. Define una auditoría de solo lectura de SEO y accesibilidad con evidencia, estados y recomendaciones. Su activación automática está **NO VERIFICADA**. |

Las guías del monorepo describen `agents/` y `skills/` como áreas de producto; no deben confundirse con `.agents/`, que contiene configuración del agente. La existencia de estos archivos no demuestra que haya agentes de Nexova implementados. El README raíz todavía indica que `AGENTS.md` no existe; esa referencia documental está desactualizada y no se modifica en este registro.

## Automatizaciones propuestas sin implementación acreditada

Las fuentes presentan estas capacidades como necesidades del briefing o propuestas de `company-choice.md`; no hay en ellas evidencia de que estén construidas o desplegadas.

| Área                              | Trabajo propuesto aún no acreditado                                                                                                                                                                                             |
| --------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Marketing y Comunicación          | Pipeline de contenido asistido por IA con revisión humana; dashboard de visitas, fuentes de tráfico y conversiones.                                                                                                             |
| Operaciones de Selección          | Análisis de CV y comparación con vacantes; scoring y ranking explicables; búsqueda RAG; portal con estado de candidaturas; comunicaciones automáticas de seguimiento. La propuesta mantiene la decisión final en manos humanas. |
| Ventas y Desarrollo de Negocio    | Dashboard de pipeline, secuencias de prospección, alertas por conversaciones inactivas y agente que sugiera el ángulo de propuesta.                                                                                             |
| Recursos Humanos interno          | Portal, onboarding automatizado, dashboard de KPIs y agente para consultas de políticas y beneficios.                                                                                                                           |
| Formación Corporativa             | Catálogo e inscripción online, recomendaciones, portal del alumno y chatbot de asesoramiento.                                                                                                                                   |
| Atención al Cliente externalizado | Chatbot de primera línea, base de conocimiento con búsqueda semántica, dashboard en tiempo real y análisis de sentimiento. El objetivo del 40% de resolución automática es una meta del briefing, no un resultado medido.       |
| Tecnología e Infraestructura      | Telemetría y logging centralizados, pipeline de datos, monitorización con alertas y agente de consulta de documentación técnica.                                                                                                |
| Dirección Ejecutiva               | Dashboard unificado, informes automáticos, alertas por umbral y asistente en lenguaje natural.                                                                                                                                  |

El foco elegido en `projectbrief.md` es Marketing y Operaciones de Selección. Las demás áreas se mantienen como contexto del briefing, no como alcance aprobado del proyecto estudiantil.

## Próximos pasos

Ordenados según los hitos enumerados en el README del monorepositorio; no representan fechas ni compromisos de entrega:

1. **Web / Hito 1:** ejecutar y registrar las comprobaciones funcionales, responsive, de accesibilidad, Lighthouse/PageSpeed y acceso público que enumera el README de la web.
2. **Infraestructura documental de agentes:** `AGENTS.md`, la regla de límites del formulario y la skill de auditoría SEO/accesibilidad existen. Sigue pendiente verificar la activación automática de la regla y de la skill; ambas permanecen **NO VERIFICADAS**. También queda pendiente actualizar, con autorización, la afirmación desactualizada del README raíz sobre la ausencia de `AGENTS.md`.
3. **Programming:** continuar con el hito de programación indicado por el README.
4. **Backend:** definir requisitos e implementar el backend que se apruebe; no se presupone FastAPI ni otra tecnología como ya elegida.
5. **Telemetry:** establecer qué métricas y eventos necesitan las áreas priorizadas antes de declarar dashboards o monitorización como hechos.
6. **RAG:** definir fuentes y criterios de evaluación antes de abordar la búsqueda semántica propuesta para selección.
7. **Agents:** desarrollar y evaluar agentes solo después de acordar fuentes, herramientas y supervisión.
8. **Workflows:** automatizar secuencias después de definir reglas, permisos y condiciones de activación.
9. **Real-time:** abordar capacidades en tiempo real cuando haya requisitos y una base técnica verificada.

La secuencia Web → Programming → Backend → Telemetry → RAG → Agents → Workflows → Real-time sigue el orden que lista la guía del monorepo. Los detalles de implementación, responsables, calendario y criterios cuantitativos siguen pendientes de definición.

## Estado de Git

Consulta de solo lectura ejecutada antes de crear este documento, el **2026-10-28**:

```text
 M BRIEFING.md
?? memory-bank/projectbrief.md
?? memory-bank/techContext.md
```

La salida refleja el estado observado en ese momento; no atribuye autoría ni causa a los cambios. La creación de este archivo ocurre después de esa captura.

## Fuentes y actualización

- [BRIEFING.md](../BRIEFING.md): requisitos del Hito 1 y contexto empresarial, problemas y necesidades de automatización de Nexova.
- [projectbrief.md](projectbrief.md): áreas elegidas, riesgos y propuestas del proyecto.
- [techContext.md](techContext.md): contexto técnico y límites de lo que está configurado o verificado.
- [company-choice.md](../company-choice.md): selección personal de áreas y propuestas de solución.
- [README.es.md](../README.es.md): organización del monorepo y orden de hitos.
- [README de la web](../uis/website/README.md): funcionalidades descritas y pruebas que siguen pendientes.
- [AGENTS.md](../AGENTS.md): instrucciones de sesión, protecciones y protocolo precommit.
- [Regla de límites del formulario](../.agents/rules/talent-form-data-boundaries.md): límites de datos y comportamiento del formulario de talento.
- [Skill de auditoría web](../.agents/skills/website-seo-accessibility-audit/SKILL.md): procedimiento de auditoría SEO y accesibilidad de solo lectura.

Al actualizar este registro, adjuntar la comprobación realizada y su resultado. Mantener como pendiente cualquier prueba sin resultado, diferenciar documentación de validación y no presentar una propuesta como funcionalidad implementada.
