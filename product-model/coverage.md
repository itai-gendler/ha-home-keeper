---
scope: The Home Keeper integration under custom_components/home_keeper/, its panel and dashboard card, and its product documentation.
method: Static inspection of source, user guide, design docs and security model.
covered:
- description: Task store, recurrence engine, task model and completion, skip and snooze records.
  paths:
  - custom_components/home_keeper/store.py
  - custom_components/home_keeper/models.py
  - custom_components/home_keeper/recurrence.py
  - custom_components/home_keeper/transitions.py
- description: Service and websocket handlers with the admin gate.
  paths:
  - custom_components/home_keeper/__init__.py
  - custom_components/home_keeper/websocket_api.py
  - custom_components/home_keeper/services.yaml
- description: Appliances, parts, stock, documents, wear-item and buy-task reconcilers and the appliance report.
  paths:
  - custom_components/home_keeper/assets.py
  - custom_components/home_keeper/reconcile.py
  - custom_components/home_keeper/manuals.py
  - custom_components/home_keeper/documents.py
  - custom_components/home_keeper/appliance_report.py
  - custom_components/home_keeper/devices.py
- description: Sensor tasks, problem-sensor sync and declarative companions.
  paths:
  - custom_components/home_keeper/sensor_tasks.py
  - custom_components/home_keeper/sensor_watcher.py
  - custom_components/home_keeper/problem_sync.py
  - custom_components/home_keeper/problem_tasks.py
  - custom_components/home_keeper/declarative_companions.py
  - custom_components/home_keeper/declarative_companion_sync.py
  - custom_components/home_keeper/declarative_presets.py
- description: Profiles, notifications and the to-do list and shopping list syncs.
  paths:
  - custom_components/home_keeper/profiles.py
  - custom_components/home_keeper/notifications.py
  - custom_components/home_keeper/notifier.py
  - custom_components/home_keeper/todo_list_sync.py
  - custom_components/home_keeper/todo_sync_driver.py
  - custom_components/home_keeper/todo_items.py
  - custom_components/home_keeper/shopping.py
  - custom_components/home_keeper/shopping_sync.py
- description: Options and settings.
  paths:
  - custom_components/home_keeper/options.py
- description: Native to-do, calendar and device-page button entities and the tag listener.
  paths:
  - custom_components/home_keeper/todo.py
  - custom_components/home_keeper/calendar.py
  - custom_components/home_keeper/button.py
  - custom_components/home_keeper/tag_listener.py
  - custom_components/home_keeper/tags.py
- description: Task photos.
  paths:
  - custom_components/home_keeper/task_photos.py
  - custom_components/home_keeper/photo_thumbs.py
- description: Companion registry.
  paths:
  - custom_components/home_keeper/companions.py
- description: Import and export.
  paths:
  - custom_components/home_keeper/transfer.py
  - custom_components/home_keeper/transfer_runner.py
  - custom_components/home_keeper/transfer_http.py
  - custom_components/home_keeper/transfer_bundle.py
- description: Panel and dashboard card frontend sources.
  paths:
  - custom_components/home_keeper/frontend/src/
- description: User guide and security model.
  paths:
  - docs/guide/
  - docs/SECURITY.md
exclusions:
- description: Tests, CI, mutation and build configuration.
  paths:
  - tests/
  - ci/
  - .github/
  - custom_components/home_keeper/frontend/test/
  - stryker.conf.json
  - vitest.config.js
  - vitest.stryker.config.js
  - pyproject.toml
- description: Documentation site, screenshots, writing-style tooling and agent rules.
  paths:
  - website/
  - docs/images/
  - styles/
  - .vale.ini
  - .amazonq/
  - .claude/
  - AGENTS.md
  - CLAUDE.md
- description: Translation tables and string catalogs.
  paths:
  - custom_components/home_keeper/translations/
  - custom_components/home_keeper/backend_strings/
  - custom_components/home_keeper/notification_strings/
  - custom_components/home_keeper/frontend/src/locales/
  - custom_components/home_keeper/strings.json
- description: Typing stubs and package metadata.
  paths:
  - typings/
  - package.json
  - package-lock.json
  - requirements-test.txt
  - requirements-typing.txt
  - hacs.json
unmapped:
- description: Count, next-due, overdue, spare-stock and tracked-date sensor entities and number entities.
  paths:
  - custom_components/home_keeper/sensor.py
  - custom_components/home_keeper/binary_sensor.py
  - custom_components/home_keeper/number.py
  - custom_components/home_keeper/task_counts.py
  - custom_components/home_keeper/task_entities.py
- description: Bus events, device triggers and the integrator API surface model.
  paths:
  - custom_components/home_keeper/events.py
  - custom_components/home_keeper/device_trigger.py
  - custom_components/home_keeper/api_surface.py
  - docs/EVENTS.md
  - docs/INTEGRATING.md
- description: Companion panel tabs that companion code registers.
  paths:
  - custom_components/home_keeper/panel_tabs.py
- description: Config flow and options flow.
  paths:
  - custom_components/home_keeper/config_flow.py
- description: Diagnostics dump.
  paths:
  - custom_components/home_keeper/diagnostics.py
- description: Preset catalogs, preset texts and the suggested-companion catalog.
  paths:
  - custom_components/home_keeper/declarative_presets_catalog.py
  - custom_components/home_keeper/declarative_preset_text.py
  - custom_components/home_keeper/companions_catalog.py
limitations: []
---

# Coverage
