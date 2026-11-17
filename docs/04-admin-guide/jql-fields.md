# JQL

The app publishes each work item's SLA values as indexed properties, so you can search them with JQL.

| Field | Type | Values |
|---|---|---|
| `slaState` | string | `ok`, `at_risk`, `breached`, `paused`, `met`, `missed` |
| `slaBreached` | string | `"true"` once a target is missed, including stopped misses that have no deadline |
| `slaDueAt` | date | deadline, sortable |
| `slaGoal` | text | SLA name |

```
slaState = "breached" AND statusCategory != Done ORDER BY slaDueAt ASC
slaState = "at_risk" AND assignee = currentUser()
slaDueAt <= endOfDay() AND statusCategory != Done
slaGoal ~ "resolution"
```

> **Tip:** To match the **Breached** count on the project page, use `slaState = "breached"`. `slaBreached = "true"` also returns work items whose timer already stopped as Missed. Those have no `slaDueAt`, so they sort first in `ORDER BY slaDueAt ASC`.

> **Warning:** Field names are camelCase. Searching "SLA state" matches nothing.

> **Note:** JQL catches up within a few minutes; the app's own screens are live. The admin **JQL** tab shows when values were last published (*Published 2 min ago · 0 waiting*) with a **Publish now** button, ready-made queries with **Open in search**, and the field list under **Fields you can use**. Time left is not indexed because it goes stale; sort by `slaDueAt` instead.

---
[Back to home](../README.md) · Support: info@berkly.nl

