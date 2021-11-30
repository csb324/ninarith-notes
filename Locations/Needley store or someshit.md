---
type: location
locationType: store
tags:
- location/place
- location/store
---

# Needley store or someshit
Store
[Location::[[Tinzelven]]]


## NPCs

```dataviewjs

dv.list(dv.pages('"People"')
  .where(p => p.type == "npc")
  .where(p => p.Workplace )
  .where(p => p.Workplace.path == dv.current().file.name)
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`))
  
```

- [ ] learn the actual name of this place.