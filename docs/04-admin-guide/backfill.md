# Backfill

New SLAs only measure new work. Backfill measures existing work items from their history.

1. In **Project settings → Apps → SLA → SLAs**, turn off **New work items only**. The save bar shows how many work items match and how many would be overdue. Select **Save changes**.
2. In **Jira settings → Apps → SLA → Projects**, open the project's **⋯** menu and select **Apply to existing work items**.
3. It runs as a background job. The project's **SLAs** tab shows its progress, and Health lists it under **Active jobs**.

When you turn SLAs on from **Get started** instead, turn off **New work items only** and turn on **Include existing work items**.

> **Warning:** Backfilled timers that were already breached are recorded but **not** announced with comments or labels. The panel marks them **Not announced**.

---
[Back to home](../README.md) · Support: info@berkly.nl

