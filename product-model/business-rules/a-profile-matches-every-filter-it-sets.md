---
appliesTo:
- type: capability
  id: browse-tasks
- type: capability
  id: send-notification
- type: capability
  id: sync-to-do-list
references:
- kind: doc
  role: intent
  target: docs/guide/views/profiles.md
- kind: code
  role: implementation
  target: custom_components/home_keeper/profiles.py#matches_filter
---

# A profile shows only tasks that match every filter it sets

Within one filter any value matches; across filters every one must match, and an exclusion, inherited labels and areas included, wins over the includes. A task created in the panel has no companion, so a Companions filter neither selects nor excludes it.
