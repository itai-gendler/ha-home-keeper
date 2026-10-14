---
singleton: true
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/options.py#async_set_options
- kind: doc
  role: intent
  target: docs/guide/views/settings.md
---

# Home Keeper settings

The integration's options, kept once for the Home Assistant instance.

## Information kept

- **One-off retention** — days a completed one-off task is kept; 0 keeps it forever
- **Due time** — At the time of completion, or At a set time with its time of day
- **Shopping list** — the to-do list buy reminders go to
- **Line text on list** — With verb or Product only
- **Problem sensor sync** — whether problem binary sensors become tasks
- **Problem sensor exclusions** — entities, devices, areas and labels the sync leaves out
- **Snooze on** — whether Snooze is offered
- **Skip on** — whether Skip is offered
- **Due today on** — whether Due today is offered
- **Hidden panel tabs** — companion panel tabs that are hidden
- **Dismissed companions** — suggested companions put aside
