---
domain: appliances
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/manuals.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/assets.py#append_document
---

# Appliance document

A manual, warranty, receipt or other document of an appliance: an external link or an uploaded file.

## Information kept

- **Name** — its title
- **Link** — the URL of a link document
- **File** — the uploaded PDF or image
