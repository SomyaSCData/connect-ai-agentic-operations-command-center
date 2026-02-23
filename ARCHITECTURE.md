# Architecture Overview

This workflow implements a structured, multi-agent operational monitoring system using n8n and CData Connect AI.

The architecture separates responsibilities across distinct stages to ensure clarity, scalability, and maintainability.

---

## Stage 1 – Discovery & Retrieval Agent

Purpose:
Explore available enterprise datasets and retrieve relevant operational metrics.

Tool Access:
- listTables
- getSchema
- queryData

Constraints:
- Maximum 4 tool calls
- Aggregated queries only
- LIMIT 50 enforced
- Stops once sufficient metrics are retrieved

Model:
claude-3-haiku

Output:
Structured JSON containing operational metrics.

---

## Stage 2 – Risk Analysis Agent

Purpose:
Evaluate operational metrics and identify risk conditions.

Responsibilities:
- Detect anomalies
- Identify threshold breaches
- Classify severity
- Provide quantitative evidence

Model:
claude-sonnet-4-5

Output:
Structured JSON:

{
  "risks": [...],
  "overall_severity": ""
}

---

## Stage 3 – Severity Gate

Purpose:
Prevent unnecessary alert generation.

Logic:
Proceed only if overall_severity is WARNING or CRITICAL.

---

## Stage 4 – Executive Reporting Agent

Purpose:
Generate executive-level summary and recommended actions.

Responsibilities:
- Summarize key risks
- Explain business impact
- Recommend next steps
- Maintain professional tone

Model:
claude-sonnet-4-5
