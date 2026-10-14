---
domain: profiles
relations:
- entity: notification
  verb: selects tasks for
  cardinality: one-to-many
references:
- kind: doc
  role: intent
  target: docs/guide/views/profiles.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/profiles.py#normalize_profile
---

# Profile

A saved filter of tasks that the task list, the dashboard card, notifications and to-do list syncs reuse.

## Information kept

- **Name** — its name
- **Include** — Overdue only, Overdue and due soon, or Every scheduled task
- **Labels** — labels to include
- **Areas** — areas to include
- **Devices** — devices to include
- **Companions** — task sources to include
- **Exclude labels** — labels to remove
- **Exclude areas** — areas to remove
- **Exclude devices** — devices to remove
- **Exclude companions** — task sources to remove
- **Exclude shopping** — whether buy tasks are removed
- **To-do list** — the to-do list the profile's tasks sync to
- **Two-way sync** — whether completions and due dates on that list come back
- **Treat removed items as completed** — whether an item removed from that list counts as done
