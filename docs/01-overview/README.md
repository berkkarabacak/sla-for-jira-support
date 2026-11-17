# Overview

## What it does
SLA for Jira Software starts a timer on each work item for every SLA you define, counts **working time only**, pauses when work is blocked, and stops when the work reaches the SLA's end. Each timer ends as **Met** or **Missed**.

## Who it's for
| Role | What they get |
|---|---|
| Team members | A live SLA timer in each work item's **SLA** panel, with its **History**. |
| Team leads | **Needs attention**, **All timers** and **Performance** on the project page. |
| Jira admins | Projects and their SLAs, working hours, health checks and JQL fields. |
| Security reviewers | Runs on Atlassian, zero egress, Forge SQL storage. |

## Key features
| Feature | Details |
|---|---|
| Four measures side by side | *Time to triage*, *Time to resolution*, *Cycle time*, *Time in review*, each timed in parallel on the same work item. |
| Working hours | Any IANA timezone, DST handled, split shifts and holidays. |
| Targets per priority | A different target per priority, or one target for all. |
| Pauses | Automatic (by status or flag) and manual from **Actions** (Pause, Resume, +4h, Exclude). |
| **History** on every timer | Shows how the deadline was worked out. |
| SLA in JQL | `slaState`, `slaBreached`, `slaDueAt`, `slaGoal` for filters, boards, dashboards and automation. |
| When a target is missed | Optional comment and label on the work item. |
| Backfill | Measure past work, with a preview first. |
| Performance | On time per SLA, metric, priority, assignee or work type, with the missed work items. **Export CSV** on All timers. |
| Health | One tab that shows whether the background jobs are on time. |

> **Tip:** SLAs are usually a Jira Service Management idea. This app brings them to Jira Software projects. See [Use cases](../05-use-cases/README.md).

## How it fits together
| Surface | Where in Jira | Page |
|---|---|---|
| SLA panel | Work item, right-hand side | [Work item SLA panel](../03-user-guide/work-item-sla-panel.md) |
| SLA field | Work item fields | [SLA field](../03-user-guide/sla-field.md) |
| Project page | Project sidebar → **SLA** | [Project SLA page](../03-user-guide/project-sla-page.md) |
| Project settings | Project settings → Apps → **SLA** | [Project settings](../04-admin-guide/project-settings.md) |
| Site-wide admin | Jira settings → Apps → **SLA** | [Site-wide admin page](../04-admin-guide/site-admin-page.md) |

---
[Back to home](../README.md) · Support: info@berkly.nl

