---
id: home-keeper
summary: 'A Home Assistant integration that tracks home maintenance and chores: recurring tasks with schedules, sensors and due states, completion history, appliances with parts and spare stock, and reminders on the household''s own phones and to-do lists.'
category: home-automation
tags:
- home-assistant
- home-maintenance
- chores
- reminders
- appliances
authors:
- name: Preston Tamkin and the Home Keeper contributors
  url: https://github.com/prestomation/ha-home-keeper
license: MIT
languages:
- en
- ca
- cs
- da
- de
- es
- fi
- fr
- it
- nb
- nl
- pl
- pt-BR
- ru
- sv
- zh-Hans
limitations:
- Home Keeper runs inside one Home Assistant instance with one configuration, and people use it with their Home Assistant accounts; who is an admin is decided in Home Assistant.
- Only an admin changes appliances, settings, profiles, notifications and declarative companions; every signed-in user uses the tasks and reads the appliances.
- Notifications go only to Home Assistant companion-app devices and persistent notifications.
- The panel has no control to disable a task; an automation or a service call disables it.
- Files and photos are added only in the panel or the dashboard card; automations and services never send a file.
references:
- kind: doc
  role: intent
  target: README.md
- kind: doc
  role: intent
  target: docs/guide/start/concepts.md
- kind: doc
  role: intent
  target: docs/SECURITY.md
- kind: doc
  role: intent
  target: docs/design/architecture.md
---

# Home Keeper

Home Keeper tracks home maintenance and chores in Home Assistant: filter changes, medicine, cleaning
and anything else that recurs. Each task has a schedule — repeating after each completion, on a
fixed calendar, just once, triggered by another integration, or based on a sensor reading — and
Home Keeper works out when it is due, overdue or due soon.

People complete, snooze and skip tasks in the Home Keeper panel, on the dashboard card, on the
native to-do list and device pages, from actionable phone notifications and by scanning NFC tags.
Every completion is kept with its note, cost, photo, reading and the person who did it. Appliances
keep their make, model, serial number, documents, parts and spare stock; wear items become
maintenance tasks and low stock becomes a buy reminder. Profiles are saved filters that drive
notifications and to-do list syncs, and declarative companions turn matching Home Assistant
entities into tasks. Every data action is also a `home_keeper.*` service for automations, scripts
and other integrations.

## Intent

In the README's words, Home Keeper "tracks home maintenance and chores in Home Assistant",
including "fridge and furnace filter changes, water filters, taking medicine, and anything else
that recurs". Its security model has "one rule: only an admin can change the home. Any signed-in
user can use it and read it."
