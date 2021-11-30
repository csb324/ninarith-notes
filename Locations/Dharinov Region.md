---
type: location
locationType: Region
Location: [[Eberron]]
tags: 
- location/region/dharinov
---

### Dharinov Region

[[Duchess v'Dharinov]] rules this area

The cities of [[Jezeten]] and [[Deal 'Ras]] sort of merged, to protect themselves from [[Frendrion the Hellrainer]]. 

Jezeten: Political capital
Deal 'Ras: Cultural capital. Site of [[AVAD]].

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