# Prompts de la conversación — Correcciones LTI-CVE.md
**IA:** Claude · **Modelo:** Claude Sonnet 4.6 (claude-sonnet-4-6)
**Fecha:** Mayo 2026

---

**Prompt 1**
Adjunto un documento llamado LTI-CV.md que contiene un PRD entregado como resolución de un ejercicio. El profesor hizo la siguiente devolución:

REVISIÓN DETALLADA: LTI-CV — Diseño del sistema ATS
📊 SCORING GRANULAR DE PROMPTS
#	Criterio	Score	Justificación y evidencia
1	Claridad de Tarea	8/10	El Prompt 1 está bien estructurado con tarea numerada (6 sub-preguntas). Los Prompts 6-11 son comandos directos pero claros. Pierde puntos en Prompt 10 (lista de diagramas sin especificar sintaxis Mermaid concreta).
2	Completitud de Contexto	7/10	El Prompt 1 fija contexto sólido (Senior PM en ATS, análisis estratégico) y se hereda en la conversación. Pero los prompts posteriores asumen el contexto sin reafirmarlo.
3	Técnica de Prompting	7/10	Role-Based correctamente usado en P1 ("Actúa como Senior Product Manager especializado en ATS"). Chain-of-Thought implícito en las 6 sub-preguntas del P1 (funcionalidades → usuarios → flujo → competidores → dolores → diferenciadores). Falta: Few-Shot, Output Format explícito, validación.
4	Prompt no vacío	9/10	4KB sustanciales, 12 prompts sin placeholders. Trabajo iterativo visible.
5	Especificidad Técnica	5/10	Muy poca: "diagrama mmd" (P10) sin tipo de Mermaid, "diagrama C4 a uno de los componentes" sin restricciones. No menciona stack, tipos de datos, librerías.
6	Coherencia Prompt→Output	8/10	El output (LTI-CVE.md, muy extenso) sí cubre lo pedido, especialmente tras el Prompt 11 que reorganiza el documento limitándolo a fase de diseño. El módulo de Notificaciones como C4 deep dive es coherente con P10.
7	Ausencia Ambigüedad	7/10	Términos mayormente claros. "Diagrama de arquitectura" (P9) es genérico — no especifica si REST, microservicios, monolito, etc. El P11 cierra esa ambigüedad listando explícitamente qué debe estar dentro/fuera del scope.
8	Validabilidad	6/10	El P11 es lo más cercano a validación: lista de "debe incluir" y "queda fuera del alcance". Pero no hay criterios binarios verificables tipo "Mermaid renderiza en GitHub" o "100% nombres consistentes".
9	Originalidad	7/10	Trabajo iterativo real con buen flow (análisis estratégico → MVP → arquitectura → reorganización → prompts.md final). La técnica de scope shaping en el Prompt 11 (lista explícita de "queda fuera del alcance") es buena práctica raramente vista.
TOTAL: 64/90 (71%) — 🟡 Cerca del threshold (75/90)

🔍 ANÁLISIS DETALLADO POR CRITERIO
Criterio 3: Técnica de Prompting → 7/10
Tu Prompt 1 muestra CoT implícito bien aplicado: las 6 sub-preguntas guían a Claude a través de un razonamiento estratégico (funcionalidades → usuarios → flujo → competidores → dolores → diferenciadores). Esto produce un análisis estructurado.

Sin embargo, los Prompts 6-10 son comandos directos sin role ni constraints. Esto funciona en una sesión LIVE de Claude que mantiene contexto, pero no es reproducible.

Fix recomendado para el Prompt 8:

ANTES:
"Luego de la sección 'Casos de Uso Principales del MVP' agrega
una sección que defina el modelo de datos que cubra entidades,
atributos (nombre y tipo) y relaciones de los 3 casos de uso
principales."

DESPUÉS:
"Actúa como arquitecto de datos senior. Sobre los 3 CU
definidos, deriva el modelo de datos siguiendo:
1. Identifica entidades de dominio
2. Atributos con nombre + tipo (uuid, varchar, int, jsonb, etc.)
3. Relaciones con cardinalidad explícita (1:N, N:M)
4. Diagrama Mermaid `erDiagram` (no usar PlantUML)
5. Tenant isolation: añadir company_id donde aplique
Valida que los nombres de entidades sean idénticos a los del CU."
Criterio 9: Originalidad → 7/10 ⭐ Destacable
El scope shaping del Prompt 11 es excelente:

"Queda fuera del alcance de este documento: MVP y Hoja de Ruta, Riesgos, Go-to-Market, Pricing, KPIs..."

Esto es una técnica anti-scope-creep que pocos aplican. Lista explícitamente lo que NO debe estar — más útil que solo decir lo que SÍ debe estar.

🏗️ ANÁLISIS DEL DOCUMENTO LTI-CVE.md
Arquitectura y completitud — 8/10

Documento muy extenso (verificado por CodeRabbit ~1500+ líneas) con análisis de mercado robusto, 3 CU, modelo de datos, arquitectura, C4 con deep dive en módulo de Notificaciones.

Modelo de datos — 7/10

CodeRabbit señaló dos problemas legítimos:

Falta uniqueness constraint en Application para el par (candidate_id, job_id) — esto permite que un mismo candidato aplique dos veces a la misma oferta.
Sin tenant identifier (organization_id) — el documento dice "middleware aplica organization_id automáticamente" pero la entidad no lo refleja como FK. Para multi-tenant esto es crítico.
Módulo de Notificaciones (C4 deep dive) — 8/10

Buena elección de componente. La estructura está bien.

Análisis de mercado — 9/10

Las métricas citadas ($3.1B, 8.1% CAGR, 97.8% Fortune 500) son buenas, pero CodeRabbit señaló acertadamente que faltan fuentes. Para un PRD esto pesa — sin citas el lector no puede verificar.

Magic link sin one-time use — 7/10

CodeRabbit identificó que el modelo de User incluye magic_link_token + magic_link_expires_at pero NO un magic_link_used_at o is_magic_link_used. Esto permite reutilización del mismo link y es un vector de ataque.

🔗 COHERENCIA EJERCICIO vs ENTREGA
Requerimiento	Status	Notas
Descripción + valor + ventajas	✅	Sólido análisis estratégico
Funciones principales	✅	Cubierto
Lean Canvas	✅	Con Mermaid
3 casos de uso + diagrama	✅	Aplicación, Evaluación, Coordinación
Modelo de datos	⚠️	Falta tenant + uniqueness en Application
Diseño alto nivel + diagrama	✅	Justificado
C4 con deep dive	✅	Módulo de Notificaciones
LTI-iniciales.md + prompts.md	✅	Estructura correcta (LTI-CV/)
Alignment: 88%

📊 SCORING GLOBAL FINAL
Categoría	Score	Max
Calidad de Prompts (64/90 normalizado)	21	30
Calidad del documento	32	40
Coherencia Prompt-Documento	16	20
Documentación / Cumplimiento estructural	9	10
Base	78	100
Bonus:

+3 🌟 Scope shaping explícito en Prompt 11
+2 🌟 Análisis de mercado con datos cuantitativos
Penalizaciones:

−3 ❌ Faltan tenant isolation + uniqueness constraint en modelo de datos
−2 ❌ Magic link sin one-time use enforcement
SCORE FINAL: 78/100 — ⭐⭐⭐⭐ (Buen trabajo, con mejoras claras)

💬 RECOMENDACIONES
Prioritarias
Añadir organization_id a entidades tenant-scoped — Candidate, Application, Interview, etc. + crear entidad Organization. Sin esto, el middleware del que hablas no tiene FK contra la cual escribir. Habilita Row-Level Security en Postgres.
Uniqueness constraint en Application — UNIQUE(candidate_id, job_id) previene duplicados.
Magic link one-time use — añadir magic_link_used_at o is_magic_link_used y validar en el flujo de consumo.
Secundarias (calidad)
Citar fuentes de métricas de mercado — las cifras ($3.1B, CAGR 8.1%) merecen footnotes con fuente (Gartner, G2, etc.). Sin esto pierde credibilidad.
Reflexión metodológica
Tu Prompt 11 de scope shaping es una buena práctica. Considera generalizarlo: al iniciar un design doc, definir explícitamente qué queda fuera. Reduce iteraciones y mantiene el doc focused.

Para reproducibilidad, considera fijar role + constraints en cada prompt aislado, no solo en el primero. Los Prompts 6-10 son tu eslabón débil.

Salida esperada:
Hacé una revisión detallada del documento para detectar los puntos a corregir. 
Listá y explicá los cambios propuestos para corregir LTI-CVE.md.

Restricciones:
No agregues funcionalidad nueva ni cambies el alcance.
No hagas modificaciones hasta que yo las autorice.

---

**Prompt 2**
Antes de aplicar los cambios al documento, adjunto la respuesta que obtuve de ChatGPT para la misma consulta.
Quiero que compares la respuesta de ChatGPT con la tuya y generes una propuesta de cambios consolidada que combine lo mejor de ambas revisiones, priorizando:
* Alineación con la devolución del profesor.
* Consistencia funcional y técnica.
* Coherencia de la documentación.

Sé crítico, evalúa cada recomendación y genera:
1. Una lista numerada de todos los cambios que recomiendas aplicar.
2. Explica brevemente el motivo de cada cambio y qué criterio usaste para seleccionarla.

No modifiques el archivo .md hasta que tengas mi aprobación.

---

**Prompt 3**
El punto "Mejorar Prompts" no lo vamos a aplicar ahora porque está en un documento independiente. Aplicá las correcciones en el documento.

---

**Prompt 4**
Actúa como un senior product manager con experiencia en productos SaaS B2B. Verifica que el PRD sea consistente en todo su contenido y que los diagramas sean coherentes y actualizados según la definición. Verifica si el PRD puede utilizarse como input para agentes de coding. Salida esperada: puntos a reforzar a corregir/mejorar. Restricciones: no incorporar nuevas funcionalidades.

---

**Prompt 5**
Genera un archivo prompt-correcciones.md que incluya todos los chats intercambiados en esta conversación e indique la IA y modelo utilizados.

---

*Prompts registrados de la sesión con Claude Sonnet 4.6 · Mayo 2026*
