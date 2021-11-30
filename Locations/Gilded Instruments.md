---
type: location
locationType: place
city: "Jalantar"
tags:
- location
- location/place
- location/store
---
# Gilded Instruments
Music Store
[Location::[[Jalantar]]]


[[Adrienne Spout|Adrienne]] used to work there.

## NPCs

```dataviewjs

dv.list(dv.pages('"People"')
  .where(p => p.type == "npc")
  .where(p => p.Workplace )
  .where(p => p.Workplace.path == dv.current().file.name)
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`))
  
```
