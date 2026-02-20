# Architecture

This workflow implements a structured multi-agent pipeline for operational monitoring.

Each stage has a clearly defined responsibility.

---

## Stage 1 – Discovery & Retrieval Agent

Purpose:
Explore enterprise datasets and retrieve operational metrics.

Capabilities:
- listTables
- getSchema
- queryData

Constraints:
- Maximum 4 tool calls
- Aggregated queries only
- LIMIT 50 enforced
- Stops once sufficient metrics are collected

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
Structured JSON with risk classifications and overall severity.

---

## Stage 3 – Severity Gate

Purpose:
Prevent unnecessary alerts.

Logic:
Only proceed if overall_severity is WARNING or CRITICAL.

---

## Stage 4 – Executive Reporting Agent

Purpose:
Generate executive-level report and recommended actions.

Responsibilities:
- Summarize risks
- Explain business impact
- Recommend next steps

Model:
claude-sonnet-4-5
