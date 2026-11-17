# Work item SLA panel

Open any work item in a software project and select **SLA** in the right-hand context area. Even collapsed, the row shows the state: *Overdue 2d 4h*, *3h 20m left*, *Paused*, *Met* or *Missed*.

## What you see
| Element | Meaning |
|---|---|
| Status | Icon and word: **Breached**, **At risk**, **On track**, **Paused**, **Not started**, **Met** or **Missed**. |
| Time | Working time: *3h 20m left* or *Overdue 2d 4h*. Once stopped: *Met in 43m* or *Missed after 13d 10h*. |
| Bar | How much of the target is used, in the status colour. |
| Due line | The deadline on your own clock, and the target: *Due Tue 20 Oct, 16:00 · Target 4h*. |
| ⓘ | The working hours, their timezone, and the deadline on their clock. |
| **History** | When the timer started, the working time used, and every change. See [History](why-explanation.md). |
| **Actions** | **Pause** / **Resume**, **+4h**, **Exclude**. See [Manual overrides](manual-overrides.md). |

With several SLAs, the worst comes first.

> **Tip:** Outside working hours the timer waits, and the time says when it resumes: *3h 20m left · resumes Mon 09:00*.

You may also see:
- **Cycle 2 of 2**: the work item was reopened, so the SLA is timing it again.
- **Not announced**: it breached before SLAs were switched on, so no comment or label was added.
- **No working hours ahead**: the working hours leave no time to count. **Fix working hours** opens the settings.
- **No SLAs yet** with a **Set up SLAs** link, when the project has no SLAs.

## Statuses
| Status | Meaning | `slaState` in JQL |
|---|---|---|
| On track | Inside its target. | `ok` |
| At risk | Close to the deadline (the project's **Warn at** setting). | `at_risk` |
| Breached | Past the deadline and still counting. | `breached` |
| Paused | Paused by a status, the flag or by hand; the reason shows beside it. | `paused` |
| Met / Missed | Stopped inside / outside the target. | `met` / `missed` |
| Not started / Excluded | Waiting for its start, or taken out of SLAs by hand. | none |

**Reopening** a done work item starts cycle 2 instead of freezing the old timer.

---
[Back to home](../README.md) · Support: info@berkly.nl

