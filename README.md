# 🌱 Fricción de Captura: La Última Milla de Datos Agrícola

> **Maker Fellowship — AI-Native · Reto Producto**
> Definición de problema real + Statement AI-First

---

## 📋 Tabla de Contenidos

- **Semana 1: Problema Real + Statement AI-First**
  - [El Problema](#-el-problema)
  - [Hipótesis de Usuario y Contexto](#-hipótesis-de-usuario-y-contexto)
  - [Flujo Actual del Problema](#-flujo-actual-del-problema)
  - [Statement AI-First](#-statement-ai-first)
  - [Evidencia de Exploración](#-evidencia-de-exploración)
  - [Metodologías Aplicadas](#-metodologías-aplicadas)
  - [Referencias](#-referencias)
  - [Deploy](#-deploy)
- **Semana 2: Problema Validado + Usuario Claro**
  - [Usuario Objetivo](#usuario-objetivo)
  - [Evidencia de Validación (6 Entrevistas)](#evidencia-de-validación-6-entrevistas)
  - [Hallazgos clave](#hallazgos-clave)
  - [Flujos Validados (Ajustes vs. Semana 1)](#flujos-validados-ajustes-vs-semana-1)
  - [Flujo AI-First Mejorado (Semana 2)](#flujo-ai-first-mejorado-semana-2)
  - [Hipótesis Ajustadas (vs. Semana 1)](#hipótesis-ajustadas-vs-semana-1)
  - [Registro de Aprendizajes y Decisiones (AI-Light)](#registro-de-aprendizajes-y-decisiones-ai-light)

---

## 🔍 El Problema

**En fincas agrícolas de exportación en Latinoamérica, una porción significativa de la información operativa diaria nunca llega a un sistema digital.** Esta es una observación directa validada en campo — no un dato estadístico publicado, sino una realidad que se repite finca tras finca.

Existe una desconexión crítica entre la realidad operativa del campo y los sistemas de gestión digital. Los trabajadores agrícolas y jefes de campo generan datos valiosos cada minuto — detección de plagas, uso de insumos, avance de labores, gastos en campo — pero el **costo cognitivo y operativo de registrar estos datos digitalmente es demasiado alto**.

Las interfaces tradicionales (formularios, apps con menús desplegables, ERPs) exigen una atención visual y una motricidad fina que son **incompatibles con el entorno físico del campo**:

| Característica del campo | Lo que exige el software |
|---|---|
| Manos sucias, mojadas, con guantes | Teclados y selectores pequeños |
| Luz solar directa sobre pantalla | Lectura precisa de texto UI |
| Movimiento constante entre lotes | Interfaces complejas que exigen atención visual sostenida (aún con apps offline, la fricción de llenar formularios persiste) |
| Urgencia operativa (30 seg máx.) | Formularios de 8-15 campos |
| Jerga local ("bombadas", "canecas", "qq") | Vocabulario estandarizado en UI |

Como resultado, la información se captura en **medios analógicos o semi-digitales** (libretas, formatos de Excel descargados para llenar a mano, memoria) o se pierde en **canales no estructurados** (audios informales de WhatsApp), creando una **"oscuridad de datos"** que impide la toma de decisiones en tiempo real.

> **Validación externa**: Diagnósticos de CEPAL, FAO e IICA confirman que, pese a la alta penetración de telefonía móvil, la captura de datos operativos en la agricultura de ALC sigue siendo mayoritariamente analógica, con importantes brechas de uso de soluciones digitales avanzadas, especialmente entre pequeños y medianos productores ([Nagel, CEPAL](https://observatorioecuadordigital.mintel.gob.ec/wp-content/uploads/2022/11/S2013050_en_compressed.pdf); [FAO, 2021](https://openknowledge.fao.org/server/api/core/bitstreams/7043933b-dd27-4674-92ec-4bbfef8a4d48/content); [CEPAL & IICA, 2024](https://agriculturadigital.cepal.org/sites/default/files/2024-08/Digitalization%20in%20the%20agricultural%20sector%20in%20Latin%20America%20and%20the%20Caribbean.pdf)). Un [estudio regional sobre barreras a la agricultura digital](https://www.alice.cnptia.embrapa.br/alice/bitstream/doc/1175490/1/AP-Drivers-and-Barriers-2025.pdf) identifica como obstáculos: baja alfabetización digital, interfaces inadecuadas al contexto de campo, y altos costos de adopción.

> **TL;DR**: El campo genera datos. El software los necesita. Pero la interfaz entre ambos está rota. No es un problema de tecnología — es un problema de *fricción de captura*.

---

## 🧑‍🌾 Hipótesis de Usuario y Contexto

> ⚠️ **Declaramos estas como hipótesis explícitas**, validadas parcialmente a través de observación directa y desarrollo iterativo con usuarios reales en fincas de banano y cacao en Ecuador y Guatemala.

### Usuario Primario
**El Jefe de Campo** (o capataz) en fincas de exportación de banano, cacao, café o palma en Latinoamérica.

- **Perfil**: 30-55 años, experiencia empírica extensa, responsable de coordinar entre 5 y 30 trabajadores diarios.
- **Habilidades digitales**: Usa WhatsApp nativamente (voz, fotos, texto). No saben usar apps administrativas complejas.
- **Motivación**: Ejecutar la operación del día, no documentarla.

### Contexto Físico
- Entorno al **aire libre**, con conectividad intermitente (2G-4G irregular).
- Condiciones climáticas variables: lluvia, sol directo, humedad alta.
- **Exigencia física constante** — el usuario camina entre 5-15 km diarios recorriendo lotes.

### Contexto Tecnológico
- **Alta penetración de smartphones** (Android de gama media-baja) y uso nativo de WhatsApp como canal de coordinación. [CEPAL documenta](https://agriculturadigital.cepal.org/sites/default/files/2024-08/Digitalization%20in%20the%20agricultural%20sector%20in%20Latin%20America%20and%20the%20Caribbean.pdf) que en países como El Salvador la penetración de telefonía móvil en hogares agrícolas supera el 90%, pero el uso de apps avanzadas es mucho menor.
- **Baja alfabetización digital** para software administrativo (SaaS, ERPs, dashboards). [IICA](https://test-assets-opsaa.iica.int/storage/resource/2025/06/c06b2de58547bca98e896f509b111fdc.pdf) profundiza en que, además del acceso, persisten brechas de uso ligadas a educación, edad y tamaño de la explotación.
- El dato operativo compite con la tarea física: si registrar algo toma más de **30 segundos**, simplemente **no se registra**.

> **Evidencia HCI**: La literatura en factores humanos aplicada a agricultura muestra que interfaces gráficas estándar son poco compatibles con las condiciones reales de trabajo en campo. Sistemas que exigen navegar múltiples pantallas bajo condiciones adversas tienden a ser abandonados ([Scott et al., 2018](https://hcioutdoors.net/wp-content/uploads/2018/03/Scott-interfaces-farm-animals.pdf); [Devitt, 2021](https://arxiv.org/abs/2111.14092)).

### Restricción Crítica  
> *"Si registrar un dato me quita más tiempo que hacer la tarea, el dato muere — aunque sea importante."*

---

## 🔄 Flujo Actual del Problema

El flujo de información actual es **asíncrono, manual y con altas pérdidas** en cada paso:

```
┌───────────────────────────────────────────────────────────────────┐
│                     FLUJO ACTUAL (Con Fricción)                        │
│                                                                         │
│  ① EVENTO          ② CAPTURA           ③ LATENCIA                      │
│  ┌──────────┐      ┌──────────────┐     ┌──────────────┐               │
│  │ Trabajador│─────▶│ Libreta /    │────▶│ Datos quedan │               │
│  │ observa o │      │ Formato Excel│     │ "atrapados"  │               │
│  │ ejecuta   │      │ Audio WA     │     │ 3-7 días     │               │
│  └──────────┘      └──────────────┘     └──────┼───────┘               │
│                                                  │                      │
│  ⑤ DECISIÓN        ④ TRANSCRIPCIÓN              │                      │
│  ┌──────────┐      ┌──────────────┐              │                      │
│  │ Gerente   │◀────│ Trabajador   │◀─────────────┘                      │
│  │ aprueba   │      │ pasa datos a │                                     │
│  │ o visita  │      │ Excel/PPT    │                                     │
│  │ campo     │      │ (½ jornada)  │                                     │
│  └──────────┘      └──────────────┘                                     │
│                                                                         │
│  ⚠️ Pérdida de datos en cada transición                                │
│  ⚠️ Decisiones con información obsoleta                                │
└───────────────────────────────────────────────────────────────────┘
```

### Los 5 pasos del flujo actual:

| # | Paso | Qué ocurre | Problema |
|---|---|---|---|
| ① | **Evento en campo** | El trabajador observa una anomalía ("Mancha roja en lote 4") o ejecuta una acción ("Aplicación de 20 sacos de urea") | El dato existe solo en la observación humana |
| ② | **Captura con fricción** | Anota en libreta o en notas de su celular, llena un formato de Excel impreso, o envía audio o texto informal ("Oigan, pilas con el lote 4 que está lleno de cochinilla") | Dato no estructurado o semi-estructurado, sin metadatos confiables |
| ③ | **Latencia** | Los datos quedan atrapados en papel, formatos Excel o historial de chat durante 3-7 días | Información perecedera se vuelve obsoleta |
| ④ | **Transcripción manual** | Un trabajador que aprendió a usar Excel pierde media jornada digitalizando datos y reportes en Excel/PowerPoint | Errores de digitación, reportes estáticos |
| ⑤ | **Decisión tardía** | El jefe o gerente aprueba después de revisar los datos o tras una visita a campo, donde frecuentemente se encuentra con realidades distintas a lo reportado en los datos | Impacto irreversible en rendimiento del cultivo; brecha entre dato reportado y realidad |

---

## 🤖 Statement AI-First

> **En lugar de construir una interfaz gráfica (GUI) y forzar al humano a estructurar los datos para la máquina, proponemos una arquitectura donde la IA actúa como el "Agente Estructurador Inteligente" — la interfaz primaria de ingestión de datos.**

### El Rol de la IA

La IA **no es** una herramienta de análisis posterior (un dashboard con gráficas). La IA **es** la interfaz de ingestión activa. Actúa como un **traductor semántico en tiempo real** ubicado entre el usuario y la base de datos.

```
┌───────────────────────────────────────────────────────────────────┐
│                     FLUJO AI-FIRST (Propuesto)                         │
│                                                                         │
│  ① EVENTO          ② CAPTURA NATURAL   ③ IA ESTRUCTURA                │
│  ┌──────────┐      ┌──────────────┐     ┌──────────────┐               │
│  │ Trabajador│─────▶│ Habla, toma  │────▶│ IA interpreta│               │
│  │ observa o │      │ foto, o      │     │ voz + imagen │               │
│  │ ejecuta   │      │ escribe WA   │     │ + texto      │               │
│  └──────────┘      └──────────────┘     └──────┼───────┘               │
│                           ▲                     │                       │
│                           │ Loop activo         │                       │
│                           │ "¿En qué lote?"     │                       │
│  ⑤ DECISIÓN        ④ DATO LISTO                │                       │
│  ┌──────────┐      ┌──────────────┐             │                       │
│  │ Gerente   │◀────│ JSON válido  │◀────────────┘                       │
│  │ decide    │      │ en base de   │                                     │
│  │ EN TIEMPO │      │ datos (seg)  │                                     │
│  │ REAL      │      │              │                                     │
│  └──────────┘      └──────────────┘                                     │
│                                                                         │
│  ✅ Cero pérdida de datos                                              │
│  ✅ Decisiones con información en tiempo real                          │
└───────────────────────────────────────────────────────────────────┘
```

### Capacidades Agénticas Requeridas

| Capacidad | Descripción | Por qué es necesaria |
|---|---|---|
| **Entendimiento Multimodal** | Interpretar lenguaje natural caótico (voz con jerga local), imágenes no estandarizadas (fotos de libretas, de plagas), y contexto temporal/espacial | El campo produce datos en formatos impredecibles |
| **Estructuración Autónoma** | Convertir inputs narrativos no estructurados en entidades de base de datos rígidas (JSON) sin formularios | Eliminar la fricción es el objetivo central |
| **Loop Humano Activo** | Si la información es ambigua, la IA tiene la agencia para "preguntar de vuelta" en el momento exacto (ej. "¿En qué lote viste la cochinilla?") | Asegurar integridad del dato sin fricción |
| **Conciencia Agro-contextual** | Saber que si se fumigó y luego llovió, hay que preguntar si re-aplicaron. Entender que "bombada" es una unidad de medida real | Sin contexto de dominio, la IA es inútil |

### Lo que el Statement AI-First **NO** propone

- ❌ No propone una solución terminada
- ❌ No define la tecnología específica
- ❌ No reemplaza al humano en la decisión
- ✅ **Sí define** que la IA debe ser un actor primario (no un feature), actuando como la interfaz entre el humano y el dato

---

## 🔬 Evidencia de Exploración

Este problema fue identificado y validado a través de la construcción iterativa de **Wasagro**, un sistema operativo para campo agrícola. Durante el desarrollo, se verificó que:

1. **El canal natural es WhatsApp**: Los usuarios ya envían audios, fotos y textos por WhatsApp para coordinarse. La IA debe interceptar ese flujo existente, no crear uno nuevo.
   - *Validación externa*: [IICA, FAO, CEPAL y RELASER](https://repositorio.iica.int/items/ebd41cc2-25ab-42af-8fa5-ecb1dc5c6265) documentan que WhatsApp se ha convertido en el canal dominante de extensión agrícola en ALC. [CGIAR publicó una guía](https://cgspace.cgiar.org/items/fad1f276-fb9c-4481-a4ca-7a43a4c39025) específica para uso de WhatsApp con productores en Honduras. [CIMMYT reporta](https://idp.cimmyt.org/productores-de-coahuila-usan-whatsapp-para-capacitarse-y-organizarse/) que productores en México migraron a grupos de WhatsApp como su canal principal.

2. **La jerga local es crítica**: Términos como "bombadas", "canecas", "quintales", "al trato", "destajo" no existen en ningún ERP estándar. La IA debe hablar el idioma del campo.

3. **La calidad del input es impredecible**: Fotos borrosas, audios con ruido de maquinaria, textos con errores tipográficos. La IA necesita una "barrera de calidad" y capacidad de pedir re-envío.
   - *Validación externa*: [Farmer.Chat (arXiv)](https://arxiv.org/html/2409.08916v2) y [KissanAI (UNDP)](https://github.com/undpindia/KissanAI_CRA_Chatbot) documentan capacidades para procesar texto, audios e imágenes para usuarios con baja alfabetización digital.

4. **El dato tiene vida útil corta**: Una plaga reportada 5 días después ya causó daño irreversible. La latencia del flujo actual destruye el valor de la información.
   - *Validación externa*: Estudios estiman [pérdidas globales de 20-40% por plagas](https://efraproject.eu/enhancing-crop-protection-a-deep-dive-into-yield-threats-precision-pest-management/), y hay [evidencia directa](https://www.frontiersin.org/journals/environmental-science/articles/10.3389/fenvs.2022.896385/full) de que retrasos en el control de plagas amplifican significativamente el daño. [Investigaciones recientes](https://pubmed.ncbi.nlm.nih.gov/40914792/) muestran que alertas tempranas de plagas se asocian con mejor rendimiento en fincas africanas.

5. **Los roles determinan acceso**: Un trabajador solo reporta; un gerente consulta y decide. La IA debe adaptar su comportamiento según el usuario.

---

## 🧪 Metodologías Aplicadas

| Metodología | Cómo se aplicó |
|---|---|
| **Problem Discovery (Lean)** | Iteración directa con jefes de campo en fincas de banano/cacao. Descubrimiento del problema a través de entrevistas y observación, no suposiciones |
| **Observación Directa** | Observación del flujo real: libreta → audio WA → Excel semanal. Medición de la latencia real (3-7 días promedio) |
| **Pensamiento AI-First** | Diseño del rol de la IA como actor primario desde el día 1. La IA no es un "feature" que se agrega después — es la arquitectura base |

> *Alineamiento metodológico*: [IICA y CEPAL](https://test-assets-opsaa.iica.int/storage/resource/2025/06/c06b2de58547bca98e896f509b111fdc.pdf) insisten en que soluciones de agricultura digital deben diseñarse a partir de necesidades reales con co-diseño en campo. La [literatura de smart farming](https://airjournal.org/ajase/journal_article/enhancing-agricultural-productivity-the-impact-of-safety-management-and-human-factors-in-smart-farming-systems/) enfatiza que el diseño centrado en el usuario es tan importante como la tecnología.

---

## 🚀 Deploy

Este repositorio incluye una **página interactiva** que visualiza el flujo del problema y el statement AI-first.

### Ver Online
👉 [Deploy en Vercel](https://wasagro-makers.vercel.app)

### Correr Localmente
```bash
# Clonar el repositorio
git clone https://github.com/Agrow7-code/Wasagro-makers.git
cd Wasagro-makers

# Abrir en navegador (es un sitio estático)
# Opción 1: Doble click en index.html
# Opción 2: Usar un servidor local
npx serve .
```

---

## 📚 Referencias

Fuentes institucionales, académicas y casos de uso que respaldan las afirmaciones de este documento:

### Brecha digital y datos en agricultura (ALC)
| Fuente | Descripción |
|---|---|
| [CEPAL — Digitalización en el sector agrícola en ALC](https://agriculturadigital.cepal.org/sites/default/files/2024-08/Digitalization%20in%20the%20agricultural%20sector%20in%20Latin%20America%20and%20the%20Caribbean.pdf) | Penetración de móviles vs. uso efectivo de soluciones digitales en hogares agrícolas |
| [CEPAL — TIC y brecha digital en agricultura (Nagel)](https://observatorioecuadordigital.mintel.gob.ec/wp-content/uploads/2022/11/S2013050_en_compressed.pdf) | Rezago del sector rural en incorporación de TIC; brechas de acceso, uso y adopción |
| [FAO — Farm data management, sharing and services](https://openknowledge.fao.org/server/api/core/bitstreams/7043933b-dd27-4674-92ec-4bbfef8a4d48/content) | Registros en papel y Excel como norma; errores y retrasos en gestión de datos |
| [Embrapa — Drivers and Barriers to Digital Agriculture (ALC)](https://www.alice.cnptia.embrapa.br/alice/bitstream/doc/1175490/1/AP-Drivers-and-Barriers-2025.pdf) | Baja alfabetización digital, interfaces inadecuadas y costos como barreras |
| [IICA — Reducción de brecha digital rural (ALC)](https://test-assets-opsaa.iica.int/storage/resource/2025/06/c06b2de58547bca98e896f509b111fdc.pdf) | Brecha de uso y adopción más allá del acceso |

### WhatsApp como canal de extensión agrícola
| Fuente | Descripción |
|---|---|
| [IICA/FAO/CEPAL — Seminario WhatsApp en extensión agrícola](https://repositorio.iica.int/items/ebd41cc2-25ab-42af-8fa5-ecb1dc5c6265) | WhatsApp como canal principal de extensión post-pandemia en ALC |
| [CGIAR — Guía de WhatsApp con productores (Honduras)](https://cgspace.cgiar.org/items/fad1f276-fb9c-4481-a4ca-7a43a4c39025) | Guía para transmitir información técnica a productores vía WhatsApp |
| [CIMMYT — Productores de Coahuila usan WhatsApp](https://idp.cimmyt.org/productores-de-coahuila-usan-whatsapp-para-capacitarse-y-organizarse/) | Caso real de migración a WhatsApp para capacitación y coordinación |
| [Ahire et al. — Role of WhatsApp in Agricultural Technology Transfer](http://rdmodernresearch.org/?edmc=4536) | Productores perciben WhatsApp como canal importante para información técnica |

### Cuadernos de campo digitales y FMIS
| Fuente | Descripción |
|---|---|
| [BrioAgro — FarmLog (cuaderno de campo por WhatsApp)](https://brioagro.com/es/farmlog-el-primer-cuaderno-de-campo-por-whatsapp-que-facilita-la-vida-a-los-agricultores/) | Primer cuaderno de campo digital operado por WhatsApp |
| [Cuaderno Campo Digital — Versión Escáner + IA](https://www.cuadernocampodigital.com/version-escaner-app-movil/) | IA para captura automática desde imágenes/PDFs |
| [Tupl — Digital Field Journal via WhatsApp + AI](https://www.tupl.com/solutions/digital-field-journal/) | Chatbot que estructura registros de campo desde WhatsApp |
| [FarmFit/GIZ — FMIS Guide](https://farmfitinsightshub.org/resources/farm-management-information-systems-fmis) | Migración de papel a digital: eficiencia vs. complejidad de adopción |

### IA y chatbots agrícolas multimodales
| Fuente | Descripción |
|---|---|
| [UNDP/KissanAI — WhatsApp Advisory Chatbot](https://github.com/undpindia/KissanAI_CRA_Chatbot) | Chatbot multilingüe para agricultura climáticamente resiliente |
| [Farmer.Chat (arXiv)](https://arxiv.org/html/2409.08916v2) | RAG multimodal para asesoría agrícola personalizada |
| [Good Agriculture — Field Notes to Farm Data](https://goodagriculture.com/2025/02/11/from-field-notes-to-farm-data-speaking-your-way-to-better-records/) | Conversión de notas de voz a datos organizados |
| [Microsoft — Data Tech's Agricultural Revolution](https://www.youtube.com/watch?v=R81HXrzSUc4) | IA multimodal para datos agrícolas dispersos |

### Factores humanos y HCI en agricultura
| Fuente | Descripción |
|---|---|
| [Scott et al. — Interfaces in Outdoor Computing Contexts](https://hcioutdoors.net/wp-content/uploads/2018/03/Scott-interfaces-farm-animals.pdf) | Incompatibilidad de pantallas táctiles con guantes, suciedad, clima |
| [Devitt — Cognitive factors in autonomous agriculture adoption](https://arxiv.org/abs/2111.14092) | Abandono de sistemas por sobrecarga cognitiva/operativa |
| [Smart Farming and Human Factors](https://airjournal.org/ajase/journal_article/enhancing-agricultural-productivity-the-impact-of-safety-management-and-human-factors-in-smart-farming-systems/) | Diseño centrado en usuario como factor crítico de éxito |

### Plagas, latencia y valor del dato fresco
| Fuente | Descripción |
|---|---|
| [FAO/AGRIVI — Crop Protection & Precision Pest Management](https://efraproject.eu/enhancing-crop-protection-a-deep-dive-into-yield-threats-precision-pest-management/) | Pérdidas globales de 20-40% por plagas |
| [Frontiers — Pest Control Delay effects](https://www.frontiersin.org/journals/environmental-science/articles/10.3389/fenvs.2022.896385/full) | Impacto negativo de retrasos en control de plagas |
| [Pest Management Science — Pest alerts and farm performance](https://pubmed.ncbi.nlm.nih.gov/40914792/) | Alertas tempranas = mejor rendimiento en fincas |

---

## 📄 Semana 2: Problema Validado + Usuario Claro

### Usuario Objetivo

**Perfil primario: Jefe de Campo / Administrador de Finca**

| Atributo | Descripción |
|---|---|
| **Quién es** | Responsable de coordinar labores diarias, registrar datos y reportar al dueño o cooperativa |
| **Edad** | 30-55 años |
| **Contexto** | Fincas bananeras, cacaoteras y cafetaleras en Ecuador y Guatemala |
| **Tecnología** | Usa WhatsApp diariamente. Celular Android gama media-baja |
| **Dolor** | Registrar datos es tedioso (papel → calculadora → Excel), propenso a errores y se hace tarde |

**Perfil secundario: Dueño / Gerente de Finca**

| Atributo | Descripción |
|---|---|
| **Quién es** | Productor que toma decisiones con datos que él no recolecta directamente |
| **Dolor** | Recibe resúmenes tardíos, incompletos o maquillados. No confía en la información |

> **Hipótesis de usuario**: El jefe de campo ya usa WhatsApp para comunicar lo que pasa en la finca. Si la IA captura y verifica esa información *desde ahí*, sin cambiar su herramienta, la adopción sería natural.

### Evidencia de Validación (6 Entrevistas)

| # | Nombre | Perfil | País | Cultivo |
|---|---|---|---|---|
| 1 | [Leonidas Estrada](entrevistas/leonidas_estrada.md) | Director AGROBAN (asociación bananera) | Ecuador | Banano |
| 2 | [William Molina](entrevistas/william_molina.md) | Técnico cadena de valor cacao (FEPP) | Ecuador | Cacao |
| 3 | [Jorge Mario Rivera](entrevistas/jorge_mario_rivera.md) | Encargado de Finca | Guatemala | Varios |
| 4 | [Víctor Rivera](entrevistas/victor_rivera.md) | Dueño de finca | Guatemala | Varios |
| 5 | [Bolívar Arias](entrevistas/bolivar_arias.md) | Dueño de finca bananera | Ecuador | Banano |
| 6 | [Washington "Wacho"](entrevistas/washington_wacho.md) | Trabajador de campo (mano derecha de Bolívar Arias) | Ecuador | Banano |

#### Hallazgos clave

**El flujo de datos es manual, lento y frágil**
> *"El fitosanitario recorre el campo, llena el formulario a mano, se sienta en la oficina, hace sus cálculos a la antigua en una calculadora, llena su Excel..."*
— Leonidas Estrada, AGROBAN

**El cuello de botella es el trabajador, no el productor**
> *"El productor puede tener la iniciativa de adoptar tecnología, pero si el trabajador no, allá viene ese cuello de botella."*
— Leonidas Estrada, AGROBAN

**WhatsApp ya es el canal natural**
> *"Si por medio de WhatsApp, ¿crees que te sería útil?" — "Sí, claro que sería importante."*
— Washington "Wacho", trabajador de campo

**No hay registro formal en campo**
> *"Registro no... uno simplemente conversa con el jefe, dialogar con él y ponerse de acuerdo."*
— Washington "Wacho", trabajador de campo

**Los datos se "maquillan" para auditorías**
> *"Si encuentra errores, ya es tarde para corregir en campo. Se maquilla el dato para la auditoría."*
— Observación validada por múltiples entrevistados

**El dueño quiere resúmenes, no data cruda**
> *"No es que me voy a poner a leer todos los chats desde el lunes... sino que de repente, pum, al final de la semana me tira un resumen."*
— Leonidas Estrada, AGROBAN

**ROI debe ser rápido**
> *"El productor bananero es súper pesetero... si yo voy a gastarme $10, ojalá el retorno sea en un mes."*
— Leonidas Estrada, AGROBAN

### Flujos Validados (Ajustes vs. Semana 1)

Las entrevistas revelaron que NO hay un solo flujo, sino **3 realidades coexistentes** en la misma finca:

**Escenario A — Informal (WhatsApp/voz, sin registro)** *(menos frecuente)*
```
Trabajador hace la labor → Le dice al jefe por audio o cara a cara
→ Información queda en la memoria o en el historial de chat → Se pierde
```

**Escenario B — Semi-formal (formularios impresos → Excel)** *(muy común)*
```
Trabajador llena formulario impreso en campo
→ El mismo trabajador o jefe pasa los datos a Excel
→ Errores de transcripción, datos incompletos, retrasos
```

**Escenario C — Digital (app de gestión existente)**
```
Técnico usa app en tablet/celular (ej. auditoría Sigatoka, control de cosecha)
→ Datos suben cuando hay Wi-Fi → Funciona en empacadora y en campo
→ Adopción limitada a labores específicas donde el productor invirtió
```

> Los 3 escenarios **pueden coexistir** dentro de una misma finca. Hay fincas que mantienen todo en papel todavía, otras que combinan papel con apps, y algunas con mayor adopción digital.

| Aspecto | Semana 1 (hipótesis) | Semana 2 (validado) |
|---|---|---|
| Canal de datos | Papel y cuadernos | WhatsApp ya es el canal principal |
| Quién captura | Jefe de campo | Combinación trabajador → jefe |
| Frecuencia del dolor | Semanal | **Diario** |
| Barrera principal | Falta de apps | Falta de apps **fáciles para el trabajador** |

### Flujo AI-First Mejorado (Semana 2)

El flujo propuesto en Semana 1 se **mantiene en su esencia** (la IA como interfaz primaria), pero las entrevistas revelaron un **conflicto central** y varias correcciones:

#### El conflicto: ¿Quién captura el dato?

Las entrevistas muestran que **no hay un solo punto de captura**, sino dos caminos reales:

| Ruta | Cómo funciona hoy | Problema |
|---|---|---|
| **Ruta A: Indirecta** (trabajador → jefe → sistema) | El trabajador ejecuta y le cuenta al jefe por voz, cara a cara, o audio de WA. El jefe interpreta y reporta | **Interferencia en la cadena**: el jefe decodifica lo que el trabajador dijo, puede haber pérdida o distorsión de información |
| **Ruta B: Directa** (jefe recorre y captura) | El jefe camina por las zonas, observa directamente, y toma datos él mismo (en app, papel impreso o hoja en blanco) | Más preciso, pero el jefe no puede estar en todos los lotes al mismo tiempo |

> **Pregunta clave**: Si el trabajador pudiera reportar directo a Wasagro (vía WhatsApp), ¿cómo nos aseguramos de que los datos sean correctos?

#### Estrategia de calidad: IA como validador de múltiples fuentes

Wasagro no elige una sola ruta — **acepta ambas** y usa la IA para cruzar y verificar:

| Mecanismo | Cómo funciona |
|---|---|
| **Validación cruzada** | Si el trabajador reporta "apliqué 20L en lote 3" y el jefe reporta "se aplicó en lote 3", la IA confirma. Si hay discrepancia, pregunta |
| **Reglas agronómicas** | La IA compara lo reportado contra la ontología: ¿esa dosis es posible para ese producto en esa hectárea? Si no, alerta |
| **Evidencia fotográfica** | Pedir foto del insumo, del lote, o de la labor ejecutada como prueba complementaria |
| **Contexto histórico** | Si el lote 3 fue fumigado hace 2 días con el mismo producto, la IA detecta la anomalía |
| **Preguntas de confirmación** | Ante datos ambiguos, la IA pregunta de vuelta: "¿En qué lote?", "¿Cuántos litros exactamente?" |

#### Flujo mejorado con doble ruta de captura

```
┌─────────────────────────────────────────────────────────────────────────────┐
│            FLUJO AI-FIRST MEJORADO (Validado Semana 2)                      │
│                                                                             │
│  ① CAMPO                                     ③ IA AGREGA + VERIFICA       │
│                                                                             │
│  RUTA A (indirecta):                         ┌──────────────────┐          │
│  ┌──────────┐         ┌──────────────┐       │ Buffer 15 seg    │          │
│  │ Trabajador│──voz──▶│ Jefe de campo│──WA──▶│ (agrega msgs     │          │
│  │ ejecuta   │──cara──▶│ interpreta   │       │  fragmentados)   │          │
│  └──────────┘         └──────┬───────┘       └───────┬──────────┘          │
│                              │                       │                      │
│  RUTA B (directa):           │                       ▼                      │
│  ┌──────────────┐            │               ┌──────────────────┐          │
│  │ Jefe recorre  │───────WA──┘               │ IA INTERPRETA    │          │
│  │ campo y toma  │                           │ voz + foto +     │          │
│  │ datos directo │                           │ texto + contexto │          │
│  └──────────────┘                            └───────┬──────────┘          │
│                                                      │                      │
│  RUTA C (futura):                                    ▼                      │
│  ┌──────────────┐                            ┌──────────────────┐          │
│  │ Trabajador    │────────WA directo─────────▶│ IA VERIFICA      │          │
│  │ reporta       │                           │ ¿Dosis correcta? │          │
│  │ a Wasagro     │             Loop activo   │ ¿Producto legal? │          │
│  └──────────────┘             "¿En qué       │ ¿Dato coherente? │          │
│                                lote fue?"    │ ¿Cruza con lo    │          │
│                              ◀───────────────│  que dijo el     │          │
│                                              │  jefe?           │          │
│                                              └───────┬──────────┘          │
│                                                      │                      │
│  ⑤ ENTREGA ESCALONADA        ④ DATO VERIFICADO      │                      │
│  ┌──────────────────┐        ┌──────────────┐        │                      │
│  │ Dueño / Gerente   │◀──────│ Dato limpio  │◀───────┘                      │
│  │                   │       │ verificado   │                               │
│  │ ⚡ DIARIO:        │       │ en base de   │                               │
│  │  Alertas críticas │       │ datos (seg)  │                               │
│  │  (plaga, error    │       └──────────────┘                               │
│  │   dosis, clima)   │                                                      │
│  │                   │                                                      │
│  │ 📊 SEMANAL:       │                                                      │
│  │  Resumen de       │                                                      │
│  │  operaciones,     │                                                      │
│  │  costos, avance   │                                                      │
│  └──────────────────┘                                                      │
│                                                                             │
│  ✅ Acepta datos de CUALQUIER ruta (trabajador o jefe)                     │
│  ✅ La IA cruza fuentes para detectar inconsistencias                      │
│  ✅ Alertas críticas llegan al dueño EL MISMO DÍA                         │
│  ✅ Resúmenes consolidados llegan cada semana                              │
└─────────────────────────────────────────────────────────────────────────────┘
```

#### Qué cambió vs. Semana 1

| Aspecto | Semana 1 | Semana 2 (mejorado) |
|---|---|---|
| **Quién captura** | Solo el trabajador | **Doble ruta**: jefe directo + trabajador vía jefe. Ruta futura: trabajador directo |
| **Riesgo de inferencia** | No contemplado | **Identificado**: cuando el trabajador le dice al jefe por voz, hay decodificación imperfecta. La IA cruza fuentes |
| **Qué hace la IA** | Estructura datos | **Estructura + verifica** contra reglas agronómicas + cruza fuentes |
| **Entrega al dueño** | Resumen semanal | **Escalonada**: alertas críticas diarias ⚡ + resúmenes semanales 📊 |
| **Agricultura de precisión** | No mencionada | Wasagro se adapta: acepta datos de múltiples fuentes (app, WA, foto) y los normaliza en un solo sistema verificado |

#### Conexión con Agricultura de Precisión

Wasagro no reemplaza apps de precisión que ya existen (ej. monitoreo Sigatoka), sino que actúa como **capa de integración verificada**:

- **Apps existentes** → datos entran por API directa
- **WhatsApp del jefe** → datos entran por IA + verificación
- **WhatsApp del trabajador** (futuro) → datos entran con doble verificación (IA + confirmación del jefe)
- **Resultado**: Un solo repositorio de datos limpios y verificados, sin importar la fuente

### Hipótesis Ajustadas (vs. Semana 1)

**Usuario Primario**

| Hipótesis (Semana 1) | Estado Semana 2 | Evidencia |
|---|---|---|
| Jefe de campo, 30-55 años, experiencia empírica | ✅ Validada | Perfil confirmado en las 9 entrevistas |
| Coordina entre 5 y 30 trabajadores | ✅ Validada | Wacho confirma: "somos 11 y nos dividimos a hacer las labores" |
| Usa WhatsApp nativamente (voz, fotos, texto) | ✅ Validada | Todos los entrevistados usan WhatsApp como canal principal |
| No sabe usar apps administrativas complejas | ⚠️ Ajustada | Algunos jefes SÍ usan apps específicas (ej. Sigatoka), pero solo si el productor invierte en capacitación. La mayoría no |
| Motivación: ejecutar la operación, no documentarla | ✅ Validada | "Registro no... uno simplemente conversa con el jefe" — Wacho |

**Contexto Físico**

| Hipótesis (Semana 1) | Estado Semana 2 | Evidencia |
|---|---|---|
| Entorno al aire libre, conectividad intermitente | ✅ Validada | Fincas visitadas en Ecuador confirman zonas sin señal estable |
| Condiciones climáticas variables | ✅ Validada | Lluvia, sol directo, humedad — confirmado por contexto de entrevistas |
| Exigencia física: 5-15 km diarios recorriendo lotes | ✅ Validada | Wacho describe su rutina de recorrido desde las 6 AM |

**Contexto Tecnológico**

| Hipótesis (Semana 1) | Estado Semana 2 | Evidencia |
|---|---|---|
| Alta penetración smartphones Android gama media-baja | ✅ Validada | Confirmado; problema adicional: robo de celulares — Leonidas Estrada |
| Baja alfabetización digital para SaaS/ERPs | ✅ Validada | "El trabajador: esa pendejada no sirve, se demora mucho" — Leonidas Estrada |
| Si registrar toma >30 seg, el dato no se registra | ✅ Validada | Confirmado en múltiples entrevistas: la tarea física siempre gana |

**Hipótesis adicionales descubiertas en validación**

| Hipótesis nueva (Semana 2) | Evidencia |
|---|---|
| El servicio post-venta y capacitación determinan la adopción más que la tecnología en sí | "Si das buen servicio, lo capacitas bien, el técnico se da cuenta que le facilita la vida" — Leonidas Estrada |
| El ROI debe ser visible en menos de 30 días | "El productor es súper pesetero... ojalá el retorno sea en un mes" — Leonidas Estrada |
| La seguridad física del dispositivo es una barrera real | "Escóndelo porque si estás en la parada del bus te van a robar" — Leonidas Estrada |
| "Necesitamos una app nueva" | ❌ Descartada — Apps nuevas fracasan por fricción de adopción. WhatsApp ES la interfaz |
| El dato no solo se pierde en papel | ⚠️ Ajustada — También se pierde en audios y chats informales que nadie procesa |

### Registro de Aprendizajes y Decisiones (AI-Light)

#### Aprendizajes clave hasta ahora

1. **El problema central no es "no hay software"**, es que el costo cognitivo de registrar datos es demasiado alto. Hay apps, hay ERPs, hay formularios — pero si registrar un dato toma más de 30 segundos en medio de una jornada física, ese dato muere.

2. **WhatsApp no es solo un canal de comunicación: es el sistema operativo informal de la finca.** Ahí se coordinan labores, se reportan problemas, se envían fotos de plagas y se piden insumos. Cualquier solución que ignore esto y pida instalar una app nueva está condenada.

3. **El dato operativo tiene vida útil muy corta.** Una plaga detectada hoy y reportada en 5 días ya causó daño irreversible. Un error de dosis descubierto al final de la semana ya contaminó el lote. La latencia actual de 3–7 días destruye el valor de la información.

4. **El usuario castiga el mínimo error.** Si la IA inventa un dato, sugiere una dosis incorrecta, o malinterpreta un audio una sola vez, el jefe de campo la rechaza. "Esa pendejada no sirve". Esto nos llevó a pensar en verificación rigurosa y validación contra reglas agronómicas, no solo en prompts bonitos.

5. **El conflicto de quién captura los datos es real.** Cuando el trabajador le dice al jefe por voz, hay interferencia y decodificación imperfecta. Cuando el jefe captura directo, no puede cubrir todos los lotes. La IA debe aceptar ambas rutas y cruzar fuentes.

#### Decisiones tomadas

1. **No construiremos primero un dashboard** — Construiremos primero la capa de ingestión AI-First vía WhatsApp. El dashboard es una consecuencia, no el producto.

2. **No pediremos al usuario que estructure datos en formularios** — La IA será el agente estructurador que interpreta lo que el jefe ya envía (audios, fotos, textos informales) y pregunta solo lo indispensable.

3. **Verificación > Digitación** — El valor real no es transcribir audios a texto; es verificar que lo que dicen es agronómicamente correcto antes de que entre al sistema.

4. **WhatsApp como interfaz única** — No app nueva. Interceptar la comunicación que ya existe.

5. **El trabajador NO es el usuario directo** — El jefe interactúa con el sistema; el trabajador le reporta al jefe como siempre.

6. **ROI demostrable en 30 días** — Pitch: "Ya no tienes que sentarte el viernes a pasar datos al Excel."

7. **Métricas de éxito centradas en captura y precisión**, no en "número de features". Lo que importa: ¿cuántos datos se capturaron?, ¿cuántos pasaron verificación?, ¿cuánto se redujo la latencia?

---

> *Construido como parte del programa **Maker Fellowship — AI-Native** 🚀*
