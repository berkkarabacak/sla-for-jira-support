# Project settings

**Project settings → Apps → SLA**. Project admins can edit; everyone else sees a **View only** lozenge and disabled controls. **View timers** opens the project's SLA page.

| Tab | Use it to |
|---|---|
| SLAs | Add and edit the project's SLAs. |
| Working hours | Choose and edit the project's working hours. |
| Activity | See who paused, extended, excluded or measured again what, and why (kept 180 days). |

## SLAs
- **Measuring**: **Measuring SLAs** on or off, which **Working hours**, and **New work items only** (work items created before that date are not measured; see [Backfill](backfill.md)).
- One card per SLA: its name, target and rule (for example *Created → leaves To Do · All work types except sub-tasks · Never pauses*), with live counts and on time over 30 days. **Edit** it, or use **More** to **Duplicate** or **Remove** it.
- **When a target is missed**: **Comment and @mention the assignee**, **Add the label sla-breached**, and **Warn at** *n*% **left**, which turns a timer **At risk**.
- Changes wait in the save bar, which says how many work items match and how many would be overdue. **Discard** or **Save changes**.

A project without SLAs starts from preset cards or **Start from scratch**.

## Add SLA
**Add SLA** (or **Edit**) opens one dialog:

| Field | Meaning |
|---|---|
| Name | What your team calls it. |
| Measure | *Time to triage*, *Time to resolution*, *Cycle time* or *Time in review*. The line under it shows where the timer starts and stops. |
| While in | *Time in review* only: the statuses it runs in. |
| Target | Working time. A "day" is 24 working hours, which is three business days on a 9-to-5 week. For "1 business day", enter 8 hours. |
| Different target per priority | Optional, one row per priority; other priorities use the target. |
| Applies to | Work types. Empty means all work types except sub-tasks. |
| Pause in / Pause while flagged | Statuses, or the Jira flag, that pause the timer. |

The dialog's button reads **Add SLA** or **Update SLA**. Nothing is saved until **Save changes**.

> **Note:** Comments for missed targets are capped at 25 work items per 5-minute check, so turning on an SLA over a big backlog can't flood the project. The rest follow on the next checks.

> **Tip:** Renaming an SLA republishes `slaGoal` in JQL automatically.

## Working hours
Choose the project's working hours and edit them with the same editor as the admin page (see [Working hours](calendars.md)). A lozenge says whether this project uses them. **Save working hours** saves.

## Activity
Every timer event in the project: Time · Event · Work item · SLA · Detail, filtered by **Event** and **SLA**. Activity does not refresh by itself: select **Refresh** to load new events. **Check now** runs the 5-minute check at once.

---
[Back to home](../README.md) · Support: info@berkly.nl

