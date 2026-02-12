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
