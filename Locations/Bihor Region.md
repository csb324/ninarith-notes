---
type: location
locationType: Region
Location: [[Eberron]]
tags:
- location/region/bihor
---

### Bihor Region
City: [[New Fairhaven]]
(Old capitol: destroyed city of [[Ghursten]])

New Fairhaven was established by [[the Swiftwards]] (insert EYES EMOJI). [[Duke v'Bihor]] lives in new fairhaven. The duke's youngest son is alive and we shall not hear anyone sugggest otherwise!!


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