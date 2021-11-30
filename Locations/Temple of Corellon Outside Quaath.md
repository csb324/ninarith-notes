---
type: location
locationType: place
tags: 
- location/place/temple-of-corellon-quaath
---

# Temple of Corellon
Temple, outside [[Quaath]]. [[Adrienne Spout|Adrienne]] was here recently.

Unusually remote, isolated in the hills.

[Affiliation:: [[Church of Corellon Larethian]]]
[Location::[[Quaath]]]
	
- [ ] get harp repaired
- [ ] return harp
	
## NPCs

```dataviewjs

dv.list(dv.pages('"People"')
  .where(p => p.type == "npc")
  .where(p => p.Home )
  .where(p => p.Home.path == dv.current().file.name)
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`))
  
```
