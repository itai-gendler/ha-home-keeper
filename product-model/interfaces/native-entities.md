---
type: api
actors:
- household-member
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/todo.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/calendar.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/button.py
- kind: doc
  role: intent
  target: docs/guide/start/features.md
---

# Native entities

The Home Keeper to-do list, the upcoming-tasks calendar and the Mark done button on each task's
device page, used through Home Assistant's own to-do, calendar and device screens.
