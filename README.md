# 📘 Agent Suite — README.md

# 🚀 Agent Suite  
**Sistema modular de agentes de IA para análisis, auditoría y documentación automática.**

---

## ✨ Descripción General

**Agent Suite** es un monorepo compuesto por **tres agentes independientes**, cada uno instalable por separado y reutilizable en cualquier proyecto, además de una API FastAPI que los orquesta.

Los agentes permiten:

- Analizar datos y generar insights.  
- Auditar la calidad e integridad de bases de datos.  
- Documentar sistemas, carpetas y proyectos de forma automática.  
- Generar reportes ejecutivos, diagramas ER y diccionarios de datos.  
- Enviar salidas por email y Slack.  
- Detectar documentación faltante (BCM, riesgos, políticas, procedimientos).

---

# 🧠 Agentes Disponibles

## 1. 🟦 AnalystAgent (Analista Jr)
Agente orientado al análisis operativo:

- KPIs genéricos.  
- Comparativos simples.  
- Anomalías básicas.  
- Gráficos PNG.  
- Resúmenes ejecutivos.  
- Notificaciones por Slack y e‑mail.  
- Puede usar hallazgos del DataAuditAgent.

---

## 2. 🟧 DataAuditAgent (Auditor de Datos)
Agente especializado en calidad e integridad:

- Data profiling automático.  
- Detección de nulos, duplicados y outliers.  
- Registros huérfanos y FKs inconsistentes.  
- Contradicciones entre columnas.  
- Severidad, impacto y sugerencias correctivas.

---

## 3. 🟩 DocumentationAgent (Documentador Empresarial)
Agente avanzado para documentación técnica y funcional:

- Diagramas ER.  
- Diccionario de datos.  
- Documentación funcional inferida.  
- Análisis de carpetas (PDF, DOCX, MD, proyectos).  
- Detección de "gaps" (BCM, riesgos, políticas faltantes).  
- Exportación a **PDF / MD / HTML**.  
- Generación de documentación corporativa completa.

---

# 🏗️ Arquitectura General
FastAPI (apps/api)
│
├── AnalystAgent (packages/analyst-agent)
├── DataAuditAgent (packages/data-audit-agent)
└── DocumentationAgent (packages/documentation-agent)
│
└── Servicios Comunes (libs/*)
├── common-db (Postgres RO + guardrails SQL)
├── common-llm (wrapper universal para cualquier LLM)
├── common-vectorstore (Chroma / Pinecone)
├── common-tools (Slack, Gmail, Sheets, Jira)
└── common-utils (viz, telemetry, security)

---

# 📁 Estructura del Repositorio
agent-suite/
│
├─ apps/
│  └─ api/
│     ├─ app/
│     │  ├─ main.py
│     │  ├─ settings.py
│     │  ├─ auth.py
│     │  ├─ schemas.py
│     │  ├─ routers/
│     │  │  ├─ analyst_router.py
│     │  │  ├─ audit_router.py
│     │  │  └─ docs_router.py
│     │  └─ di.py
│     └─ pyproject.toml
│
├─ packages/
│  ├─ analyst-agent/
│  ├─ data-audit-agent/
│  └─ documentation-agent/
│
├─ libs/
│  ├─ common-db/
│  ├─ common-llm/
│  ├─ common-vectorstore/
│  ├─ common-tools/
│  └─ common-utils/
│
├─ fixtures/
│  └─ dummy_docs/
│
├─ infra/
│  └─ docker/
│     ├─ Dockerfile
│     └─ docker-compose.yml
│
├─ requirements.txt
├─ .env.example
└─ README.md

---

# 🛠️ Tecnologías Principales

- **FastAPI**  
- **PostgreSQL (read‑only)**  
- **SQLAlchemy + guardrails SQL**  
- **Python 3.11+**  
- **Docker / Docker Compose**  
- **ChromaDB** (vector store local)  
- **Slack SDK**  
- **Gmail API / SMTP**  
- **matplotlib / plotly**  
- **OpenTelemetry** (monitoreo)  
- **Wrapper universal para LLMs** (Gemini → GPT → Claude)

---

# 🔒 Seguridad

- Conexión **Postgres READ-ONLY**.  
- Rechazo de consultas **DML/DDL**.  
- `LIMIT` + `TIMEOUT` por defecto.  
- Solo **plantillas SQL whitelisted**.  
- Redacción de PII en logs.  
- Scopes por herramienta.  
- Tokens solo en `.env`.

