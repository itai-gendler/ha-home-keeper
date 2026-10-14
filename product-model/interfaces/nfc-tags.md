---
type: device
actors:
- household-member
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/tag_listener.py
- kind: code
  role: implementation
  target: custom_components/home_keeper/tags.py
- kind: doc
  role: intent
  target: docs/guide/tasks/nfc-tags.md
---

# NFC tags

Home Assistant NFC and RFID tags that a person scans with a phone or a reader to complete the
tasks linked to the tag.
