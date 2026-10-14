---
entities:
- {entity: task, shows: [Name, Due date, Schedule kind, Device, Area, Labels, Integration chips, Managed by]}
- {entity: task-photo, shows: [Image]}
- {entity: profile, shows: [Name]}
- {entity: home-assistant-user, shows: [Task list layout], collects: [Task list layout]}
entryPoints:
- panel: /home-keeper/tasks
---

# Task list

The Tasks tab: every task with its status, scope pills with counts, search, the Profile picker,
grouping, and the layout choice. Disabled, monitored, counted, shopping and completed tasks have
sections of their own.
