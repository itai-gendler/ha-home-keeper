---
domain: tasks
availability:
- {place: 'panel::household'}
- {place: services}
references:
- kind: code
  role: implementation
  target: custom_components/home_keeper/sensor_watcher.py#SensorTaskWatcher
- kind: code
  role: implementation
  target: custom_components/home_keeper/problem_sync.py#ProblemSensorSync
- kind: doc
  role: intent
  target: docs/guide/tasks/triggered-tasks.md
- kind: doc
  role: intent
  target: docs/guide/tasks/sensor-tasks.md
---

# Arm a task

Make a condition-driven task due now: Home Keeper arms a sensor-based task when its entity meets its condition, a declarative companion's or a synced problem sensor's task when its entity does, and a usage task when the meter reaches its target; a companion arms its triggered task.
