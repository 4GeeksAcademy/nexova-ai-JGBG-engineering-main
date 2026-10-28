# Instrucciones del repositorio

## Alcance y estructura

Estas instrucciones aplican al monorepositorio. Antes de trabajar en un área, consulta su README y respeta sus instrucciones específicas. Mantén la estructura existente y limita los cambios al alcance solicitado.

`agents/` contiene agentes del producto y `skills/` contiene capacidades reutilizables; ambas son carpetas del monorepositorio. No son configuración del agente. `.agents/` sería una ubicación distinta para configuración: no la crees ni muevas allí contenido como parte de una tarea en otra carpeta.

No inventes información empresarial ni afirmes que una tecnología, integración o capacidad está implementada si las fuentes del proyecto no lo verifican. Distingue los hechos confirmados de las propuestas. No asumas comandos de validación globales: consulta la documentación del componente y comunica las limitaciones.

## Lectura al inicio de cada sesión

Al inicio de cada sesión, lee estos documentos en este orden:

1. `memory-bank/projectbrief.md`
2. `memory-bank/techContext.md`
3. `memory-bank/progress.md`

Consulta además el README y el contexto pertinentes a la tarea antes de modificar un área.

## Archivos, carpetas y operaciones protegidos

Sin autorización explícita del desarrollador:

- No modifiques `BRIEFING.md` ni ningún archivo de `memory-bank/`.
- No modifiques los documentos de contexto `CONTEXT*.md` ni `company-choice.md`.
- No modifiques aplicaciones existentes, incluida la web bajo `uis/website/`, otras interfaces bajo `uis/` ni servicios bajo `services/`.
- No ejecutes `commit`, `push`, `merge`, `reset` ni cambios de rama.

No elimines archivos, carpetas, ramas ni repositorios. No expongas credenciales, secretos ni datos personales. No incorpores datos reales a ejemplos, fixtures o documentación sin autorización y procedencia verificable. Si detectas datos sensibles, evita divulgarlos y limita su uso a lo estrictamente autorizado.

## Protocolo obligatorio antes de cada commit

Completa estos pasos, en orden, antes de solicitar o ejecutar un commit:

1. Confirma que al inicio de la sesión leíste los tres documentos de `memory-bank/`; relee el contexto relevante si hace falta.
2. Revisa el estado del repositorio y el diff existente. Conserva los cambios preexistentes y no descartes cambios ajenos.
3. Lee el README del área afectada y confirma que cada cambio está dentro del alcance autorizado.
4. Comprueba que no se modificaron archivos protegidos ni se incluyeron secretos, datos personales o datos sin procedencia verificada.
5. Ejecuta la validación focalizada documentada para el componente. Si no existe o no puede ejecutarse, informa esa limitación; no afirmes que una validación pasó si no se ejecutó.
6. Revisa el diff final y el estado del repositorio. Resume los archivos afectados, las validaciones realizadas y las limitaciones.
7. Solicita autorización explícita antes de ejecutar el commit. La autorización para un commit no autoriza `push`, `merge`, `reset` ni cambios de rama.
