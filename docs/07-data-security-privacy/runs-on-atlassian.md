# Runs on Atlassian and zero egress

The app is built on Atlassian Forge with UI Kit on every screen. It declares **no** external fetch permissions: no outside servers, no Slack, no webhooks, no email. A test in the code checks this on every build. Customer data never leaves Atlassian.

---
[Back to home](../README.md) · Support: info@berkly.nl

