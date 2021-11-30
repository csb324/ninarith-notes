---
type: location
locationType: place
location: [[Tinzelven]]
tags: 
- location/place/the-thrusting-trumpet
---
# The Thrusting Trumpet

Tavern in [Location::[[Tinzelven]]]. Really the only tavern. Also, the inn. 

[[Left Side Haircut]] performed there

## NPCs

```dataviewjs

dv.list(dv.pages('"People"')
  .where(p => p.type == "npc")
  .where(p => p.Workplace )
  .where(p => p.Workplace.path == dv.current().file.name)
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`))
  
```
