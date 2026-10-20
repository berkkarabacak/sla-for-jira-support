# SLA for Jira Software — Get started

SLA for Jira Software measures how long work takes against targets you set, on
ordinary Jira Software projects. It counts working hours only, pauses when work
is blocked, and publishes every clock to JQL. Nothing leaves Atlassian.

Support: https://github.com/berkkarabacak/sla-for-jira-support/issues · info@berkly.nl

## 1. Your first SLA in 5 steps

1. Open **Jira settings (⚙) → Apps → SLA**, or the **Get started** page under
   Manage apps, and pick a project for one-click setup.
2. Or go to **Project settings → Apps → SLA → Targets** and add a goal. Choose a
   measurement: *Time to triage*, *Time to resolution*, *Cycle time* or *Time in
   review*. Each one states its start and stop condition in the picker.
3. Set the target (for example 8 working hours) and, optionally, which issues it
   applies to.
4. Pick a calendar (working hours). The default uses your site's timezone.
5. Save. New policies measure issues created from today. Backfilling existing
   issues is a separate, previewed opt-in.

The clock now shows in the issue's right-hand **SLA** panel, and the team watches
timers in the project sidebar under **SLA** (At risk now, On-time %, All timers,
Report).

## 2. Calendars and timezones

- Site-wide calendars live under **Jira settings → Apps → SLA → Calendars**;
  each project picks one under **Project settings → Apps → SLA → Working hours**.
- A calendar has a timezone (any IANA zone, DST handled), weekly hours (split
  shifts allowed) and holidays.
- A clock only counts minutes inside working hours. Outside them it waits, and
  the panel shows when it resumes.
- Editing a calendar re-plans existing deadlines in place; history is kept.

## 3. Pause, extend, exclude, restart

- **Automatic pause:** in a goal, set *Pause while the issue is in* (statuses)
  and/or *Pause while the issue is flagged*.
- **Manual overrides** in the issue's SLA panel: **Pause** / **Resume**,
  **Add 4h** (extends the deadline by 4 working hours) and **Exclude** (stop
  measuring this issue; it can be measured again later). Each is recorded with
  who and why (Project settings → SLA → Activity).
- **Reopening** (Done → In Progress) starts cycle 2 instead of freezing the clock.

## 4. SLA in JQL

These fields work in the issue navigator, boards, filters and automation:

| Field | Meaning | Example |
|---|---|---|
| `slaState` | `ok`, `at_risk`, `breached`, `paused`, `met`, `missed` | `slaState = "at_risk" AND assignee = currentUser()` |
| `slaBreached` | `"true"` once a target is missed | `slaBreached = "true" AND statusCategory != Done ORDER BY slaDueAt ASC` |
| `slaDueAt` | deadline (date, sortable) | `slaDueAt <= endOfDay() AND statusCategory != Done` |
| `slaGoal` | goal name (text) | `slaGoal ~ "resolution"` |

Field names are camelCase: searching "SLA state" matches nothing. The JQL index
updates within a few minutes; the app's own screens are real-time.

## 5. What the Health tab means

**Jira settings → Apps → SLA → Health**

| Line | Meaning | Action |
|---|---|---|
| Last check | The five-minute sweep that moves clocks and announces breaches. | Warns if older than 15 minutes. |
| Last hourly job | Retries JQL publishing and cleanup. | None. |
| Timers | Running (breached ones included) · paused · not started · stopped. | None. |
| Excluded timers | Issues someone excluded manually. | None. |
| Timers on an older calendar version | A calendar changed since these deadlines were worked out. | None: the hourly job gives them new deadlines. |
| No reachable deadline | The calendar has no working time ahead (e.g. no hours set). | Fix the calendar's working hours. |
| Waiting to publish to JQL | Issues whose SLA values are not in JQL yet. | Normally clears within minutes; a reason is shown if it fails. |
| Active jobs | Backfill or republish jobs in progress. | None. |
| Sprint field / Flagged field | The Jira fields the app found on your site. | "not found" means sprint or flag-based features can't work. |

## Legal

[Privacy policy](https://berkly.nl/privacy/sla-for-jira) ·
[EULA](https://berkly.nl/eula/sla-for-jira) · [DPA](https://berkly.nl/dpa/sla-for-jira)
