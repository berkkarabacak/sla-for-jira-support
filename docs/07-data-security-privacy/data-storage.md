# Data storage and retention

All data lives in the app's Forge SQL database on Atlassian, one per site.

| Data | Personal data? | Kept |
|---|---|---|
| Calendars, holidays, goals | No | Until you delete them |
| Timers (work item key, summary, status, priority, assignee ID and name, SLA times) | Yes | While installed; per goal history on delete if chosen |
| Activity log (who did what) | Yes (account ID) | 180 days |
| Diagnostics | No | Newest 500 rows |

**Sites never mix:** Atlassian's Forge platform can serve several customers from one process, so the app keeps everything it holds in memory (settings, field ids, permission answers) separately for each installation, and reads a site's data only from that site's own database. The saved copy of the Needs attention list in your browser is kept per site and per person.

**Uninstall:** the app can no longer read its database. Atlassian keeps it for a short window (28 days at the time of writing) in case you reinstall, then deletes it.

---
[Back to home](../README.md) · Support: info@berkly.nl

