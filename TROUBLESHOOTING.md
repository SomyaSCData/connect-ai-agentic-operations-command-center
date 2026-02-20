# Troubleshooting

## Max Iterations Reached

Cause:
Agent is exploring too many tables.

Solution:
- Restrict schema exploration to relevant table names.
- Ensure prompt includes strict stop conditions.
- Keep Max Iterations at 5.

---

## Rate Limit Errors

Cause:
Excessive token usage due to tool loops or large result sets.

Solution:
- Use claude-3-haiku for retrieval.
- Limit query results to 50 rows.
- Reduce Max Output Tokens.

---

## Invalid JSON Output

Cause:
Model drift or formatting deviation.

Solution:
- Use strict output format instructions.
- Enable "Require Specific Output Format" if needed.
