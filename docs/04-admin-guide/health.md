# Health

**Jira settings → Apps → SLA → Health**

One banner at the top: **No problems found** (with when the last check ran), or how many checks need attention, with **Run check now**.

**Checks**

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

**Tools:** **Run check now**; and for one project, chosen under **Repair a project**, **Rebuild JQL index** and **Fix timers**. All are safe to run twice and announce nothing on work items.

**Recent warnings (7 days)** lists problems in plain language, each with its fix.

Collapsed at the bottom: **Technical details** (schema, SQL requests per month, storage, egress, licence), **Data & privacy** (what is stored, with the privacy policy, EULA, DPA and support links) and **Copy diagnostics**, a block to paste into a support request.

---
[Back to home](../README.md) · Support: info@berkly.nl

