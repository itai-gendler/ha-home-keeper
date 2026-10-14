---
kind: validation
routes:
  panel: Panel
steps:
- text: The Admin picks a file larger than 100 MB
  kind: actor
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
- text: The Product rejects the file before the upload
  kind: product
  actor: admin
  entities: []
  contexts:
    panel: {place: 'panel::household::appliance'}
---

# Refuse a file over 100 MB

## Trigger

An admin picks a file larger than 100 MB.

## Outcome

Nothing is uploaded.

## Edge cases

- An upload a proxy rejects shows the reason under Upload file and as a Home Assistant notification.
