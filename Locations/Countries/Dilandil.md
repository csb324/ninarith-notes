---
type: location
locationType: country
tags: 
- location/country/dilandil
---
# Dilandil
Country, [Location::[[Major Nations]]]

Elves live here, mostly. 


## Points of Interest
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

## NPCs

```dataviewjs

dv.list(dv.pages('"People"')
  .where(p => p.type == "npc")
  .where(p => p.Home )
  .where(p => p.Home.path == dv.current().file.name)
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`))
  
```
