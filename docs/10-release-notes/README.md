# Release notes

Plain-English summary of what changed, newest first. Dates are when the change reached the main branch.

## 13 November 2026
- Sites never share anything, even in memory. Atlassian can run several customers' copies of the app in the same process, so the app now keeps each site's settings, field ids and permission checks separate. Before this, a second site served by the same process could briefly be handed another site's cached settings, and its own database setup could be skipped.
- The **Needs attention** list that your browser keeps for a quicker first paint is now kept per site and per person, so it can never show another site's work items while a page loads.

## 28 October 2026 — 5.0: redesigned screens
- Status at a glance everywhere: an icon, a word and a colour (red breached, yellow at risk, blue on track, green met), a bar, and times such as "Overdue 2d 4h" or "3h 20m left". Deadlines are on your own clock.
- Fewer words: help moved into ⓘ tips and collapsed sections, and each thing has one name: SLA (not goal), timer, work item, working hours, on time.
- The project page has three tabs: **Needs attention** (was At risk now), **All timers** and **Performance** (On-time % and Report in one, with the missed work items a click away). **Configure** opens the project's settings.
- The work item panel shows the status, the time and the due date first, with **History** (was Why?) and **Actions** (was More actions) under each SLA.
- Project settings: tabs **SLAs**, **Working hours** and **Activity**. Each SLA is added or edited in one **Add SLA** dialog, changes wait in a save bar (**Discard** / **Save changes**), and the working hours editor starts the week on Monday.
- Site admin: **Projects** lists each project's SLAs by name (the Goals tab is gone) and adds SLAs to another project from a picker; **SLA in JQL** is now **JQL**; **Health** opens with one banner that says whether anything needs attention.
- **Get started** is one card, **Turn on SLAs for a project**, plus a **Now** strip of live counts.
- Activity no longer refreshes by itself: select **Refresh** to load new events.
- Lighter on the database: Activity stopped polling every 30 seconds, the admin page no longer reads every project's setup, and the missed work items load only when you open them.

## 28 October 2026
- Editing your working hours now moves running deadlines. Before, a calendar change left the deadlines it affected on the old hours; now they are recalculated in place, quietly (nothing is announced because of the edit itself), and a very large project finishes within a few hours.
- The collapsed SLA row in the issue sidebar now shows the live state ("Overdue 1d 20h", "3h 20m left", "Met") instead of a fixed "SLA" label.
- Health: "Last check" is now "Last recorded check". A quiet check is recorded every 30 minutes and Health warns after 45.
- The app makes far fewer database requests when nothing is happening, so more sites fit inside the platform's free allowance.

## 21 October 2026
- The site-wide admin page now opens with the app name, a one-line description and counts of projects, goals, timers and breaches.
- Marketplace listing text rewritten around what sets the app apart.

## 20 October 2026
- Get started guide, linked from the admin page and Health.
- Admin and work lists load faster.
- Deadlines show your own clock first and the calendar's clock beside it.
- At risk now keeps time left for out-of-hours rows and shows when they resume; its caption now covers breached rows too.
- Triage preset ships with Highest 1h and High 2h tiers.
- Privacy, data and support section with legal links on the admin page.
- Health explains the "older calendar version" line and no longer shows it in red.

## 19 October 2026
- Final privacy policy, EULA and DPA published.
- Confirmation before deleting working hours; clearer save notices on Calendars.
- An inactive paid licence makes the app read-only instead of blocking it.

## 14 October 2026
- "View timers for this project" opens the project SLA page correctly.
- Targets explain that a working day counts as 24 working hours.
- On-time tiles count done work only; Recalculate agrees with the header; the panel links to "Set up an SLA" when no goal applies.

## 12–13 October 2026
- Personal data is reported to Atlassian and erased for closed accounts (new `report:personal-data` scope; sites approve the upgrade).
- The manual pause note shows in the panel headline.

## 8–10 October 2026
- Plain-language Health logs, Show CSV, Sprint and Flagged field names in Health.
- Renaming a goal republishes it to JQL.
- First-run guidance, manager-ready results card, Copy as CSV, Exclude warning.
- SLA in JQL tab with index freshness and Publish now; overdue work in At risk now.
- Excluded work items can be measured again; Activity shows names.
- Fixed a stuck backfill and mismatched counts.

## Early October 2026
- Assignee, priority and report deadlines stay current.
- Breached state published to JQL; pause and resume only shift a breached deadline by the paused time.
- Reliability fixes for JQL publishing and overlapping events.

---
[Back to home](../README.md) · Support: info@berkly.nl
