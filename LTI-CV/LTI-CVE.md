# Diseño Preliminar — Plataforma ATS de Nueva Generación
**Senior Product Manager Report · Mayo 2026**

> **North Star:** "El ATS que hace que contratar sea tan fluido para el equipo interno como hacer un pedido online, y tan transparente para el candidato como rastrear un envío."

---

## 1. Descripción del Software

Esta plataforma es un **Applicant Tracking System (ATS) de nueva generación** diseñada para empresas de 50 a 5.000 empleados que necesitan contratar mejor, más rápido y con menos fricción interna. A diferencia de los sistemas tradicionales —concebidos como bases de datos de candidatos con flujos de aprobación— esta plataforma está construida desde cero con tres principios irrenunciables: la experiencia del candidato como ventaja competitiva, la adopción del hiring manager como condición de diseño, y la inteligencia artificial como motor de ejecución real (no como feature de marketing).

La plataforma cubre el ciclo completo de adquisición de talento: desde la creación de la vacante y la publicación multicanal, hasta la coordinación de entrevistas, la toma de decisión colaborativa, la generación de la oferta y el traspaso al HRIS corporativo. Todo ello en una interfaz que el recruiter usa a diario con fluidez, que el hiring manager puede operar desde el móvil en 30 segundos, y que el candidato experimenta como el proceso de selección más transparente y respetuoso que ha vivido.

**Contexto de mercado:**

| Métrica | Valor |
|---|---|
| Mercado global ATS 2025 | $3.1B |
| CAGR proyectado 2026–2034 | 8.1% |
| Fortune 500 que usa un ATS | 97.8% |
| Recruiters frustrados con su ATS actual | 68% |

---

## 2. Análisis de los 3 ATS Más Relevantes del Mercado

### 2.1 Greenhouse
**Segmento:** Mid-market y enterprise · **Rating G2 2026:** 4.4/5 · **+7.500 empresas clientes**

| Dimensión | Puntuación |
|---|---|
| UX / Usabilidad | 88/100 |
| Structured hiring | 92/100 |
| Integraciones | 80/100 |
| Analytics | 70/100 |
| Precio-valor | 60/100 |

**Fortalezas:** Mejor UX del mercado enterprise con interfaz intuitiva y bien diseñada. Structured hiring nativo con scorecards predefinidos. Marketplace de +500 integraciones. Greenhouse AI lanzado en septiembre 2025 con resumen automático de candidatos.

**Limitaciones críticas:** Precio elevado y proceso de ventas opaco sin precios públicos. Reporting básico sin personalización avanzada. Sincronización HRIS parcial: transfiere solo campos básicos (no compensación ni códigos de posición). Implementación compleja que requiere consultores externos.

---

### 2.2 iCIMS Talent Cloud
**Segmento:** Enterprise · **Rating G2:** 4.2/5 · **~4.000 empresas clientes** · Adquirió Apli en 2025

| Dimensión | Puntuación |
|---|---|
| UX / Usabilidad | 65/100 |
| Structured hiring | 78/100 |
| Integraciones | 95/100 |
| Analytics | 75/100 |
| Precio-valor | 50/100 |

**Fortalezas:** ~800 integraciones disponibles — el ecosistema más grande del mercado ATS. Automatización de workflows avanzada con motor de reglas configurable. API robusta y bien documentada. Conectores enterprise nativos con Workday, ADP, SAP, UKG y Oracle HCM.

**Limitaciones críticas:** Implementación lenta y extremadamente compleja: 6–18 meses promedio. UX anticuada con curva de aprendizaje alta. Soporte al cliente inconsistente. Modelo de pricing exclusivamente enterprise — inaccesible para PYMEs.

---

### 2.3 Workday Recruiting
**Segmento:** Enterprise HCM suite · **Rating G2:** 4.0/5 · **+10.000 empresas Workday** · Absorbió Paradox en 2025

| Dimensión | Puntuación |
|---|---|
| UX / Usabilidad | 60/100 |
| Structured hiring | 70/100 |
| Integraciones | 85/100 |
| Analytics | 90/100 |
| Precio-valor | 45/100 |

**Fortalezas:** Suite HCM unificada con HRIS nativo — eliminación total de silos de datos. Analytics y reporting avanzado con People Analytics integrado. IA conversacional vía adquisición de Paradox en 2025. Movilidad interna nativa.

**Limitaciones críticas:** UX rígida y frustrante para recruiters de uso diario. Implementación de 6 a 18 meses con equipos de consultoría especializados. Costo total de propiedad muy elevado. Parsing de CVs deficiente que obliga a candidatos a rellenar campos manualmente.

---

### 2.4 Dolores Identificados — Ordenados por Impacto de Negocio

**#1 — Pérdida de candidatos cualificados por UX deficiente** ░░ Impacto: 96%
El 60% de candidatos abandona aplicaciones que consideran largas o complejas. El 69% abandona cuando el ATS falla al parsear su CV. Los mejores perfiles no toleran fricciones técnicas.
*Impacto: Directo en revenue · Daño al employer brand · Posiciones vacías más tiempo*

**#2 — Baja adopción de hiring managers → feedback tardío** ░░ Impacto: 90%
Los HMs encuentran el sistema complejo y lo evitan. El pipeline se paraliza, los candidatos esperan semanas sin respuesta y terminan aceptando otras ofertas.
*Impacto: Alarga time-to-hire 5–15 días · Candidatos perdidos · Frustra al equipo de recruiting*

**#3 — Comunicación deficiente con candidatos** ░░ Impacto: 85%
El 52% cita la falta de comunicación como su mayor frustración. Solo el 10% cree que sus aplicaciones son revisadas por alguien real. Los rechazos llegan tarde o nunca.
*Impacto: Destrucción del employer brand · Candidatos que ghostean a la empresa*

**#4 — Integración HRIS incompleta y sincronización parcial** ░░ Impacto: 78%
Incluso los ATS líderes sincronizan solo campos básicos. Esto obliga a trabajo manual post-contratación de 3–5 horas por hire, duplica errores y consume tiempo de RRHH.
*Impacto: Ineficiencia operacional · Datos inconsistentes · Riesgo de compliance*

**#5 — Reporting limitado y dashboards no accionables** ░░ Impacto: 72%
Los paneles estándar son superficiales. Cualquier métrica personalizada requiere exportar a Excel. Los líderes de TA no pueden demostrar ROI ni identificar cuellos de botella.
*Impacto: Decisiones sin datos · TA no puede influir estratégicamente en el negocio*

**#6 — Pricing opaco que penaliza el crecimiento** ░░ Impacto: 65%
Los ATS líderes han migrado funcionalidades incluidas a tiers de pago o add-ons. Las empresas en crecimiento ven saltar su factura sin cambios en el producto.
*Impacto: Impacto presupuestario directo · Fricción en renovaciones anuales*

**#7 — Workflows rígidos que no se adaptan a procesos únicos** ░░ Impacto: 55%
Las organizaciones deben doblar sus procesos reales para encajar en la estructura del ATS. Genera burocracia interna y bajas tasas de adopción.

**#8 — Burnout de equipos de TA por falta de automatización real** ░░ Impacto: 45%
El 27% de equipos de TA reporta burnout. Los ATS actuales automatizan superficialmente pero dejan sin resolver la coordinación de entrevistas, seguimiento y actualización de estados.

---

## 3. Diferenciadores para un ATS Superior

### 3.1 Valor Añadido

El valor central que entrega la plataforma se articula en cuatro ejes:

**Reducción del time-to-hire.** Al eliminar el cuello de botella de la adopción de hiring managers y automatizar la coordinación de entrevistas, las empresas que adoptan la plataforma reducen su tiempo promedio de contratación en un 30% desde el primer mes. Cada día que una posición clave permanece vacante tiene un costo directo en productividad y oportunidad.

**Employer brand como activo estratégico.** El 52% de los candidatos cita la comunicación deficiente como su mayor frustración con los procesos de selección actuales. Esta plataforma convierte cada interacción con un candidato —incluyendo los rechazos— en una experiencia positiva y recordada. Los candidatos que viven un proceso transparente recomiendan la empresa aunque no consigan el trabajo, generando un ciclo de atracción de talento orgánico y sostenible.

**TA como función estratégica, no administrativa.** Los equipos de Talent Acquisition que usan esta plataforma acceden a analíticas accionables en tiempo real: coste por contratación, ROI del proceso, conversión por etapa y benchmarks contra la industria. Esto les permite demostrar su impacto al negocio con datos concretos y tomar decisiones informadas sobre dónde invertir sus recursos.

**Automatización que libera tiempo de alto valor.** El copiloto de IA reduce el 40% de las tareas administrativas repetitivas del recruiter: coordinación de agendas, redacción de comunicaciones, actualización de estados y seguimiento de candidatos pasivos. El equipo de TA dedica su tiempo a lo que realmente importa: identificar talento, construir relaciones y tomar mejores decisiones de contratación.

### 3.2 Ventajas Competitivas

**Ventajas de producto — lo que el usuario experimenta desde el día 1:**
- Aplicación del candidato en menos de 4 minutos con autocompletado y tracking en tiempo real
- HM Inbox móvil con decisión posible en 30 segundos vía magic link, sin login al sistema
- Workflows 100% configurables sin código: el ATS se adapta a la empresa, no al revés
- Integración HRIS bidireccional profunda (todos los campos, no solo nombre y cargo)

**Ventajas de modelo — lo que diferencia la propuesta de negocio:**
- Pricing transparente y público, sin add-ons ni penalización al crecimiento
- Usuarios internos ilimitados en todos los tiers, eliminando la barrera de adopción por seat
- Prueba gratuita de 30 días sin tarjeta: la experiencia del producto es el argumento de venta

**Ventajas de plataforma — las defensas estructurales que se refuerzan con el tiempo:**
- Efecto de datos: cada contratación registrada entrena los modelos de IA, haciendo las recomendaciones más precisas con el uso
- Efecto de red de employer brand: el ranking público de empresas con mejor experiencia de candidato genera presión competitiva positiva entre clientes
- Volante de crecimiento: candidatos satisfechos → recruiters que renuevan → referidos de pares → nuevos clientes, sin depender de publicidad pagada

### 3.3 Los 7 Diferenciadores Clave

**Diferenciador 1 — Candidate experience como producto central**
Formulario progresivo con autocompletado desde LinkedIn o CV, sin campos innecesarios. Portal personalizado donde el candidato ve exactamente en qué etapa está y qué sigue. Notificaciones proactivas por WhatsApp y email en cada cambio de estado. El primer ATS donde el candidato recomienda la empresa aunque no consiga el trabajo.
*Ataca: Pain #1 y #3 · NPS candidato objetivo >50*

**Diferenciador 2 — HM Inbox: decisión en 30 segundos desde el móvil**
Vista de bandeja exclusiva: foto, resumen IA de 5 líneas, score de fit, tres botones. Magic link en el email — decisión sin login completo al sistema. El HM nunca necesita formación para contribuir al proceso.
*Ataca: Pain #2 · Adopción HM objetivo >75% · Time-to-hire -30%*

**Diferenciador 3 — IA que ejecuta acciones, no que "sugiere"**
Resumen automático de candidatos con scorecard de fit vs. descripción del puesto. Redacción y envío automático de rechazos, follow-ups y mensajes de oferta personalizados. Detección de candidatos en riesgo de abandono con acción preventiva automática. Transcripción de videoentrevistas con generación de scorecard sintético.
*Ataca: Pain #8 · Elimina el 40% de trabajo administrativo manual*

**Diferenciador 4 — Analytics accionables por rol, sin exportar a Excel**
Dashboards diseñados para cada rol: CEO, VP People, recruiter, CFO. Alertas automáticas cuando un KPI sale del rango esperado del benchmark. ROI de reclutamiento calculado y presentable en tiempo real.
*Ataca: Pain #5 · TA como función estratégica · Valor directo para C-suite*

**Diferenciador 5 — Integración HRIS bidireccional profunda desde el día 1**
Sincronización completa con Workday y BambooHR. Todos los campos relevantes: posición, compensación, entidad legal, código de empleado. Sin trabajo manual post-contratación, sin datos duplicados, sin inconsistencias.
*Ataca: Pain #4 · Elimina 3–5 horas de trabajo manual por contratación*

**Diferenciador 6 — Workflows 100% configurables sin código**
Pipeline visual drag-and-drop, aprobaciones multinivel, campos personalizados por puesto. Triggers automáticos condicionales configurables sin conocimientos técnicos.
*Ataca: Pain #7 · Alta flexibilidad · Sin dependencia de IT*

**Diferenciador 7 — Pricing transparente alineado con el éxito del cliente**
Usuarios internos ilimitados en todos los tiers — cobrar por seat penaliza la adopción de HMs. Tres tiers con precios públicos: Starter ($499/mes), Growth ($1.499/mes), Scale (custom). Prueba gratuita de 30 días sin tarjeta de crédito.
*Ataca: Pain #6 · NRR objetivo >115%*

---

## 4. Usuarios Principales del Sistema

| Usuario | Frecuencia de uso | Necesidad principal |
|---|---|---|
| Recruiter / TA Manager | Diaria — uso intensivo | Pipeline fluido, automatización, métricas de conversión |
| Hiring Manager | Baja — alta resistencia | Simplicidad máxima, decisión rápida sin formación |
| VP de People / TA Director | Semanal — estratégico | Reportes de ROI, métricas para C-suite, visión global |
| Administrador de sistema | Mensual — técnico | Configuración, integraciones, permisos, custom fields |
| Candidato | Puntual — externo | Aplicación rápida, transparencia, comunicación proactiva |
| Agencia de reclutamiento | Frecuente — externo | Acceso controlado, envío de candidatos, tracking de fees |

> **Insight clave:** El hiring manager es el usuario más crítico y más descuidado del mercado. Su baja adopción genera el cuello de botella más costoso de todo el proceso: candidatos esperando feedback durante días mientras el pipeline se paraliza.

---

## 5. Flujo Completo de Reclutamiento

**Tiempo promedio de ciclo: 23–45 días según industria**

1. **Requisición** — Creación y aprobación de la vacante por el hiring manager y HR. Incluye definición de perfil, nivel salarial y código de posición en el HRIS.
2. **Publicación** — Distribución de la oferta a job boards, career site propio y redes sociales desde un panel centralizado.
3. **Aplicación** — El candidato aplica, sube documentos y completa evaluaciones iniciales. El ATS parsea el CV y crea el perfil automáticamente.
4. **Screening** — Filtrado inicial automático por criterios definidos. Preguntas de knockout, evaluación de requisitos mínimos, ranking de candidatos.
5. **Entrevistas** — Secuencia estructurada: phone screen → entrevista técnica → panel. Coordinación automatizada de agendas.
6. **Evaluación** — Completar scorecards, votación de candidatos preferidos, deliberación del equipo y decisión final del hiring manager.
7. **Oferta** — Generación y envío de la carta oferta, negociación, aceptación formal y firma de documentos.
8. **Onboarding** — Traspaso de datos al HRIS, inicio de procesos de incorporación, comunicación de próximos pasos.

**Actividades transversales:** Comunicación continua con candidatos · Analytics en tiempo real · Compliance y GDPR · Colaboración interna · Sincronización HRIS

---

## 6. Funciones Principales

### 6.1 Gestión de Vacantes y Sourcing
- Publicación multicanal en job boards (LinkedIn, Indeed, Glassdoor) desde un panel único
- Distribución automática a portales de empleo locales e internacionales
- Career site propio con employer branding personalizable
- Gestión de referencias internas de empleados
- Portal de agencias externas de reclutamiento con acceso controlado

### 6.2 Gestión del Pipeline de Candidatos
- Parsing automático de CVs y extracción de datos estructurados
- Filtrado y screening inicial por criterios predefinidos
- Pipeline Kanban visual con drag-and-drop entre etapas
- Búsqueda global y filtros avanzados sobre la base de candidatos
- Historial completo de interacciones por candidato

### 6.3 Colaboración y Comunicación
- Scorecards estructurados para evaluación de entrevistas
- Sistema de comentarios y votaciones entre recruiters y hiring managers
- Coordinación automatizada de entrevistas con sincronización de calendarios
- Plantillas de comunicación y secuencias de email automatizadas
- Notificaciones de estado para candidatos en tiempo real

### 6.4 Analytics, Integraciones y Compliance
- Métricas clave: time-to-hire, source of hire, conversión por etapa, costo por contratación
- Integraciones con HRIS (Workday, SAP, BambooHR), assessments y videoentrevista
- Gestión de cumplimiento normativo: GDPR, EEO, OFCCP
- Talent pool y CRM para candidatos pasivos con nurturing automatizado
- Movilidad interna: visibilidad de vacantes para empleados actuales

**Funcionalidades adicionales:** Gestión de oferta y onboarding · Cumplimiento normativo regional · Gestión de agencias externas · Movilidad interna · Gestión de referencias

---

## 7. Lean Canvas — Modelo de Negocio

# Lean Canvas — ATS centrado en experiencia humana

```mermaid
---
config:
  theme: base
  themeVariables:
    fontSize: "11px"
    primaryColor: "#fefce8"
    primaryTextColor: "#1e293b"
    primaryBorderColor: "#94a3b8"
    lineColor: "#94a3b8"
    background: "#ffffff"
---
block-beta
  columns 5

  P["**PROBLEMA**
  60% de candidatos abandona formularios complejos.
  HMs evitan el ATS y el pipeline se traba 5–15 días.
  Sin feedback al candidato se daña la marca empleadora.
  Sync HRIS roto genera 3–5 h de trabajo manual por hire."]:1

  block:COL2:1
    columns 1
    S["**SOLUCIÓN**
    App móvil en menos de 4 min con parser de CV.
    HM Inbox con magic link y decisión en 30 seg.
    Portal candidato con tracking en tiempo real.
    Copiloto IA que ejecuta, no solo sugiere."]:1

    M["**MÉTRICAS CLAVE**
    NPS candidato mayor 50
    Activación HM mayor 75%
    Time-to-hire menos 30%
    NRR mayor 115%
    Churn anual menor 8%"]:1
  end

  U["**PROPUESTA DE VALOR ÚNICA**
  Contratar tan fluido como pedir comida online
  y seguir el proceso tan transparente como rastrear un envío.
  El ATS que pone la experiencia humana
  en el centro del proceso de selección."]:1

  block:COL4:1
    columns 1
    V["**VENTAJA INJUSTA**
    Dataset propietario donde cada hire entrena la IA.
    Efecto de red vía ranking público de employer brand.
    Integraciones exclusivas con HRIS tier-1."]:1

    C["**CANALES**
    Red de founders y design partners en M0–M6.
    SEO sobre HR tech.
    Thought leadership en LinkedIn 3× por semana.
    Comunidades de TA y HR."]:1
  end

  G["**SEGMENTOS**
  _Primario_
  Tech cos. 50–500 emp., 20–80 hires/año.
  Usuarios de Greenhouse y Workable insatisfechos.
  _Early adopters_
  Startups serie A–B con founders técnicos."]:1

  COSTS["**ESTRUCTURA DE COSTOS**
  Personal 65% · Infra e IA 12% · Ventas 10% · Legal 8% · Operaciones 5%
  Burn rate: 30–40k USD/mes hasta 110–140k USD/mes al mes 12
  Objetivo Seed: 1.5–2 M USD"]:2

  SP(" "):1

  REV["**FUENTES DE INGRESOS**
  Starter 499 USD/mes · Growth 1 499 USD/mes · Scale desde 3 500 USD/mes
  SaaS recurrente · usuarios ilimitados · sin add-ons · prueba 30 días sin tarjeta
  ARR objetivo al mes 12: 500k–1 M USD"]:2

  style P     fill:#FCEBEB,stroke:#F09595,stroke-width:1.5px,color:#7F1D1D
  style S     fill:#EFF6FF,stroke:#85B7EB,stroke-width:1.5px,color:#1E3A5F
  style M     fill:#F0FDF4,stroke:#97C459,stroke-width:1.5px,color:#14532D
  style U     fill:#FEFCE8,stroke:#EF9F27,stroke-width:2px,color:#451A03
  style V     fill:#F5F3FF,stroke:#AFA9EC,stroke-width:1.5px,color:#2E1065
  style C     fill:#FFF7ED,stroke:#F0997B,stroke-width:1.5px,color:#7C2D12
  style G     fill:#F0FDF4,stroke:#5DCAA5,stroke-width:1.5px,color:#064E3B
  style COSTS fill:#FCEBEB,stroke:#F09595,stroke-width:1.5px,color:#7F1D1D
  style REV   fill:#F0FDF4,stroke:#97C459,stroke-width:1.5px,color:#14532D
  style SP    fill:transparent,stroke:transparent
```
---

## 8. Casos de Uso Principales

### Caso de Uso 1 — El Candidato Aplica a una Vacante

**Actor principal:** Candidato externo
**Objetivo:** Completar una aplicación desde cualquier dispositivo en menos de 4 minutos, con total claridad sobre qué pasará a continuación.

**Flujo paso a paso:**

1. El candidato accede al career site de la empresa o a la vacante publicada en un job board.
2. Selecciona la posición y hace clic en "Aplicar". El sistema detecta si está en móvil o escritorio y adapta el formulario.
3. Puede importar su perfil desde LinkedIn o subir su CV. El parser extrae automáticamente nombre, experiencia, formación y habilidades, pre-rellenando los campos sin que el candidato deba escribir lo que ya está en su CV.
4. El formulario presenta solo los campos estrictamente necesarios para esa posición. No hay páginas de registro previo ni captchas. El progreso se guarda automáticamente si el candidato abandona y retoma.
5. Al enviar, el candidato recibe confirmación inmediata por email y WhatsApp con el nombre del recruiter responsable y un enlace a su portal personal de seguimiento.
6. Desde ese portal, el candidato puede ver en qué etapa está su candidatura, cuándo esperar novedades y cómo fue evaluado (una vez que el proceso avanza).

**Resultado esperado:** Tasa de finalización de aplicación >80% · Tiempo medio de aplicación <4 minutos · NPS del candidato >50

**Diagrama de flujo:**

```mermaid
---
config:
  layout: elk
  theme: default
---
flowchart TD

    A([Candidato accede al career site o job board]) --> B[Selecciona vacante y hace clic en Aplicar]

    B --> C{¿Dispositivo del candidato?}

    C -->|Móvil| D[Formulario adaptado para móvil]
    C -->|Escritorio| E[Formulario estándar]

    D --> F[Importa perfil desde LinkedIn o sube CV]
    E --> F

    F --> G[Parser extrae datos automáticamente]

    G --> H[Campos pre-rellenados sin escritura manual]

    H --> I[Candidato completa campos mínimos requeridos]

    I --> J{¿Abandona antes de enviar?}

    J -->|Sí| K[(Progreso guardado automáticamente)]
    K --> I

    J -->|No| L[Envío de la candidatura]

    L --> M[Confirmación inmediata por email y WhatsApp]

    M --> N[Candidato recibe enlace al portal personal]

    N --> O([Portal de seguimiento: etapa, tiempos, evaluación])

    classDef startEnd fill:#f0fdf4,stroke:#4ade80,stroke-width:2px
    classDef process fill:#eef2ff,stroke:#818cf8,stroke-width:2px
    classDef decision fill:#fff7ed,stroke:#fb923c,stroke-width:2px
    classDef storage fill:#fdf4ff,stroke:#e879f9,stroke-width:2px

    class A,O startEnd
    class B,D,E,F,G,H,I,L,M,N process
    class C,J decision
    class K storage
```

**Diagrama UML de caso de uso:**

```mermaid
---
title: UML Caso de Uso 1 · El candidato aplica a una vacante
config:
  theme: default
---
flowchart LR

  C(["👤 Candidato"])
  S(["🤖 Sistema ATS (parser / IA)"])

  subgraph SYS["Sistema ATS"]
    UC1(["Acceder a vacante"])
    UC2(["Importar perfil desde LinkedIn"])
    UC3(["Subir CV y parsear datos"])
    UC4(["Completar formulario"])
    UC5(["Guardar progreso"])
    UC6(["Enviar candidatura"])
    UC7(["Consultar portal de seguimiento"])
  end

  C --> UC1
  C --> UC2
  C --> UC3
  C --> UC4
  C --> UC6

  UC1 -. "«include»" .-> UC2
  UC4 -. "«extend»" .-> UC5
  UC6 -. "«include»" .-> UC7

  S --> UC3
  S --> UC6

  style C    fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  style S    fill:#e2e8f0,stroke:#64748b,color:#1e293b
  style UC1  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC2  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC3  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC4  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC5  fill:#fffbeb,stroke:#d97706,color:#451a03
  style UC6  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC7  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style SYS  fill:#f8fafc,stroke:#94a3b8,stroke-width:2px,color:#334155
```

**Problema del mercado que resuelve:** El 60% de candidatos abandona aplicaciones complejas. El 69% abandona cuando el ATS falla al parsear su CV. Este caso de uso convierte la aplicación en una experiencia que el candidato quiere completar y recuerda positivamente.

---

### Caso de Uso 2 — El Hiring Manager Evalúa y Decide sobre un Candidato

**Actor principal:** Hiring Manager
**Objetivo:** Revisar un candidato y emitir una decisión en menos de 30 segundos desde el móvil, sin necesidad de acceder al sistema completo.

**Flujo paso a paso:**

1. El recruiter avanza un candidato a la etapa de revisión del hiring manager. El sistema genera automáticamente una notificación push y un email al HM.
2. El email contiene un magic link de acceso directo — sin usuario ni contraseña. El HM toca el enlace desde su teléfono.
3. Ve una tarjeta del candidato con: foto y nombre, resumen de 5 líneas generado por IA (experiencia relevante, puntos fuertes, posible fit con el rol), score de compatibilidad y el CV adjunto para quien quiera profundizar.
4. Debajo de la tarjeta, tres botones de acción: **Avanzar**, **Rechazar** y **Necesito más información** (que abre un campo de texto para dejar una nota al recruiter).
5. La decisión se registra en el sistema en tiempo real. El recruiter recibe la notificación de inmediato y puede actuar sobre el candidato sin esperar.
6. Si el HM no responde en 24 horas, el sistema envía un recordatorio automático. Si no responde en 48 horas, el recruiter recibe una alerta para hacer seguimiento.

**Resultado esperado:** Tasa de activación de HMs >75% · Tiempo de respuesta por candidato <24h · Reducción del time-to-hire en 5–15 días por vacante

**Diagrama de flujo:**

```mermaid
---
config:
  layout: elk
  theme: default
---
flowchart TD

    A([Recruiter avanza candidato a etapa HM Review])

    A --> B[Sistema genera notificación push + email al HM]

    B --> C[Email con magic link de acceso directo]

    C --> D{¿HM abre el enlace?}

    D -->|No — 24h| E[Sistema envía recordatorio automático]

    E --> D

    D -->|No — 48h| F[Alerta al recruiter para hacer seguimiento manual]

    D -->|Sí| G[HM ve tarjeta del candidato: foto, resumen IA 5 líneas, score de fit, CV adjunto]

    G --> H{Decisión del HM}

    H -->|Avanzar| I[Candidato pasa a etapa de entrevistas]

    H -->|Rechazar| J[Candidato marcado como rechazado]

    H -->|Necesito más info| K[HM deja nota al recruiter]

    K --> L[Recruiter recibe notificación y actúa]

    I --> M([Recruiter notificado en tiempo real])

    J --> M

    L --> M

    classDef processNode stroke:#818cf8,fill:#eef2ff
    classDef decisionNode stroke:#fb923c,fill:#fff7ed
    classDef alertNode stroke:#f87171,fill:#fef2f2
    classDef successNode stroke:#4ade80,fill:#f0fdf4
    classDef startEnd stroke:#2dd4bf,fill:#f0fdfa

    class B,C,E,G,L processNode
    class D,H decisionNode
    class F alertNode
    class I,M successNode
    class A,J startEnd
```

**Diagrama UML de caso de uso:**

```mermaid
---
title: UML Caso de Uso 2 · El hiring manager evalúa y decide
config:
  theme: default
---
flowchart LR

  R(["👤 Recruiter"])
  HM(["👤 Hiring Manager"])
  S(["🤖 Sistema ATS"])

  subgraph SYS["Sistema ATS"]
    UC1(["Avanzar candidato a HM Review"])
    UC2(["Enviar notificación + magic link"])
    UC3(["Revisar tarjeta del candidato"])
    UC4(["Tomar decisión sobre candidato"])
    UC5(["Enviar recordatorio automático"])
    UC6(["Registrar decisión en pipeline"])
  end

  R --> UC1
  R --> UC6

  HM --> UC3
  HM --> UC4

  UC1 -. "«include»" .-> UC2
  UC4 -. "«extend»" .-> UC5
  UC4 -. "«include»" .-> UC6

  S --> UC2
  S --> UC5

  style R    fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  style HM   fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  style S    fill:#e2e8f0,stroke:#64748b,color:#1e293b
  style UC1  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC2  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC3  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC4  fill:#fef9c3,stroke:#ca8a04,color:#713f12
  style UC5  fill:#fffbeb,stroke:#d97706,color:#451a03
  style UC6  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style SYS  fill:#f8fafc,stroke:#94a3b8,stroke-width:2px,color:#334155
```

**Problema del mercado que resuelve:** Los hiring managers evitan entrar al ATS porque les resulta complejo. Su falta de feedback genera el cuello de botella más costoso del proceso de selección. Este caso de uso elimina la fricción por diseño: el HM nunca necesita aprender el sistema.

---

### Caso de Uso 3 — El Recruiter Coordina y Confirma una Entrevista

**Actor principal:** Recruiter
**Objetivo:** Agendar una entrevista entre el candidato y el entrevistador sin intercambio manual de emails, en menos de 2 minutos.

**Flujo paso a paso:**

1. El recruiter selecciona al candidato en el pipeline y hace clic en "Agendar entrevista". Elige el tipo (phone screen, técnica, panel) y los entrevistadores involucrados.
2. El sistema consulta automáticamente la disponibilidad real del calendario de los entrevistadores (Google Calendar u Outlook) y genera tres opciones de horario compatibles para los próximos 5 días hábiles.
3. El recruiter confirma las opciones con un clic. El sistema envía al candidato un email y un WhatsApp con los tres slots propuestos, con un enlace de confirmación en un solo toque.
4. El candidato elige su horario preferido. El sistema envía invitaciones de calendario automáticamente a todos los participantes, con el enlace de videollamada incluido si aplica.
5. 24 horas antes de la entrevista, el sistema envía recordatorios automáticos al candidato y a los entrevistadores. 1 hora antes, un recordatorio final al candidato.
6. Si el candidato necesita reprogramar, puede hacerlo desde el enlace del email sin contactar al recruiter. El sistema renegocia la disponibilidad y actualiza todos los calendarios.
7. Finalizada la entrevista, el sistema solicita automáticamente a cada entrevistador que complete su scorecard, con un recordatorio si no lo hace en 24 horas.

**Resultado esperado:** Tiempo de coordinación por entrevista reducido de 45–90 min a menos de 2 min · Tasa de no-shows reducida >40% · 100% de scorecards completados antes de la siguiente etapa

**Diagrama de flujo:**

```mermaid
---
config:
  layout: elk
  theme: default
---
flowchart TD

    A([Recruiter selecciona candidato y hace clic en Agendar entrevista])

    A --> B[Elige tipo de entrevista y entrevistadores]

    B --> C[Sistema consulta calendarios Google Calendar / Outlook]

    C --> D[Genera 3 opciones de horario para los próximos 5 días hábiles]

    D --> E[Recruiter confirma las opciones con un clic]

    E --> F[Email + WhatsApp al candidato con 3 slots propuestos]

    F --> G{¿Candidato responde?}

    G -->|Elige horario| H[Sistema envía invitaciones de calendario a todos los participantes]

    G -->|Necesita reprogramar| I[Candidato reprograma desde el enlace de email]

    I --> C

    H --> J[Recordatorio automático 24h antes a todos]

    J --> K[Recordatorio final 1h antes al candidato]

    K --> L([Entrevista realizada])

    L --> M[Sistema solicita scorecard a cada entrevistador]

    M --> N{¿Scorecard completado en 24h?}

    N -->|Sí| O([Evaluación registrada en el pipeline])

    N -->|No| P[Recordatorio automático al entrevistador]

    P --> N

    classDef startEnd fill:#f0fdf4,stroke:#4ade80,stroke-width:2px
    classDef process fill:#ecfeff,stroke:#22d3ee,stroke-width:2px
    classDef decision fill:#fefce8,stroke:#facc15,stroke-width:2px
    classDef notification fill:#f5f3ff,stroke:#a78bfa,stroke-width:2px
    classDef feedback fill:#fff7ed,stroke:#fb923c,stroke-width:2px

    class A,L,O startEnd
    class B,C,D,E,H,J,K,M notification
    class F,I,P feedback
    class G,N decision
```

**Diagrama UML de caso de uso:**

```mermaid
---
title: UML Caso de Uso 3 · El recruiter coordina una entrevista
config:
  theme: default
---
flowchart LR

  R(["👤 Recruiter"])
  C(["👤 Candidato"])
  E(["👤 Entrevistador"])
  CAL(["📆 Calendario Google / Outlook"])

  subgraph SYS["Sistema ATS"]
    UC1(["Agendar entrevista"])
    UC2(["Consultar disponibilidad"])
    UC3(["Enviar slots al candidato"])
    UC4(["Confirmar horario"])
    UC5(["Reprogramar entrevista"])
    UC6(["Enviar recordatorios"])
    UC7(["Solicitar scorecard"])
  end

  R --> UC1

  C --> UC4
  C --> UC5

  E --> UC7

  CAL --> UC2

  UC1 -. "«include»" .-> UC2
  UC1 -. "«include»" .-> UC3

  UC4 -. "«include»" .-> UC6

  UC5 -. "«include»" .-> UC2

  UC4 -. "«extend»" .-> UC5

  UC7 -. "«extend»" .-> UC6

  style R    fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  style C    fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  style E    fill:#dbeafe,stroke:#3b82f6,color:#1e3a5f
  style CAL  fill:#e2e8f0,stroke:#64748b,color:#1e293b

  style UC1  fill:#fef9c3,stroke:#ca8a04,color:#713f12
  style UC2  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC3  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC4  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC5  fill:#fffbeb,stroke:#d97706,color:#451a03
  style UC6  fill:#f0fdf4,stroke:#16a34a,color:#14532d
  style UC7  fill:#f0fdf4,stroke:#16a34a,color:#14532d

  style SYS  fill:#f8fafc,stroke:#94a3b8,stroke-width:2px,color:#334155
```

**Problema del mercado que resuelve:** La coordinación de entrevistas es la tarea más repetitiva y frustrante del recruiter, y una de las principales causas de burnout en equipos de TA. Este caso de uso la convierte en un proceso de un clic que el sistema ejecuta completamente de forma autónoma.

---

## 9. Modelo de Datos

El modelo de datos cubre las entidades, atributos y relaciones necesarias para soportar los tres casos de uso principales: aplicación del candidato, evaluación por el hiring manager y coordinación de entrevistas. El diseño prioriza simplicidad y extensibilidad.

### 9.1 Entidades y Atributos

#### `Job` (Vacante)

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único de la vacante |
| `title` | STRING | Título del puesto |
| `description` | TEXT | Descripción completa del rol y responsabilidades |
| `requirements` | TEXT | Requisitos mínimos y deseables |
| `department` | STRING | Departamento o área de la empresa |
| `location` | STRING | Ubicación (ciudad, país o "remoto") |
| `employment_type` | ENUM | `full_time` · `part_time` · `contract` · `internship` |
| `salary_range_min` | INTEGER | Banda salarial mínima |
| `salary_range_max` | INTEGER | Banda salarial máxima |
| `status` | ENUM | `draft` · `published` · `paused` · `closed` |
| `published_at` | TIMESTAMP | Fecha y hora de publicación |
| `closes_at` | TIMESTAMP | Fecha límite de recepción (nullable) |
| `created_by` | UUID (FK → User) | Usuario que creó la vacante |
| `hiring_manager_id` | UUID (FK → User) | Hiring manager asignado |
| `created_at` | TIMESTAMP | Fecha de creación |
| `updated_at` | TIMESTAMP | Última modificación |

#### `Candidate` (Candidato)

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único del candidato |
| `first_name` | STRING | Nombre |
| `last_name` | STRING | Apellido |
| `email` | STRING (único) | Email principal |
| `phone` | STRING | Teléfono con prefijo de país |
| `linkedin_url` | STRING | URL del perfil LinkedIn (nullable) |
| `location` | STRING | Ciudad y país |
| `cv_url` | STRING | Ruta al archivo CV (PDF) |
| `parsed_experience` | JSONB | Experiencia laboral extraída del CV |
| `parsed_education` | JSONB | Formación académica extraída del CV |
| `parsed_skills` | ARRAY[STRING] | Habilidades extraídas del CV |
| `source` | ENUM | `linkedin` · `indeed` · `career_site` · `referral` · `agency` · `other` |
| `gdpr_consent` | BOOLEAN | Consentimiento explícito de tratamiento de datos |
| `gdpr_consent_at` | TIMESTAMP | Fecha y hora del consentimiento |
| `portal_token` | STRING | Token único para acceso al portal (sin login) |
| `created_at` | TIMESTAMP | Fecha de registro |
| `updated_at` | TIMESTAMP | Última modificación |

#### `Application` (Candidatura)

Entidad central del modelo. Representa la relación entre un candidato y una vacante específica, y contiene todo el estado del proceso de selección.

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único |
| `candidate_id` | UUID (FK → Candidate) | Candidato que aplica |
| `job_id` | UUID (FK → Job) | Vacante a la que aplica |
| `stage` | ENUM | `applied` · `screening` · `hm_review` · `interview` · `offer` · `hired` · `rejected` |
| `stage_updated_at` | TIMESTAMP | Cuándo cambió de etapa por última vez |
| `rejection_reason` | ENUM | `underqualified` · `overqualified` · `cultural_fit` · `position_cancelled` · `other` (nullable) |
| `rejection_note` | TEXT | Nota interna sobre el rechazo (no visible al candidato) |
| `ai_fit_score` | FLOAT | Score 0–1 de compatibilidad calculado por IA |
| `ai_summary` | TEXT | Resumen de 5 líneas generado por IA para el HM Inbox |
| `cover_letter` | TEXT | Carta de presentación (nullable) |
| `answers` | JSONB | Respuestas a preguntas de knockout |
| `candidate_nps` | INTEGER | Puntuación NPS del candidato (0–10, nullable) |
| `candidate_nps_comment` | TEXT | Comentario libre del candidato (nullable) |
| `assigned_recruiter_id` | UUID (FK → User) | Recruiter responsable |
| `created_at` | TIMESTAMP | Fecha de aplicación |
| `updated_at` | TIMESTAMP | Última modificación |

#### `User` (Usuario interno)

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único |
| `first_name` | STRING | Nombre |
| `last_name` | STRING | Apellido |
| `email` | STRING (único) | Email corporativo |
| `role` | ENUM | `admin` · `recruiter` · `hiring_manager` · `ta_lead` · `viewer` |
| `department` | STRING | Departamento |
| `calendar_provider` | ENUM | `google` · `outlook` · `none` |
| `calendar_token` | TEXT | Token OAuth para calendario (encriptado, nullable) |
| `notification_email` | BOOLEAN | Recibe notificaciones por email |
| `notification_push` | BOOLEAN | Recibe notificaciones push móvil |
| `magic_link_token` | STRING | Token temporal para HM Inbox (nullable, expira en 72h) |
| `magic_link_expires_at` | TIMESTAMP | Expiración del magic link activo (nullable) |
| `is_active` | BOOLEAN | Si el usuario tiene acceso activo |
| `last_login_at` | TIMESTAMP | Fecha y hora del último acceso (nullable) |
| `created_at` | TIMESTAMP | Fecha de creación |
| `updated_at` | TIMESTAMP | Última modificación |

#### `Interview` (Entrevista)

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único |
| `application_id` | UUID (FK → Application) | Candidatura a la que pertenece |
| `type` | ENUM | `phone_screen` · `technical` · `panel` · `cultural_fit` · `final` |
| `status` | ENUM | `proposed` · `scheduled` · `confirmed` · `completed` · `cancelled` · `no_show` |
| `scheduled_at` | TIMESTAMP | Fecha y hora definitiva (nullable hasta confirmar) |
| `duration_minutes` | INTEGER | Duración prevista en minutos |
| `location_type` | ENUM | `video` · `phone` · `in_person` |
| `video_link` | STRING | URL de la videollamada (nullable) |
| `reminder_sent_24h` | BOOLEAN | Si se envió el recordatorio de 24h |
| `reminder_sent_1h` | BOOLEAN | Si se envió el recordatorio de 1h |
| `created_by` | UUID (FK → User) | Usuario que creó la entrevista |
| `created_at` | TIMESTAMP | Fecha de creación |
| `updated_at` | TIMESTAMP | Última modificación |

#### `InterviewParticipant` (Participante de entrevista)

Tabla de unión entre `Interview` y `User` que registra a cada entrevistador y su estado de confirmación y evaluación.

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único |
| `interview_id` | UUID (FK → Interview) | Entrevista a la que pertenece |
| `user_id` | UUID (FK → User) | Entrevistador asignado |
| `confirmed` | BOOLEAN | Si el entrevistador confirmó asistencia |
| `confirmed_at` | TIMESTAMP | Cuándo confirmó (nullable) |
| `calendar_event_id` | STRING | ID del evento en calendario (nullable) |
| `scorecard_submitted` | BOOLEAN | Si completó y envió su scorecard |
| `scorecard_submitted_at` | TIMESTAMP | Cuándo lo envió (nullable) |
| `created_at` | TIMESTAMP | Fecha de creación |

#### `Scorecard` (Evaluación de entrevista)

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único |
| `interview_participant_id` | UUID (FK → InterviewParticipant) | Evaluador y entrevista correspondientes |
| `application_id` | UUID (FK → Application) | Candidatura evaluada |
| `overall_rating` | ENUM | `strong_yes` · `yes` · `neutral` · `no` · `strong_no` |
| `criteria_scores` | JSONB | Puntuaciones por criterio (ej. `{"technical": 4, "communication": 3}`) |
| `strengths` | TEXT | Puntos fuertes observados |
| `concerns` | TEXT | Dudas o puntos débiles observados |
| `notes` | TEXT | Notas libres adicionales |
| `submitted_at` | TIMESTAMP | Fecha y hora de envío |
| `created_at` | TIMESTAMP | Fecha de creación |

#### `Notification` (Notificación)

| Atributo | Tipo | Descripción |
|---|---|---|
| `id` | UUID | Identificador único |
| `recipient_type` | ENUM | `candidate` · `user` |
| `recipient_id` | UUID | ID del candidato o usuario destinatario |
| `channel` | ENUM | `email` · `whatsapp` · `push` · `sms` |
| `type` | ENUM | `application_received` · `stage_change` · `interview_scheduled` · `interview_reminder` · `scorecard_request` · `hm_inbox_alert` · `rejection` · `offer` |
| `status` | ENUM | `pending` · `sent` · `delivered` · `failed` |
| `sent_at` | TIMESTAMP | Cuándo fue enviada (nullable) |
| `payload` | JSONB | Contenido y variables de la notificación |
| `related_entity_type` | STRING | Entidad relacionada: `application`, `interview`, etc. |
| `related_entity_id` | UUID | ID de la entidad relacionada |
| `created_at` | TIMESTAMP | Fecha de creación |

### 9.2 Relaciones entre Entidades

**Diagrama entidad-relación (ERD):**

```mermaid
erDiagram

  User {
    uuid id PK
    string first_name
    string last_name
    string email
    enum role
    enum calendar_provider
    string magic_link_token
    timestamp magic_link_expires_at
    boolean is_active
    timestamp created_at
  }

  Job {
    uuid id PK
    string title
    text description
    text requirements
    string department
    string location
    enum employment_type
    integer salary_range_min
    integer salary_range_max
    enum status
    timestamp published_at
    timestamp closes_at
    uuid created_by FK
    uuid hiring_manager_id FK
    timestamp created_at
  }

  Candidate {
    uuid id PK
    string first_name
    string last_name
    string email
    string phone
    string cv_url
    jsonb parsed_experience
    jsonb parsed_education
    array parsed_skills
    enum source
    boolean gdpr_consent
    timestamp gdpr_consent_at
    string portal_token
    timestamp created_at
  }

  Application {
    uuid id PK
    uuid candidate_id FK
    uuid job_id FK
    uuid assigned_recruiter_id FK
    enum stage
    timestamp stage_updated_at
    enum rejection_reason
    float ai_fit_score
    text ai_summary
    jsonb answers
    integer candidate_nps
    timestamp created_at
  }

  Interview {
    uuid id PK
    uuid application_id FK
    uuid created_by FK
    enum type
    enum status
    timestamp scheduled_at
    integer duration_minutes
    enum location_type
    string video_link
    boolean reminder_sent_24h
    boolean reminder_sent_1h
    timestamp created_at
  }

  InterviewParticipant {
    uuid id PK
    uuid interview_id FK
    uuid user_id FK
    boolean confirmed
    timestamp confirmed_at
    string calendar_event_id
    boolean scorecard_submitted
    timestamp scorecard_submitted_at
    timestamp created_at
  }

  Scorecard {
    uuid id PK
    uuid interview_participant_id FK
    uuid application_id FK
    enum overall_rating
    jsonb criteria_scores
    text strengths
    text concerns
    text notes
    timestamp submitted_at
    timestamp created_at
  }

  Notification {
    uuid id PK
    enum recipient_type
    uuid recipient_id
    enum channel
    enum type
    enum status
    timestamp sent_at
    jsonb payload
    string related_entity_type
    uuid related_entity_id
    timestamp created_at
  }

  User ||--o{ Job : "crea (created_by)"
  User ||--o{ Job : "gestiona (hiring_manager)"
  User ||--o{ Application : "asignado como recruiter"
  User ||--o{ Interview : "agenda (created_by)"
  User ||--o{ InterviewParticipant : "participa como entrevistador"

  Job ||--o{ Application : "recibe"

  Candidate ||--o{ Application : "realiza"

  Application ||--o{ Interview : "genera"
  Application ||--o{ Scorecard : "acumula"
  Application ||--o{ Notification : "dispara"

  Interview ||--o{ InterviewParticipant : "tiene"
  Interview ||--o{ Notification : "genera"

  InterviewParticipant ||--|| Scorecard : "entrega"
```

### 9.3 Relaciones Principales

| Relación | Cardinalidad | Descripción |
|---|---|---|
| `User` → `Job` (hiring_manager) | 1:N | Un hiring manager puede tener múltiples vacantes asignadas |
| `Job` → `Application` | 1:N | Una vacante recibe múltiples candidaturas |
| `Candidate` → `Application` | 1:N | Un candidato puede aplicar a múltiples vacantes |
| `Application` → `Interview` | 1:N | Una candidatura puede tener múltiples entrevistas |
| `Interview` → `InterviewParticipant` | 1:N | Una entrevista puede tener múltiples entrevistadores |
| `InterviewParticipant` → `Scorecard` | 1:1 | Cada participante entrega un único scorecard por entrevista |
| `Application` → `Scorecard` | 1:N | Una candidatura acumula scorecards de cada entrevistador en cada ronda |
| `Application` → `Notification` | 1:N | Una candidatura genera múltiples notificaciones a lo largo del proceso |

### 9.4 Reglas de Negocio Principales

**Unicidad de candidatura:** No puede existir más de una `Application` activa entre el mismo `Candidate` y el mismo `Job`.

**Progresión de etapas:** El campo `stage` sigue una máquina de estados. Transiciones válidas: `applied → screening → hm_review → interview → offer → hired`. Cualquier etapa puede transicionar a `rejected`. No se permiten retrocesos excepto de `hm_review` a `screening`.

**Integridad del scorecard:** No se puede avanzar una `Application` de `interview` a `offer` si existe algún `InterviewParticipant` con `scorecard_submitted = false` en la última ronda.

**Expiración del magic link:** El `magic_link_token` expira en 72 horas. Cada nueva alerta al HM genera un nuevo token y anula el anterior.

**Consentimiento GDPR:** No se puede crear una `Application` si `Candidate.gdpr_consent = false`. Los registros sin candidaturas activas se eliminan automáticamente a los 12 meses.

---

## 10. Diseño del Sistema a Alto Nivel

El sistema sigue una arquitectura de **monolito modular** en la fase de diseño preliminar, con separación clara entre módulos para facilitar la extracción a microservicios cuando el crecimiento lo justifique. Esta decisión evita la complejidad operacional prematura de los microservicios manteniendo velocidad de desarrollo sin sacrificar la separación de responsabilidades.

```
┌─────────────────────────────────────────────────────────────────┐
│                         CLIENTES                                │
├──────────────┬──────────────────┬───────────────────────────────┤
│  Web App     │   Mobile Web     │   HM Inbox (magic link)       │
│  (React SPA) │   (PWA)          │   (email → token URL)         │
├──────────────┴──────────────────┴───────────────────────────────┤
│                        CDN / Edge                               │
│              (assets estáticos, cache de respuestas)            │
├─────────────────────────────────────────────────────────────────┤
│                      API GATEWAY                                │
│   Rate limiting · Autenticación JWT · Routing · Logging         │
├────────────┬────────────┬────────────┬────────────┬─────────────┤
│  Auth      │  Jobs      │  Pipeline  │ Interviews │ Notif.      │
│  Module    │  Module    │  Module    │  Module    │  Module     │
├────────────┴────────────┴────────────┴────────────┴─────────────┤
│                     SERVICIOS TRANSVERSALES                     │
│   AI Service · CV Parser · Calendar Sync · File Storage         │
├─────────────────────────────────────────────────────────────────┤
│                        CAPA DE DATOS                            │
│   PostgreSQL (principal) · Redis (cache/jobs) · S3 (archivos)   │
├─────────────────────────────────────────────────────────────────┤
│                   INFRAESTRUCTURA / CLOUD                       │
│   AWS / Railway · CI/CD · Monitoring · Alerting                 │
└─────────────────────────────────────────────────────────────────┘
```

**Diagrama de arquitectura:**

```mermaid
---
config:
  layout: elk
  theme: default
---
graph TD

  subgraph CLIENTES["Capa de presentacion"]
    direction LR

    SPA["Web App React SPA (recruiter / admin)"]
    PWA["Candidate Portal PWA (candidato)"]
    HMI["HM Inbox Magic link view (hiring manager)"]
  end

  subgraph EDGE["CDN / Edge"]

    CDN["Cloudflare Assets estaticos | Cache | DDoS"]
  end

  subgraph GATEWAY["API Gateway"]

    GW["Rate limiting | JWT auth | RBAC | Routing | Logging | CORS"]
  end

  subgraph BACKEND["Modulos del backend - monolito modular"]
    direction LR

    AUTH["auth Login | SSO OAuth2 JWT | Magic links"]

    JOBS["jobs CRUD vacantes Publicacion multicanal"]

    PIPE["pipeline Kanban candidatos Maquina de estados Webhooks HRIS"]

    INTV["interviews Agendado | iCal Scorecards"]

    NOTIF["notifications Email | WhatsApp Push | Cola + reintentos"]
  end

  subgraph SERVICIOS["Servicios transversales"]
    direction LR

    CVPARSER["CV Parser LLM ligero PDF / DOCX to JSON"]

    AI["AI Scoring Fit score | Resumen HM Audit log bias"]

    CALSYNC["Calendar Sync Google Calendar API Microsoft Graph API"]

    FILES["File Storage S3 / R2 URLs firmadas | GDPR"]
  end

  subgraph DATOS["Capa de datos"]
    direction LR

    PG["PostgreSQL Datos relacionales RLS multi-tenant"]

    REDIS["Redis Cache | Cola BullMQ Recordatorios programados"]

    S3["S3 / R2 CVs | documentos Retencion GDPR"]
  end

  subgraph INFRA["Infraestructura / Cloud"]
    direction LR

    HOST["Railway to AWS ECS Hosting backend"]

    CICD["GitHub Actions CI/CD | Tests | Docker"]

    MON["Sentry | Datadog Monitoreo | Alertas"]
  end

  subgraph EXTERNOS["Servicios externos"]
    direction LR

    LI["LinkedIn Jobs API"]

    IND["Indeed API"]

    WA["WhatsApp Business API"]

    MAIL["SendGrid / Resend"]

    GCAL["Google Calendar / MS Graph"]

    LLM["LLM externo GPT-4o mini"]
  end

  SPA --> CDN
  PWA --> CDN
  HMI --> CDN

  CDN --> GW

  GW --> AUTH
  GW --> JOBS
  GW --> PIPE
  GW --> INTV
  GW --> NOTIF

  PIPE --> CVPARSER
  PIPE --> AI

  INTV --> CALSYNC

  NOTIF --> FILES

  AUTH --> PG
  JOBS --> PG
  PIPE --> PG
  INTV --> PG
  NOTIF --> PG

  CVPARSER --> REDIS
  AI --> REDIS
  NOTIF --> REDIS

  FILES --> S3

  HOST --- PG
  HOST --- REDIS
  HOST --- S3

  CICD --> HOST

  MON -.-> HOST

  JOBS --> LI
  JOBS --> IND

  NOTIF --> WA
  NOTIF --> MAIL

  CALSYNC --> GCAL

  CVPARSER --> LLM
  AI --> LLM
```

El sistema se organiza en siete capas con responsabilidades claramente delimitadas. Los tres clientes — la Web App para recruiters, el Candidate Portal para candidatos y el HM Inbox para hiring managers — acceden al sistema a través de Cloudflare, que actúa como CDN y primera línea de protección. Todo el tráfico entra por un único API Gateway que centraliza autenticación JWT, control de acceso por rol (RBAC), rate limiting y logging estructurado.

El backend es un **monolito modular** compuesto por cinco módulos independientes: `auth` gestiona identidad y magic links; `jobs` controla el ciclo de vida de vacantes y su distribución a job boards externos; `pipeline` es el núcleo transaccional que mueve candidatos entre etapas con validación de reglas de negocio; `interviews` orquesta el agendado con integración de calendarios; y `notifications` opera el motor multicanal de comunicaciones con cola de reintentos.

Los cuatro **servicios transversales** son consumidos por múltiples módulos: el CV Parser extrae datos estructurados de documentos vía LLM; el AI Scoring calcula el fit del candidato y genera el resumen para el HM Inbox; el Calendar Sync abstrae las diferencias entre Google Calendar y Microsoft Graph; y el File Storage gestiona el ciclo de vida de archivos con URLs firmadas y purga GDPR.

La **capa de datos** combina PostgreSQL como base relacional principal con Row-Level Security para aislamiento multi-tenant, Redis para cache de consultas frecuentes y cola de trabajos asíncronos (BullMQ), y S3/R2 para almacenamiento de archivos. El despliegue arranca en Railway para el MVP y migra a AWS ECS al superar los 500 clientes, con GitHub Actions como pipeline de CI/CD y Sentry + Datadog para observabilidad en producción.

**Decisiones de seguridad clave:**

| Capa | Medida implementada |
|---|---|
| Transporte | HTTPS obligatorio en todos los endpoints. HSTS activado. |
| Autenticación | JWT con access tokens de 1h. Refresh tokens de 30 días. Magic links de un solo uso con expiración de 72h |
| Autorización | RBAC estricto por endpoint. Un recruiter solo puede operar candidaturas de sus vacantes asignadas |
| Datos en reposo | Encriptación AES-256 en la base de datos. Tokens OAuth encriptados a nivel de columna |
| Multi-tenancy | Row-Level Security en PostgreSQL. `organization_id` aplicado automáticamente vía middleware |
| GDPR | Endpoint de borrado de datos de candidato. Purga automática programada a los 12 meses |


**Justificación de la Arquitectura — Monolito Modular para el Backend del ATS**

La decisión de adoptar una arquitectura de **monolito modular** para el backend de la plataforma ATS responde a un balance deliberado entre velocidad de desarrollo, madurez del equipo, complejidad operacional y horizonte de crecimiento. Esta arquitectura permite construir un producto sólido, mantenible y con separación clara de responsabilidades desde el día 1, sin incurrir en la sobrecarga operacional que impondrían los microservicios en una fase de producto tan temprana.

- Evitar Complejidad Operacional Prematura
- Velocidad de Desarrollo como Ventaja Competitiva
- Separación de Responsabilidades sin Sobrecarga de Red
- Compatibilidad con la Capa de Datos Elegida
- El Módulo de Notificaciones como Caso de Validación

Los módulos están diseñados con fronteras claras para que, cuando el negocio lo requiera, puedan extraerse como microservicios sin necesidad de reescribir el dominio de negocio.
 
La arquitectura está diseñada para evolucionar: cuando el volumen de clientes, la madurez del equipo o los patrones de carga lo justifiquen, los módulos están listos para ser extraídos. Hasta entonces, el monolito modular es la apuesta que maximiza la velocidad de entrega, minimiza la complejidad operacional y mantiene la integridad transaccional que las reglas de negocio del ATS exigen.

---

## 11. Diagrama C4 — Módulo de Notificaciones en Profundidad

El módulo de Notificaciones es el componente de mayor volumen del sistema y el más crítico para la experiencia del candidato y la adopción del hiring manager. Se profundiza en él hasta el nivel de código (C4 nivel 4).

### Nivel 1 — Contexto del Sistema

```mermaid
---
config:
  layout: elk
  theme: default
---
graph TB

  subgraph USUARIOS["Usuarios y actores externos"]
    CAND["👤 Candidato"]
    HM["👤 Hiring Manager"]
    REC["👤 Recruiter"]
  end

  subgraph SYS["Sistema ATS"]
    ATS["Plataforma ATS\n(monolito modular)"]
  end

  subgraph EXTERNOS["Canales externos"]
    EMAIL["📧 Email\n(SendGrid / Resend)"]
    WA["💬 WhatsApp\n(Business API)"]
    PUSH["🔔 Push\n(Firebase FCM)"]
  end

  CAND -->|"aplica, confirma entrevista"| ATS
  HM -->|"evalúa candidato vía magic link"| ATS
  REC -->|"gestiona pipeline"| ATS

  ATS -->|"notificaciones de estado"| EMAIL
  ATS -->|"confirmaciones y recordatorios"| WA
  ATS -->|"alertas en tiempo real"| PUSH

  EMAIL --> CAND
  WA --> CAND
  WA --> HM
  PUSH --> REC

  style ATS fill:#dbeafe,stroke:#3b82f6
  style USUARIOS fill:#f0fdf4,stroke:#4ade80
  style EXTERNOS fill:#fff7ed,stroke:#fb923c
```

### Nivel 2 — Contenedores del Sistema

```mermaid
---
config:
  layout: elk
  theme: default
---
graph TB

  subgraph SPA["Web App (React SPA)"]
    UI["Frontend recruiter / admin"]
  end

  subgraph API["API Gateway"]
    GW["JWT auth · RBAC · Routing"]
  end

  subgraph BACK["Backend — Monolito Modular"]
    PIPE["Módulo Pipeline"]
    INTV["Módulo Interviews"]
    NOTIF["🔴 Módulo Notifications\n(componente en foco)"]
  end

  subgraph DATOS["Capa de datos"]
    PG["PostgreSQL"]
    REDIS["Redis + BullMQ"]
  end

  subgraph CANALES["Servicios de envío"]
    SG["SendGrid / Resend"]
    WA["WhatsApp API"]
    FCM["Firebase FCM"]
  end

  UI --> GW
  GW --> PIPE
  GW --> INTV

  PIPE -->|"dispara eventos"| NOTIF
  INTV -->|"dispara eventos"| NOTIF

  NOTIF --> PG
  NOTIF --> REDIS
  NOTIF --> SG
  NOTIF --> WA
  NOTIF --> FCM

  style NOTIF fill:#fef2f2,stroke:#f87171,stroke-width:3px
```

### Nivel 3 — Componentes del Módulo de Notificaciones

```mermaid
---
config:
  layout: elk
  theme: default
---
graph TD

  subgraph NOTIF["Módulo Notifications"]

    EVENT["Event Listener\nEscucha eventos del sistema\n(application_stage_changed,\ninterview_scheduled, etc.)"]

    DEDUP["Deduplication Guard\nVerifica si ya existe una notif\ndel mismo tipo en las últimas N horas\npara evitar duplicados"]

    TEMPLATE["Template Engine\nCarga la plantilla por tipo de notif\nInyecta variables dinámicas\n(nombre, vacante, fecha, link)"]

    QUEUE["Notification Queue\n(BullMQ sobre Redis)\nEncola trabajos de envío\ncon reintentos exponenciales"]

    DISPATCHER["Channel Dispatcher\nEnruta al canal correcto\n(email / WhatsApp / push)\nsegún preferencias del destinatario"]

    LOGGER["Notification Logger\nRegistra resultado en tabla\nNotification de PostgreSQL\n(sent, delivered, failed)"]
  end

  subgraph CANALES["Adaptadores de canal"]
    EMAIL_ADAPTER["Email Adapter\n(SendGrid / Resend)"]
    WA_ADAPTER["WhatsApp Adapter\n(Twilio / 360dialog)"]
    PUSH_ADAPTER["Push Adapter\n(Firebase FCM)"]
  end

  EVENT --> DEDUP
  DEDUP -->|"no duplicado"| TEMPLATE
  DEDUP -->|"duplicado detectado"| LOGGER

  TEMPLATE --> QUEUE
  QUEUE --> DISPATCHER

  DISPATCHER --> EMAIL_ADAPTER
  DISPATCHER --> WA_ADAPTER
  DISPATCHER --> PUSH_ADAPTER

  EMAIL_ADAPTER --> LOGGER
  WA_ADAPTER --> LOGGER
  PUSH_ADAPTER --> LOGGER

  style EVENT fill:#dbeafe,stroke:#3b82f6
  style DEDUP fill:#fef9c3,stroke:#ca8a04
  style TEMPLATE fill:#f0fdf4,stroke:#16a34a
  style QUEUE fill:#fdf4ff,stroke:#e879f9
  style DISPATCHER fill:#ecfeff,stroke:#22d3ee
  style LOGGER fill:#f8fafc,stroke:#94a3b8
```

### Nivel 4 — Código: Notification Queue Worker

El componente de mayor complejidad interna es el **Queue Worker**, que procesa los trabajos de envío de forma asíncrona con manejo de errores, reintentos y logging.

```typescript
// notifications/queue/worker.ts

interface NotificationJob {
  notificationId: string;
  recipientType: 'candidate' | 'user';
  recipientId: string;
  channel: 'email' | 'whatsapp' | 'push';
  templateType: NotificationTemplateType;
  variables: Record<string, string>;
  attemptCount: number;
}

class NotificationWorker {
  // Procesa un trabajo de la cola BullMQ
  async process(job: NotificationJob): Promise<void> {
    const adapter = this.resolveAdapter(job.channel);

    try {
      // 1. Renderizar la plantilla con variables dinámicas
      const rendered = await this.templateEngine.render(
        job.templateType,
        job.variables
      );

      // 2. Enviar por el canal correspondiente
      const result = await adapter.send({
        recipientId: job.recipientId,
        content: rendered,
      });

      // 3. Registrar el resultado como enviado
      await this.logger.markSent(job.notificationId, result.externalId);

    } catch (error) {
      // 4. Reintentos con backoff exponencial (máx 3 intentos)
      if (job.attemptCount < 3) {
        const delayMs = Math.pow(2, job.attemptCount) * 1000; // 1s, 2s, 4s
        await this.queue.retryAfter(job, delayMs);
      } else {
        // 5. Marcar como fallido tras agotar reintentos
        await this.logger.markFailed(job.notificationId, error.message);
      }
    }
  }

  private resolveAdapter(channel: string): ChannelAdapter {
    const adapters = {
      email: this.emailAdapter,
      whatsapp: this.whatsappAdapter,
      push: this.pushAdapter,
    };
    return adapters[channel];
  }
}
```

**Decisiones de diseño del módulo:**
- La cola BullMQ sobre Redis desacopla el disparo del evento del envío efectivo, permitiendo que los módulos de Pipeline e Interviews no esperen a que se complete el envío.
- El Deduplication Guard evita que una candidatura reciba dos notificaciones del mismo tipo en corto tiempo (ej. dos recordatorios de entrevista por error del sistema).
- El backoff exponencial protege la tasa de envío ante picos de carga y respeta los rate limits de los proveedores externos.
- El registro completo en `Notification` permite auditoría, depuración y cálculo de métricas de entregabilidad por canal.

---

## 12. Conclusión Estratégica — Por Qué Este ATS Gana al Mercado

### La ventana estratégica

El mercado ATS tiene $3.1B en facturación anual con un CAGR proyectado del 8.1% hasta 2034. El 97.8% de las empresas Fortune 500 usa un ATS. Y sin embargo, el **68% de los usuarios reporta frustración** con su sistema actual.

Los líderes actuales (Greenhouse, iCIMS, Workday) resolvieron correctamente la organización del pipeline de candidatos pero **fallaron sistemáticamente en lo que más importa: la experiencia humana del proceso**.

### Nosotros vs. el mercado actual

| Dimensión | Mercado actual | Este ATS |
|---|---|---|
| Experiencia candidato | Formularios lentos, sin transparencia | 4 min, tracking en tiempo real, siempre respuesta |
| Adopción HM | Sistema complejo, baja adopción | Magic link, 3 botones, 30 segundos |
| IA | Feature de marketing, poco impacto real | Copiloto que ejecuta y aprende con datos propios |
| Analytics | Dashboards básicos, exportar a Excel | Por rol, accionables, con alertas automáticas |
| Integración HRIS | Campos básicos, sincronización parcial | Bidireccional profunda, todos los campos |
| Flexibilidad | La empresa se adapta al ATS | El ATS se adapta a la empresa |
| Pricing | Opaco, add-ons, penaliza crecimiento | Transparente, sin sorpresas, escala con éxito |

### Los 7 diferenciadores que hacen ganar

1. **Candidato en el centro** → Ataca pain #1 y #3 · NPS candidato objetivo >50
2. **HM Inbox (30 segundos)** → Ataca pain #2 · Time-to-hire -30% · Adopción HM >75%
3. **IA que ejecuta** → Ataca pain #8 · Elimina 40% de tareas administrativas
4. **Analytics accionables** → Ataca pain #5 · TA como función estratégica
5. **HRIS bidireccional profundo** → Ataca pain #4 · 3–5 horas ahorradas por contratación
6. **Workflows no-code** → Ataca pain #7 · Sin dependencia de IT · Alta flexibilidad
7. **Pricing transparente** → Ataca pain #6 · NRR objetivo >115%

### La tesis final

> Los ATS actuales construyeron herramientas para gestionar candidatos. Nosotros construimos una plataforma para que las empresas contraten mejor y los candidatos vivan el mejor proceso de su vida.

Esa diferencia de perspectiva — del sistema al ser humano — genera un producto 10x superior y un volante de crecimiento que se autorefuerza:

- Cada candidato satisfecho habla bien de la empresa y genera employer brand orgánico
- Cada recruiter que contrata más rápido demuestra ROI interno y renueva el contrato
- Cada hiring manager que decide en 30 segundos reduce el time-to-hire y la fricción del equipo
- Cada dato generado por el uso del producto hace la IA más precisa y el diferenciador más defendible

**El mercado está listo. Los usuarios están frustrados. La tecnología está disponible. La ventana está abierta.**

---

*Documento preparado por Senior Product Manager · Mayo 2026*
*Confidencial — Uso interno. No distribuir sin autorización.*
