# Troubleshooting

## Max Iterations Reached

Cause:
The discovery agent is exploring too many tables.

Resolution:
- Restrict table selection in the prompt.
- Keep Max Iterations at 5.
- Ensure clear stop conditions.

---

## Rate Limit Errors

Cause:
Excessive token usage from tool loops or large result sets.

Resolution:
- Use claude-3-haiku for discovery.
- Limit all queries to 50 rows.
- Reduce Max Output Tokens if needed.

---

## Invalid JSON Output

Cause:
Model deviating from required structure.

Resolution:
- Reinforce structured output instructions.
- Enable strict output formatting if available.
