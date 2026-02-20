# Architecture Overview

This workflow transitions from a deterministic ETL model to an agentic reasoning model.

---

## Design Principles

The previous architecture relied on:

- Hardcoded SQL queries
- JavaScript-based threshold logic
- Manual iteration and merging

The new architecture leverages:

- Tool-augmented agents
- Structured multi-agent flow
- Autonomous schema discovery
- Controlled reasoning boundaries

---

## Agent 1: Discovery & Retrieval

Capabilities:
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

---

## Agent 2: Risk Analysis

Input:
Structured operational metrics from Agent 1.

Responsibilities:
- Detect threshold breaches
- Identify anomalies
- Classify severity
- Provide quantitative evidence

Model:
claude-sonnet-4-5

---

## Agent 3: Executive Reporting

Input:
Structured risk classification from Agent 2.

Output:
- Executive summary
- Business impact explanation
- Recommended next steps

Model:
claude-sonnet-4-5
