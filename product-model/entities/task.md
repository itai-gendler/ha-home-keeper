---
domain: tasks
relations:
- entity: completion
  verb: records
  cardinality: one-to-many
- entity: skip
  verb: records
  cardinality: one-to-many
- entity: task-photo
  verb: shows
  cardinality: one-to-many
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/models.py#build_task
- kind: code
  role: implementation
  target: custom_components/home_keeper/models.py#normalize_fields
- kind: doc
  role: intent
  target: docs/guide/start/concepts.md
---

# Task

A piece of home maintenance or a chore that Home Keeper tracks, with the schedule that decides when it is due.

## Information kept

- **Name** — what to do
- **Notes** — Markdown notes
- **Schedule kind** — Repeats after each completion, Repeats on a fixed schedule, Just once, triggered, Based on a sensor, or a counted use
- **Interval** — every how many days, weeks, months or years
- **Fixed start** — the date and time a fixed schedule is anchored to
- **Due date** — when the task is next due; empty while it waits for a condition
- **Last completed** — when it was last done
- **Active season** — the windows of the year the task belongs in
- **Device** — the Home Assistant device or appliance it is about
- **Area** — the room, taken from the device unless set
- **Labels** — Home Assistant labels on the task
- **Sensor** — the entity, and optionally the attribute, a sensor-based task watches
- **Trigger mode** — Usage or meter, Threshold, State, Availability or Template
- **Trigger condition** — the target, comparison, state and hold of the trigger
- **Trigger template** — the Jinja template a template trigger renders
- **Combined cadence** — the Or every period and Combine with choice of a usage task
- **Clear when back to normal** — whether the task completes itself when the sensor recovers
- **Meter baseline** — the reading a usage task counts from
- **On completion** — One-tap done, Ask for details or Require details
- **Required completion fields** — the details a completion must carry
- **NFC tag** — the tag whose scan completes the task
- **Require tag scan** — whether only a scan completes the task
- **Snooze length** — the task's own snooze length
- **Linked consumable** — the part a completion draws stock from
- **Links to show on card** — appliance documents the dashboard card shows on the task
- **Integration chips** — chips an integration attaches to the task
- **Managed by** — the companion, declarative companion, problem sensor or appliance part that owns the task, with the fields it locks
- **Deletion protected** — whether its managing integration protects it from deletion
- **Completed by its condition** — whether only the recovery of its condition completes the task
- **External id** — the author's own stable name for import and export

## States

### Scheduled

The task has a due date: a clock schedule, or a condition that is armed.

### Monitored

The task waits for its condition and has no due date.

### Counted

The use task of a counted wear item: it records uses and is never due.

### Completed

A one-off task that was done; it stays in the Completed section.

### Disabled

The task keeps everything recorded on it, and Home Keeper stops asking for it.
