---
type: location
locationType: Region
Location: [[Eberron]]
tags: 
- location/region/luthei
---

### Luthei Region
Most powerful, most fucked.

[[Duke v'Luthei]] rules from the palace. Intensely private. Almost impossible to penetrate without paperwork. Extraordinarily dangerous.

```dataviewjs
dv.list(
	dv.pages('[[' + dv.current().file.name + ']]')
	.where(p => p.type == "location")
	.where(p => p.Location)
  .where((p) => {
  	if(dv.isArray(p.Location)) {
		return p.Location.path.includes(dv.current().file.name)	
	} else {
		return p.Location.path == dv.current().file.name
	}
  })
  	.sort(p => p.file.name, 'asc')
	.map(k => `[[${k.file.name}]]`))

```