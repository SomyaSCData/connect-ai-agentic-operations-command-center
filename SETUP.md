# Setup Guide

## Step 1 – Import Workflow

Import:
operations-command-center-agentic.json

---

## Step 2 – Configure Credentials

- MCP Header Authentication
- Anthropic API key
- Gmail credentials (optional)

---

## Step 3 – Validate Execution

Run the workflow manually.

Confirm:

- Discovery Agent completes within 5 iterations.
- Risk Analysis Agent outputs valid structured JSON.
- Severity Gate filters NORMAL conditions.
- Email alert triggers only when required.
