# Pauses and manual overrides

## Automatic pauses
Set in each SLA (see [Project settings](../04-admin-guide/project-settings.md)):
- **Pause in** chosen statuses.
- **Pause while flagged.**

## Actions in the SLA panel
Select **Actions** under an SLA, then:

| Action | Effect |
|---|---|
| **Pause** / **Resume** | Stops and restarts the timer. A breached deadline only moves by the paused working time. |
| **+4h** | Extends the deadline by 4 working hours. |
| **Exclude** | Stops every timer on this work item and removes it from reports. **Measure again** brings it back. |

Each action asks for a **Reason**. Who did it and why shows in the timer's [History](why-explanation.md) and in **Project settings → Apps → SLA → Activity**.

> **Warning:** Excluded work items no longer count toward **On time**. Health lists how many timers are excluded.

---
[Back to home](../README.md) · Support: info@berkly.nl

