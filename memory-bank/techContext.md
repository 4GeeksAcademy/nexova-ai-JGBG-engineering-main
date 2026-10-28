# Contexto técnico: Nexova Solutions

## 1. Propósito y criterio de evidencia

Este documento resume el contexto técnico disponible para el proyecto transversal de Ingeniería impulsada por IA de 4Geeks Academy. No presupone que una recomendación o necesidad de negocio ya esté implementada.

Se usan estas categorías:

- **Configurado en el repositorio:** respaldado por un archivo de configuración versionado.
- **Documentado:** descrito por un README, sin validación independiente de la implementación.
- **Recomendado o previsto:** guía de arquitectura o necesidad futura; no equivale a una decisión técnica implementada.
- **No verificado:** no hay evidencia suficiente en las fuentes revisadas.

## 2. Stack tecnológico con evidencia

| Área               | Estado y evidencia                                                                                                                                                                                                                                           |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| Sitio público      | **Configurado/documentado.** `uis/website/package.json` declara `tailwindcss` `^4.3.3` y `@tailwindcss/cli` `^4.3.0` como dependencias de desarrollo. Define `build` y `watch`, que ejecutan Tailwind CLI sobre `src/input.css` y generan `dist/styles.css`. |
| Entorno del sitio  | **Documentado.** `uis/website/README.md` requiere Node.js y npm, y prescribe ejecutar la instalación y los scripts desde `uis/website/`. `package.json` declara `type: commonjs`; esto no acredita por sí solo el uso de un framework de aplicación.         |
| Pruebas del sitio  | **No configuradas como suite.** El script `test` de `uis/website/package.json` imprime que no hay pruebas y termina con error. El README enumera comprobaciones funcionales, de accesibilidad, rendimiento y publicación que deben ejecutarse y registrarse. |
| Tipos compartidos  | **Metadata declarada, uso no verificado.** `packages/shared/package.json` declara `@repo/shared-types`, con `index.ts` como `main` y `types`; no declara scripts ni dependencias. No demuestra compilación ni consumo del paquete.                           |
| Resto del monorepo | **No verificado/configuración no encontrada en las fuentes revisadas.** No se encontró configuración que acredite backend, base de datos, colas, framework de frontend, framework o proveedor de IA, autenticación, CI o infraestructura de despliegue.      |

Las versiones de Tailwind se reproducen exactamente como aparecen en `uis/website/package.json`. El README menciona `package-lock.json`, pero no se verificó su contenido; por tanto, no se afirma qué versiones quedaron resueltas o instaladas.

## 3. Arquitectura y decisiones respaldadas

### Configurado o documentado

- El repositorio separa sus áreas en carpetas. Los README de raíz describen `uis/` para interfaces, `services/` para lógica backend, `data/` para datos y pipelines, `agents/` y `skills/` para capacidades de IA, `workflows/` para orquestación, `packages/` y `shared/` para reutilización, e `infra/`, `scripts/` e `internal/` para operaciones y herramientas. Esta organización está documentada; no demuestra que todos esos componentes estén implementados.
- `uis/website/` es el sitio público del Hito 1. Su README lo describe como estático, con landing y formulario; el envío se simula en el navegador y no transmite ni almacena información. También documenta el build de estilos con Tailwind CLI.
- El README raíz indica que no hay runner de workspace configurado y que los comandos del sitio deben ejecutarse desde su propia carpeta.

### Recomendaciones, no decisiones implementadas

- El README raíz recomienda una API FastAPI centralizada y evitar separar prematuramente el backend en microservicios.
- Los README describen la posible organización de backoffice, servicios, agentes y skills, pero no aportan configuración que pruebe que esas aplicaciones o sistemas estén desplegados.
- Docker Compose y n8n aparecen como opciones o ejemplos en la guía del monorepo; no se encontró configuración que pruebe su uso en este proyecto.

Hay una discrepancia documental: el README raíz describe una plantilla sin aplicaciones ejecutables, mientras que `uis/website/README.md` y `uis/website/package.json` documentan el sitio y su build npm. El README raíz también menciona `docker-compose.yml`, que no se encontró entre las configuraciones revisadas. Este documento registra la diferencia sin resolverla por inferencia.

## 4. Organización de las áreas

| Ruta              | Estado documentado                                                                                                                                                                                                  |
| ----------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `uis/website/`    | Sitio público de Nexova para el Hito 1. El README documenta HTML, validación en navegador, formulario de envío simulado y build CSS con Tailwind. No es un backend ni un sistema de almacenamiento de candidaturas. |
| `uis/backoffice/` | La guía de `uis/` lo propone como lugar para aplicaciones internas; no se encontró esa carpeta en la revisión. No hay aplicación de backoffice verificada.                                                          |
| `services/`       | La guía lo reserva para APIs y workers; no se encontró un servicio concreto ni configuración de backend. FastAPI es una recomendación del README raíz, no un stack configurado.                                     |
| `agents/`         | La guía propone una carpeta y documentación por agente. Existe una plantilla en `agents/_template/`; su presencia no acredita un agente de Nexova en ejecución ni un framework de agentes.                          |
| `skills/`         | La guía define capacidades reutilizables para agentes. El repositorio incluye carpetas como `code-review/`, `data-analysis/` y `research/`; no se verificaron aquí sus dependencias o ejecución como servicios.     |

El README raíz describe además carpetas para datos, MCPs, workflows, paquetes, infraestructura, scripts y documentación. Se consideran estructura y guía del monorepo, no evidencia de sistemas productivos.

## 5. Contexto y restricciones técnicas de Nexova

`BRIEFING.md` describe el entorno empresarial actual como un conjunto de herramientas poco conectadas: HubSpot, Zendesk legacy, Google Workspace, un ATS propio de principios de los años 2010 y hojas de cálculo. También describe despliegues manuales y ausencia de telemetría y logging centralizado. Estas son características del contexto empresarial, no dependencias declaradas por este repositorio.

El briefing plantea como necesidades futuras integración de datos, monitorización, logging y alertas. Para las áreas seleccionadas en `memory-bank/projectbrief.md` —Marketing y Comunicación y Operaciones de Selección— también plantea retos relacionados con contenido y métricas de marketing, cribado de CV, seguimiento de candidaturas y matching. No especifica arquitectura, proveedor, producto, protocolo ni tecnología para resolverlos.

Restricciones verificables para el estado actual:

- El formulario de la web del Hito 1 está documentado como simulación estática: no debe tratarse como recepción real ni almacenamiento de datos de candidatos.
- La guía indica ejecutar los comandos npm desde `uis/website/`; no documenta un comando global de monorepo.
- `npm test` no ejecuta pruebas automatizadas reales.
- No se debe asumir interoperabilidad con las herramientas empresariales de Nexova: no hay integraciones configuradas en las fuentes consultadas.
- Las necesidades de RAG, scoring de CV y agentes descritas por el briefing no acreditan tecnología ni despliegue. `projectbrief.md` presenta la supervisión humana como parte de la propuesta del proyecto, no como una configuración técnica ya implementada.

## 6. Tecnologías y decisiones pendientes

Las siguientes tecnologías no deben presentarse como implementadas sin nueva evidencia:

- **FastAPI, Docker/Compose y n8n:** recomendaciones o ejemplos documentales; no se encontró configuración correspondiente.
- **RAG, bases de datos vectoriales o relacionales, y pipelines de datos:** necesidades o posibilidades del proyecto; implementación no verificada.
- **Proveedores, modelos o frameworks de LLM/agentes:** no especificados en las fuentes revisadas.
- **Backoffice, API, workers, colas, autenticación e integraciones con HubSpot, Zendesk o ATS:** no verificados como implementados.
- **Nube, despliegue, CI, monitorización y logging del propio software:** no hay configuración suficiente para determinar su estado.
- **Política técnica de privacidad, permisos, retención y seguridad de datos:** pendiente de definición para cualquier sistema futuro que procese datos de candidatos o empleados.
- **Pruebas automatizadas y criterios cuantitativos de aceptación:** no establecidos para el conjunto del monorepo; el README web pide realizar comprobaciones, y su script `test` es solo un placeholder.

La elección de estas tecnologías y sus criterios de integración, seguridad, evaluación y operación requiere decisiones posteriores respaldadas por requisitos y configuración concretos.

## 7. Fuentes y verificación

- `BRIEFING.md`: herramientas y limitaciones empresariales de Nexova, además de necesidades futuras de IA y automatización.
- `memory-bank/projectbrief.md`: áreas elegidas por el proyecto y distinción entre contexto oficial y propuestas.
- `README.md` y `README.es.md`: guía del monorepo y organización recomendada.
- `uis/README.md` y `uis/README.es.md`: organización prevista de las interfaces y estado recomendado de `website` y `backoffice`.
- `uis/website/README.md` y `uis/website/package.json`: alcance documentado del sitio, comandos, dependencias declaradas y estado de pruebas.
- `services/README.md` y `services/README.es.md`: propósito y organización prevista de servicios.
- `agents/README.md`, `agents/README.es.md` y `agents/_template/README.md`: organización de agentes y función de la plantilla.
- `skills/README.md` y `skills/README.es.md`: propósito de las skills.
- `packages/shared/package.json`: metadata del paquete de tipos compartidos.

Para verificar este documento, comprobar que cada tecnología tenga una fuente concreta, que las versiones coincidan con el manifiesto, y que las recomendaciones y necesidades empresariales estén etiquetadas como tales. Las ausencias se expresan como “no se encontró en las fuentes revisadas”, no como inexistencia absoluta. La revisión de este Markdown no acredita que el sitio, sus pruebas, integraciones o despliegues hayan sido ejecutados o validados.
