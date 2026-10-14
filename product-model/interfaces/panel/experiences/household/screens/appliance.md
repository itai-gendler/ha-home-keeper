---
entities:
- {entity: appliance, shows: [Name, Device, Icon, Manufacturer, Model, Serial number, Replacement cost, Notes, Custom fields, Tracked dates, Area, Parent appliance, Related devices, Managed by, Maintenance history], collects: [Name, Icon, Manufacturer, Model, Serial number, Replacement cost, Notes, Custom fields, Tracked dates, Area, Parent appliance, Related devices]}
- {entity: part, shows: [Name, Part number, Vendor, Cost, Notes, Kind, Replacement interval, Action, Count uses as, Use task name, Target uses, Time limit, Last replaced, Stock, Reorder at, Stock unit, Used per completion, Restock quantity, Auto-create buy task, Product URL, Attached file, NFC tag, Require tag scan], collects: [Name, Part number, Vendor, Cost, Notes, Kind, Replacement interval, Action, Count uses as, Use task name, Target uses, Time limit, Last replaced, Stock, Reorder at, Stock unit, Used per completion, Restock quantity, Auto-create buy task, Product URL, Attached file, NFC tag, Require tag scan]}
- {entity: appliance-document, shows: [Name, Link, File], collects: [Name, Link, File]}
- {entity: task, shows: [Name, Due date]}
entryPoints:
- panel: /home-keeper/appliances/<id>
---

# Appliance

One appliance's page with its Parts, Tasks, Documents, Details, Related and History tabs, and the
appliance editor beside it. A user who is not an admin sees it with a View only chip.
