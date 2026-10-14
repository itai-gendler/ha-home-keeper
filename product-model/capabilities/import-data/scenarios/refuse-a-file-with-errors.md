---
kind: validation
routes:
  panel: Panel
steps:
- text: The Admin previews a file with an unquoted no in a text field
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
- text: The Product reports the error with its path and keeps Import off
  kind: product
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::administration::import-and-export'}
---

# Refuse a file with errors

## Trigger

A file has an error in one section.

## Outcome

No record in any section is written.
