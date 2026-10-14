---
domain: appliances
relations:
- entity: part
  verb: has
  cardinality: one-to-many
- entity: appliance-document
  verb: has
  cardinality: one-to-many
references:
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/assets.py
---

# Appliance

A physical thing that tasks are about, such as a fridge, a furnace or a water heater, also called an asset.

## Information kept

- **Name** — its name
- **Device** — its own virtual device, or an existing Home Assistant device it adds metadata to
- **Icon** — an mdi icon
- **Manufacturer** — the maker
- **Model** — the model
- **Serial number** — kept only in the appliance record
- **Replacement cost** — what it costs to replace
- **Notes** — Markdown notes
- **Custom fields** — labelled text, link or date values
- **Tracked dates** — date fields that also become date sensors
- **Area** — its room
- **Parent appliance** — the appliance it is a subdevice of
- **Related devices** — devices from any integration shown with it
- **Managed by** — the companion that owns it and locks its name and parts
- **Maintenance history** — the completions of its tasks, including tasks since deleted
- **External id** — the author's own stable name for import and export

## States

### Active

In the default appliance list.

### Archived

Out of the active list, with every record, its device and its entities kept.
