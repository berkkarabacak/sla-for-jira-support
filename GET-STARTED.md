# SLA for Jira Software: Get started

SLA for Jira Software measures how long work takes against working-hours targets on ordinary **Jira Software** projects. No Jira Service Management needed. It counts working hours only, pauses when work is blocked, and publishes every timer to JQL. It runs on Atlassian and sends no data anywhere else.

Full documentation: [documentation home](docs/README.md) · Support: https://github.com/berkkarabacak/sla-for-jira-support/issues · info@berkly.nl

## 1. Your first SLA in 5 minutes

**Option A: one-click setup**

1. Open **Jira settings (⚙) → Apps → SLA get started**.
2. In **Turn on SLAs for a project**, choose the **Project** and, if you like, the **Work types** (empty means all except sub-tasks).
3. Select **Turn on SLAs**. The project gets two SLAs, *Time to triage · 4h* and *Time to resolution · 3d*, on the default working hours.

If the project already has SLAs, turning them on replaces them with the two defaults. Get started warns you first.

**Option B: add an SLA by hand**

1. Go to **Project settings → Apps → SLA**. On the **SLAs** tab, pick a preset card or **Start from scratch**; later, use **Add SLA**.
2. Choose what to **Measure**. The line under it shows where the timer starts and stops.
3. Set the **Target** (for example 8 working hours) and, optionally, which work types it **Applies to**.
4. Check the **Working hours** on the **Measuring** card. The default uses your site's timezone.
5. Select **Add SLA**, then **Save changes**.

New SLAs measure work items **created from now on** (**New work items only**). Measuring older work is a separate, previewed step: [Backfill](docs/04-admin-guide/backfill.md).

## 2. See your first result

1. Create a work item in the project, or move one into the SLA's start condition.
2. Open it. The **SLA** panel shows the status, the time left (for example *3h 20m left*) and when it is due. **History** explains every start, pause and stop.
3. Open the project sidebar → **SLA**. It has three tabs: **Needs attention** (breached and soon-due timers, most overdue first), **All timers** (every timer, with CSV export) and **Performance** (on time, met, missed, and the missed work items). **Configure** opens the project's SLA settings.
4. Within a few minutes, try JQL: `slaState = "ok"`.

## 3. Working hours and timezones

- Working hours are managed under **Jira settings (⚙) → Apps → SLA → Working hours**. Each project picks its working hours on **Project settings → Apps → SLA**, and the project's **Working hours** tab shows and edits them.
- A set of working hours has a timezone (any IANA zone, DST handled), a week starting on Monday (split shifts allowed) and holidays.
- A timer only counts time inside working hours. Outside them it waits.
- Saving working hours gives running timers new deadlines in place; history is kept.

## 4. Pauses and manual overrides

- **Automatic pauses**, set in each SLA: **Pause in** chosen statuses, and **Pause while flagged**.
- **Actions** under an SLA in the work item panel: **Pause** / **Resume**, **+4h** (extends the deadline by 4 working hours) and **Exclude** (stops every timer on the work item and removes it from reports; **Measure again** brings it back). Each asks for a **Reason**, shown with who did it in the timer's **History** and in **Project settings → Apps → SLA → Activity**.
- **Reopening** a done work item starts cycle 2 instead of freezing the old timer.

## 5. SLA values in JQL

These fields work in the issue navigator, boards, filters and automation:

| Field | Meaning | Example |
|---|---|---|
| `slaState` | `ok`, `at_risk`, `breached`, `paused`, `met`, `missed` | `slaState = "at_risk" AND assignee = currentUser()` |
| `slaBreached` | `"true"` once a target is missed, including stopped misses that have no deadline | `slaBreached = "true" AND statusCategory != Done ORDER BY slaDueAt ASC` |
| `slaDueAt` | deadline (date, sortable) | `slaDueAt <= endOfDay() AND statusCategory != Done` |
| `slaGoal` | SLA name (text) | `slaGoal ~ "resolution"` |

Field names are camelCase: searching "SLA state" matches nothing. JQL catches up within a few minutes; the app's own screens are live.

## 6. What the Health tab means

**Jira settings (⚙) → Apps → SLA → Health** opens with one banner: **No problems found**, or how many checks need attention, with **Run check now**.

| Check | Meaning | Action |
|---|---|---|
| Last check | The 5-minute check that moves timers and announces breaches. A check with nothing to do is recorded every 30 minutes. | Warns if older than 45 minutes. |
| Hourly job | Retries JQL publishing and cleans up. | None. |
| Timers | Running (breached included) · paused · not started · stopped. | None. |
| Excluded timers | Timers someone excluded. | None. |
| Deadlines to refresh | Timers whose working hours changed after their deadline was set. | None: a background job gives them new deadlines within about six hours. |
| No reachable deadline | Timers whose working hours leave no time to run in. | Fix those working hours. |
| Waiting to publish | Work items whose SLA values are not in JQL yet. | Clears within minutes; the reason shows if it fails. |
| Active jobs | Backfill or JQL rebuild in progress. | None. |
| Sprint field / Flagged field | Jira fields found on your site. | **Not found** means sprint- or flag-based pauses can't work. |

## Legal

[Privacy policy](https://berkly.nl/privacy/sla-for-jira) · [EULA](https://berkly.nl/eula/sla-for-jira) · [DPA](https://berkly.nl/dpa/sla-for-jira)
