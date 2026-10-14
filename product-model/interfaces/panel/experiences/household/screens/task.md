---
entities:
- {entity: task, shows: [Name, Notes, Schedule kind, Interval, Fixed start, Due date, Last completed, Active season, Device, Area, Labels, Sensor, Trigger mode, Trigger condition, Trigger template, Combined cadence, Clear when back to normal, Meter baseline, On completion, Required completion fields, NFC tag, Require tag scan, Snooze length, Linked consumable, Links to show on card, Integration chips, Managed by], collects: [Name, Notes, Schedule kind, Interval, Fixed start, Active season, Device, Area, Labels, Sensor, Trigger mode, Trigger condition, Trigger template, Combined cadence, Clear when back to normal, On completion, Required completion fields, NFC tag, Require tag scan, Snooze length, Linked consumable, Links to show on card]}
- {entity: completion, shows: [Completed at, Note, Cost, Photo, Who, Reading], collects: [Completed at, Note, Cost, Photo, Who, Reading]}
- {entity: skip, shows: [Skipped at, Note, Who], collects: [Skipped at, Note, Who]}
- {entity: task-photo, shows: [Image, Cover]}
- {entity: part, shows: [Name, Stock, Product URL]}
entryPoints:
- panel: /home-keeper/tasks/<id>
---

# Task

One task's page, with its Schedule, Notes and History tabs, its photos, the Done, Snooze, Skip and
Due today actions, the completion dialog, and the edit form beside it.
