---
domain: appliances
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/reconcile.py#reanchor_edited_parts
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
---

# Edit a part

Change a part's details, schedule, stock settings, product link, tag and attached file. Its tasks follow: a rename renames them and a new interval reschedules them. On a part a companion owns, only the stock fields are the household's.
