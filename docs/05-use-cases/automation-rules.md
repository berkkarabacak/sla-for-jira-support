# Automation rules

Jira Automation can use the SLA JQL fields.

| Rule | Trigger | Condition / action |
|---|---|---|
| Escalate breaches | Scheduled, every hour, JQL `slaBreached = "true" AND statusCategory != Done AND priority != Highest` | Edit priority → Highest |
| Morning digest | Scheduled, daily, JQL `slaDueAt <= endOfDay() AND statusCategory != Done` | Send email to the team (from Jira, not the app) |
| Nudge assignee | Scheduled, JQL `slaState = "at_risk"` | Comment mentioning the assignee |

## "When an SLA breaches" (there is no SLA trigger)

Forge apps can add Automation **actions** but not **triggers**, so there is no "SLA breached" trigger to pick. Two ways to get the same result:

1. **Scheduled rule (simplest).** Trigger: *Scheduled*, every 15 minutes, JQL `slaBreached = "true" AND statusCategory != Done AND labels != sla-escalated`. Actions: assign, comment or send the email, then *Edit work item → add label* `sla-escalated` so each item fires once. The app updates the index every 5 minutes.
2. **Any trigger + the Check SLA timer action.** Trigger: e.g. *Work item updated* or *Scheduled*. Action: **Check SLA timer (breach / at risk)** (from SLA for Jira Software) with work item key `{{issue.key}}`. Then an *If* condition on the smart value it returns (the rule builder lists it, e.g. `state`, `breached`, `timeLeft`, `remainingMinutes`, `goal`).

### Finding the action in the rule builder

1. **Add an action**, then type `SLA timer` (or `SLA`) in the search box.
2. Scroll to the **Other apps** group at the **bottom** of the results. Jira always lists app actions last, so for `SLA` you first see Amazon and Google *translate* actions and Slack actions, which match the letters "sla".
3. The first time, the step says *"Before you can use this step, you'll need to connect Atlassian Automation to SLA for Jira Software"*. Click **Connect** once (a Jira admin may need to do this), then set the work item key to `{{issue.key}}`.

> **Tip:** At-risk works the same way: use `slaState = "at_risk"` in option 1, or `state` equals `at_risk` in option 2.

> **Note:** The app itself only writes a comment and a label on breach. Any email or chat message comes from your Jira Automation rule, so the app keeps zero egress.

---
[Back to home](../README.md) · Support: info@berkly.nl

