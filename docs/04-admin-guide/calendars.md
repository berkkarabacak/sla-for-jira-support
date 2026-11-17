# Working hours, timezones, split shifts and holidays

**Jira settings → Apps → SLA → Working hours** has one card per set of working hours: its week, timezone, hours per week, holidays and how many projects use it. **New working hours** adds a set; each card has **Edit** and **Delete**. Each project picks its working hours in **Project settings → Apps → SLA**.

| Part | Details |
|---|---|
| Week | Start from a shape (**Mon–Fri 9–5**, **24/7** or **Clear**), then set each day from Monday: a From–To time, or **Closed**. **Copy Monday to weekdays** repeats Monday. |
| Split shifts | Several windows per day (09:00–12:00, 13:00–17:00). |
| Timezone | Any IANA zone (for example `Europe/Istanbul`). DST handled. |
| Holidays | Dates with no working time. |

A summary line says what the week adds up to, for example *40 h/week · a 4h SLA raised Fri 16:00 is due Mon 12:00*. **Save working hours** gives running timers new deadlines in place; history is kept.

**Delete** asks for confirmation. Working hours that a project still uses can't be deleted: move the project to other working hours first.

> **Warning:** Working hours with no working time ahead give timers no reachable deadline. The panel then shows **No working hours ahead**, and Health counts them under **No reachable deadline**.

---
[Back to home](../README.md) · Support: info@berkly.nl

