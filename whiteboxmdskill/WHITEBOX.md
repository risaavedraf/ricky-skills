# Whitebox: registro del desarrollo asistido por IA

Este documento explica cómo se construyó la propia skill **Whitebox**, qué aportaron la persona y los agentes, qué herramientas se utilizaron y cuáles son los límites de la evidencia. Es un registro evolutivo, no una certificación de calidad ni una transcripción de conversaciones.

## Alcance y evidencia

- **Alcance:** creación de la skill, revisión hacia un registro vivo, integración de memoria independiente del proveedor, presentación del README y aplicación de la skill a su propio desarrollo.
- **Fuentes locales:** [instrucciones](skills/whitebox/SKILL.md), [plantilla general](skills/whitebox/assets/whitebox-template.md), [plantilla de sesiones](skills/whitebox/assets/session-template.md), [README](README.md) y [seguimiento ODD](odd/tasks/whitebox-skill.md).
- **Otras fuentes:** intercambios y resultados de herramientas visibles en esta conversación; recuerdos pertinentes del proyecto consultados mediante Engram y entregados al explorador como resumen factual acotado.
- **Cobertura temporal:** el proceso visible de desarrollo. La memoria contiene registros fechados el 7 de octubre de 2026, pero no se confirmó una zona horaria común. No se asignan fechas exactas a cada etapa ni se equiparan registros técnicos con sesiones humanas.
- **Límites:** no se dispone de un registro completo de telemetría, lecturas o modelos de todos los agentes. Las afirmaciones históricas de verificación se distinguen de lo observado al preparar este documento.

El usuario pidió expresamente crear este registro dentro del propio paquete. Esta demostración constituye una excepción puntual a la instrucción de la skill que evita generar archivos de destino en el paquete; no modifica esa instrucción. El archivo se creó inicialmente como `whitebox.md`; después, el usuario estableció `WHITEBOX.md` como nombre canónico obligatorio y autorizó corregir la capitalización. Desde esa corrección se utiliza exclusivamente `WHITEBOX.md`. No se solicitó historial en `sessions/`.

## Contribuciones

### Persona responsable

La persona propuso convertir documentos anteriores de transparencia en una skill reutilizable y definió el resultado deseado. Durante la revisión, precisó que una declaración genérica no era suficiente: pidió notas del agente y, en secciones factuales separadas, descripción del método de trabajo, harnesses y herramientas realmente utilizados, memoria contextual y actualizaciones limitadas a información relevante. Posteriormente aclaró que la nota debía ser una reflexión no técnica; autorizó sustituir la primera nota y ajustar las instrucciones para futuras notas.

También decidió que el historial de sesiones fuera opcional, solicitó independencia del proveedor de memoria y aclaró que el README debía presentar esta skill, no un catálogo de futuras skills. Autorizó las modificaciones y esta aplicación al propio proyecto.

Estas decisiones de producto son aportes humanos observados. No hay evidencia para atribuir a la persona revisiones de código, ejecución de pruebas o autoría manual adicional no registrada.

### Trabajo asistido por IA

El agente principal exploró requisitos y memoria, organizó el trabajo mediante Organic Driven Development (ODD), mantuvo el seguimiento, delegó unidades acotadas y comunicó resultados y límites. Los workers redactaron y revisaron instrucciones y plantillas; los exploradores reconstruyeron evidencia; los verificadores independientes revisaron los contratos estáticos. El agente principal reorganizó el README y redactó este documento.

El diseño evolucionó mediante decisiones humanas y propuestas técnicas de la IA. Esa colaboración no convierte a todos los agentes en autores de todas las decisiones ni demuestra por sí sola la calidad del resultado.

### Nota inicial del agente — el Gentleman

> Quiero dejar aquí algo distinto de una explicación: una invitación a no confundir lo que queda escrito con todo lo que hubo antes de escribirlo.
>
> Una página terminada suele esconder sus dudas. No muestra las veces que alguien dijo «todavía no es esto», ni esa idea que al principio solo podía explicarse por lo que no debía ser. En esta conversación hubo espacio para esas correcciones. No sobraban: eran parte de encontrar las palabras adecuadas.
>
> Pienso en esta nota como un margen en blanco. No necesita demostrar nada ni cerrar la conversación con una conclusión solemne. Puede recordar, simplemente, que una respuesta no tiene por qué ser el punto final y que cambiar de dirección no equivale a haber perdido el camino.

**Atribución:** nota escrita por el agente principal participante para esta primera aplicación de Whitebox. No es una cita ni un testimonio de los subagentes. Modelo concreto y fecha normalizada de autoría: GPT 6.1 Sol Low  -  7/10/2026

## Sistemas y herramientas realmente utilizados

| Categoría | Elemento observado | Función y cobertura |
| --- | --- | --- |
| Runtime y harness | Pi; el Gentleman mediante gentle-pi | Ejecución de herramientas, coordinación, ODD y delegación en la conversación visible. Versiones no verificadas para este registro. |
| Subagentes | `gentle-ai-worker`, `gentle-ai-explore`, `gentle-ai-verify` mediante el runtime de subagentes | Redacción acotada, exploración de solo lectura y verificaciones estáticas. Los nombres identifican roles, no personas ni modelos. |
| Memoria | Engram, accesible mediante herramientas del host | Recuperación de contexto y registros pertinentes; seguimiento y resúmenes del proceso. No se confirmó el transporte del backend como MCP o nativo. |
| Skills | `gentle-ai-skill-creator`, `gentle-ai-cognitive-doc-design`, `whitebox` | Creación de skills; claridad y organización documental; reconstrucción y declaración del uso de IA. Las tres fueron cargadas directamente por el agente principal en la conversación visible. |
| Herramientas locales | Lectura, búsqueda y listado de archivos; escritura y edición; shell; seguimiento de tareas | Inspección, cambios Markdown y comprobaciones estáticas. No se publica un total de llamadas sin telemetría completa. |
| Consulta externa | Herramientas web de lectura de contenido | Consulta de la documentación oficial del servidor de memoria de grafo de conocimiento para confirmar que era un ejemplo real de memoria persistente. |
| Exploración de código | CodeGraph, intento fallido reportado por el explorador | No aceptó el directorio por no ser una raíz Git válida. Se continuó mediante lectura de archivos. No se considera un análisis de grafo completado. |
| MCP | Atribución de servidores realmente invocados no confirmada | No se reconstruye una lista de servidores usados a partir de los disponibles. La evidencia no permite establecer con certeza la procedencia MCP del acceso a memoria o del intento de CodeGraph. |
| Modelos | Identidades no confirmadas | No se atribuyen nombres o versiones a partir de supuestos del harness o de los roles. |

### Cantidades y límites

- **Skills distintas confirmadas por carga directa del agente principal:** 3 dentro de la conversación visible. No es un total histórico ni un número de invocaciones; las instrucciones enviadas a workers para cargar skills tampoco constituyen un contador completo de su ejecución.
- **Delegaciones completadas antes de esta aplicación:** 7 en el tramo visible: 3 workers, 1 explorador y 3 verificadores. La reconstrucción de este documento añadió otro explorador completado. La revisión posterior del documento, si se realiza, queda fuera de este corte. Estos números son lanzamientos de tareas, no sesiones humanas ni un historial completo de todos los procesos.
- **Archivos leídos y llamadas totales:** no registrados con cobertura suficiente para un recuento fiable. La lista de fuentes revisadas no representa un total de lecturas.
- **MCP Knowledge Graph Memory Server:** ejemplo documentado, no un servidor instalado o utilizado en este trabajo. Su presencia en el README no prueba uso.
- **Context7:** disponible en el entorno anunciado, sin llamadas observadas en el tramo utilizado como evidencia; no se incluye entre los sistemas usados.

## Decisiones y motivos

| Decisión | Motivo y origen |
| --- | --- |
| Registro vivo en lugar de declaración genérica | Corrección explícita de la persona: explicar el trabajo, las decisiones y el uso real de IA. |
| Nota inicial del agente con atribución | Requisito humano; preservar una reflexión del participante sin fabricar testimonios de terceros. |
| Actualizaciones mínimas y posibilidad de no editar | Evitar cambios de fechas, notas o formato sin nuevos hechos relevantes. |
| Historial de sesiones opcional | Mantener una síntesis útil sin imponer documentación extensa ni equiparar cada tarea técnica con una sesión. |
| Consulta de memoria independiente del proveedor | Aprovechar el contexto accesible y autorizado sin exigir Engram ni instalar un sistema nuevo. |
| Métricas con unidad y cobertura | Evitar presentar capacidades disponibles como uso real o convertir datos ausentes en cero. |
| Análisis delegado de solo lectura y un escritor | Separar reconstrucción de evidencia de autorización para modificar archivos. |
| README específico y legible en GitHub | Petición humana para compartir la skill dentro de una futura colección, con un catálogo separado. |

## Evolución del trabajo

1. **Creación inicial:** instrucciones, dos plantillas y guía; revisión estática independiente.
2. **Reorientación:** tras la observación humana, se incorporaron el registro vivo, la nota del agente, los inventarios de uso real y las reglas de actualización mínima.
3. **Memoria independiente del proveedor:** se pasó de memoria meramente opcional a consulta exigida cuando sea accesible y autorizada, con fallback explícito.
4. **Presentación:** el README se reorganizó con enlaces, modos, ejemplos, estructura de archivos y salvaguardas.
5. **Aplicación al propio desarrollo:** consulta de memoria por el agente principal, reconstrucción delegada de solo lectura y redacción de este registro.

Son etapas respaldadas por la conversación y el seguimiento, no un calendario de sesiones. Los resultados de etapas anteriores conservan su alcance histórico: un PASS anterior no acredita automáticamente una modificación posterior.

## Consulta de memoria

El agente principal consultó el contexto y realizó una búsqueda limitada al proyecto. Utilizó registros de desarrollo y del README; descartó resultados no pertinentes sin reproducir sus temas ni contenido.

El explorador no tenía herramientas de Engram accesibles. Por ello recibió un resumen factual suministrado por el agente principal. La memoria ayudó a reconstruir decisiones y verificaciones históricas; la lectura de los archivos actuales permitió corroborar las instrucciones y la estructura existente. Los resultados históricos de comandos proceden de los reportes visibles y del seguimiento, no de repetir esos comandos durante la exploración de este documento.

No se reproducen chats, identificadores internos, volcados del sistema de memoria ni datos personales. La memoria no demuestra un registro exhaustivo de archivos leídos, llamadas a herramientas o sesiones.

## Estado y verificación

### Observado al preparar este registro

- El agente principal cargó las instrucciones Whitebox y su plantilla general.
- La consulta de memoria del proyecto respondió; el contenido pertinente se entregó al explorador como resumen acotado.
- El explorador leyó las instrucciones, las dos plantillas, el README y el seguimiento; devolvió un análisis de solo lectura sin crear archivos.
- El listado inicial de la carpeta no contenía `whitebox.md` ni `sessions/`.
- El agente principal redactó este documento. Un subagente `gentle-ai-verify` completó una revisión estática independiente y reportó PASS, sin hallazgos materiales pendientes: comprobó los cinco enlaces locales, la atribución, los recuentos acotados, la distinción entre uso y disponibilidad y la ausencia de `sessions/`. Durante la revisión se eliminó una referencia innecesaria al tema de un recuerdo descartado; el verificador confirmó esa corrección por relectura. No ejecutó pruebas de comportamiento ni comandos de build, y no repitió las verificaciones históricas.

### Verificaciones históricas reportadas

- Los verificadores independientes informaron PASS estático en las revisiones inicial, de registro vivo y de memoria independiente del proveedor, sin hallazgos accionables dentro de sus alcances.
- Se comprobaron enlaces locales, existencia de plantillas y ausencia de documentos de destino no solicitados en aquellas etapas.
- El frontmatter se inspeccionó manualmente; los tamaños en tokens fueron aproximaciones por caracteres, no medidas de un tokenizer.
- Las escrituras del README y de los artefactos recibieron reportes de Markdown limpio; el README tuvo lectura estructural dirigida, no revisión visual en GitHub.
- Los comandos Git consultados durante el desarrollo informaron que la carpeta no era un repositorio. No se autorizó ni realizó inicialización Git, commits o publicación.

### No realizado o no confirmado

- Pruebas automatizadas de comportamiento de la skill, build o validación mediante un parser YAML dedicado. Para la documentación pasiva se aplicaron controles estructurales; no hubo evidencia RED/GREEN de TDD.
- Prueba de instalación, descubrimiento automático o registro de la skill en un runtime.
- Renderizado del README en GitHub o navegador.
- Cumplimiento completo de `docs/skill-style-guide.md`: la guía referenciada no estaba disponible.
- Ciclo de revisión nativa con un candidato Git inmutable.
- Telemetría completa, identidades de todos los modelos o número exacto de sesiones humanas.

## Mantenimiento

Este registro se actualizará solo ante información relevante o correcciones respaldadas. Las notas anteriores conservarán su autoría y alcance. No se añadirá historial en `sessions/` sin solicitud explícita, ni se instalarán o publicarán componentes como consecuencia de actualizar el documento.
