# Integrations and automation

| Integration | How |
|---|---|
| JQL, filters, boards, dashboards | Indexed fields `slaState`, `slaBreached`, `slaDueAt`, `slaGoal`. See [JQL](../04-admin-guide/jql-fields.md). |
| Jira Automation | **Check SLA timer (breach / at risk)** action, listed under *Other apps* at the bottom of the action search (returns state, breached, time left as smart values), plus the JQL fields in scheduled rules. There is no SLA trigger: Forge apps can't add one. See [recipes](../05-use-cases/automation-rules.md). |
| Comment and label on a missed target | Optional per project; the label can drive filters and automation. |
| Spreadsheets | **Export CSV** on All timers. |

> **Note:** There is no built-in Slack, email or webhook integration. That is deliberate: the app makes no outside calls.

---
[Back to home](../README.md) · Support: info@berkly.nl

