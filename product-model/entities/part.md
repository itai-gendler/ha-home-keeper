---
domain: appliances
relations:
- entity: task
  verb: keeps
  cardinality: one-to-many
references:
- kind: doc
  role: intent
  target: docs/guide/appliances/appliances.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/reconcile.py#reconcile_part_tasks
---

# Part

A consumable or a wear item of an appliance, with its spare stock.

## Information kept

- **Name** — its name
- **Part number** — the part number
- **Vendor** — where it is bought
- **Cost** — its price
- **Notes** — Markdown notes
- **Kind** — Consumable or Wear item
- **Replacement interval** — how often a wear item is due
- **Action** — Replace, Clean, Service, Renew, Sharpen, Rotate or Inspect
- **Count uses as** — the word for a use when the wear item counts uses
- **Use task name** — the name of the use task
- **Target uses** — the uses after which the wear item is due
- **Time limit** — a period beside the count, whichever comes first
- **Last replaced** — when the wear item was last replaced
- **Stock** — spares in stock, counted or measured
- **Reorder at** — the threshold for low stock
- **Stock unit** — the unit stock is measured in
- **Used per completion** — how much one completion draws
- **Restock quantity** — how much a completed buy task adds
- **Auto-create buy task** — whether low stock makes a buy task
- **Product URL** — the product page
- **Attached file** — one file such as a receipt
- **NFC tag** — the tag that completes its task
- **Require tag scan** — whether only a scan completes its task
