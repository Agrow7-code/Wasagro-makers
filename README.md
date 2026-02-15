# 🌱 Fricción de Captura: La Última Milla de Datos Agrícola

> **Maker Fellowship — AI-Native · Reto Producto**
> Definición de problema real + Statement AI-First

---

## 📋 Tabla de Contenidos

- [El Problema](#-el-problema)
- [Hipótesis de Usuario y Contexto](#-hipótesis-de-usuario-y-contexto)
- [Flujo Actual del Problema](#-flujo-actual-del-problema)
- [Statement AI-First](#-statement-ai-first)
- [Evidencia de Exploración](#-evidencia-de-exploración)
- [Metodologías Aplicadas](#-metodologías-aplicadas)
- [Deploy](#-deploy)

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
- **Alta penetración de smartphones** (Android de gama media-baja) y uso nativo de WhatsApp como canal de coordinación.
- **Baja alfabetización digital** para software administrativo (SaaS, ERPs, dashboards).
- El dato operativo compite con la tarea física: si registrar algo toma más de **30 segundos**, simplemente **no se registra**.

### Restricción Crítica  
> *"Si registrar un dato me quita más tiempo que hacer la tarea, el dato muere — aunque sea importante."*

---

## 🔄 Flujo Actual del Problema

El flujo de información actual es **asíncrono, manual y con altas pérdidas** en cada paso:

```
┌─────────────────────────────────────────────────────────────────────────┐
│                     FLUJO ACTUAL (Con Fricción)                        │
│                                                                         │
│  ① EVENTO          ② CAPTURA           ③ LATENCIA                      │
│  ┌──────────┐      ┌──────────────┐     ┌──────────────┐               │
│  │ Trabajador│─────▶│ Libreta /    │────▶│ Datos quedan │               │
│  │ observa o │      │ Formato Excel│     │ "atrapados"  │               │
│  │ ejecuta   │      │ Audio WA     │     │ 3-7 días     │               │
│  └──────────┘      └──────────────┘     └──────┬───────┘               │
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
└─────────────────────────────────────────────────────────────────────────┘
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
┌─────────────────────────────────────────────────────────────────────────┐
│                     FLUJO AI-FIRST (Propuesto)                         │
│                                                                         │
│  ① EVENTO          ② CAPTURA NATURAL   ③ IA ESTRUCTURA                │
│  ┌──────────┐      ┌──────────────┐     ┌──────────────┐               │
│  │ Trabajador│─────▶│ Habla, toma  │────▶│ IA interpreta│               │
│  │ observa o │      │ foto, o      │     │ voz + imagen │               │
│  │ ejecuta   │      │ escribe WA   │     │ + texto      │               │
│  └──────────┘      └──────────────┘     └──────┬───────┘               │
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
└─────────────────────────────────────────────────────────────────────────┘
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

2. **La jerga local es crítica**: Términos como "bombadas", "canecas", "quintales", "al trato", "destajo" no existen en ningún ERP estándar. La IA debe hablar el idioma del campo.

3. **La calidad del input es impredecible**: Fotos borrosas, audios con ruido de maquinaria, textos con errores tipográficos. La IA necesita una "barrera de calidad" y capacidad de pedir re-envío.

4. **El dato tiene vida útil corta**: Una plaga reportada 5 días después ya causó daño irreversible. La latencia del flujo actual destruye el valor de la información.

5. **Los roles determinan acceso**: Un trabajador solo reporta; un gerente consulta y decide. La IA debe adaptar su comportamiento según el usuario.

---

## 🧪 Metodologías Aplicadas

| Metodología | Cómo se aplicó |
|---|---|
| **Problem Discovery (Lean)** | Iteración directa con jefes de campo en fincas de banano/cacao. Descubrimiento del problema a través de entrevistas y observación, no suposiciones |
| **Observación Directa** | Observación del flujo real: libreta → audio WA → Excel semanal. Medición de la latencia real (3-7 días promedio) |
| **Pensamiento AI-First** | Diseño del rol de la IA como actor primario desde el día 1. La IA no es un "feature" que se agrega después — es la arquitectura base |

---

## 🚀 Deploy

Este repositorio incluye una **página interactiva** que visualiza el flujo del problema y el statement AI-first.

### Ver Online
👉 [Deploy en Vercel](https://hidden-mare.vercel.app) *(disponible tras deploy)*

### Correr Localmente
```bash
# Clonar el repositorio
git clone https://github.com/[tu-usuario]/hidden-mare.git
cd hidden-mare

# Abrir en navegador (es un sitio estático)
# Opción 1: Doble click en index.html
# Opción 2: Usar un servidor local
npx serve .
```

---

## 📄 Licencia

MIT

---

> *Construido como parte del programa **Maker Fellowship — AI-Native** 🚀*
