# JQL filters

| Need | JQL |
|---|---|
| My at-risk work | `slaState = "at_risk" AND assignee = currentUser()` |
| Open breaches, most urgent first | `slaState = "breached" AND statusCategory != Done ORDER BY slaDueAt ASC` |
| Due today | `slaDueAt <= endOfDay() AND statusCategory != Done` |
| Resolution SLAs missed this month | `slaGoal ~ "resolution" AND slaState = "missed" AND resolved >= startOfMonth()` |
| Paused work | `slaState = "paused"` |

> **Tip:** Save each as a filter and share it with the team.

---
[Back to home](../README.md) · Support: info@berkly.nl

