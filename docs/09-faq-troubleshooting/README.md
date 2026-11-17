# FAQ and troubleshooting

## Do I need Jira Service Management?
No. The app works on Jira Software projects.

## My JQL search returns nothing.
Use camelCase names (`slaState`, not "SLA state"). Values arrive within a few minutes; check the admin **JQL** tab for freshness and use **Publish now**.

## Old work items have no timer.
SLAs measure new work only. Run a [Backfill](../04-admin-guide/backfill.md).

## A timer isn't moving.
It may be outside working hours (the panel shows when it resumes), paused, or excluded. Open its **History**.

## Health says "No reachable deadline".
Its working hours have no working time ahead. Add working hours.

## Health says "Last check" is old.
The check runs every 5 minutes, but when nothing is due it records itself only every 30 minutes, so "10 or 25 minutes ago" on a quiet site is normal. If it stays over 45 minutes, the check has stopped: select **Run check now**, and if that does not move it, contact support.

## Health says "Sprint field / Flagged field: Not found".
Your site has no such field, so sprint- or flag-based pauses can't work.

## Only some breaches got a comment.
Comments are capped at 25 work items per check; the rest follow on the next checks.

## Settings show "View only".
You need project admin rights, or the licence is inactive.

See also [Health](../04-admin-guide/health.md).

---
[Back to home](../README.md) · Support: info@berkly.nl

