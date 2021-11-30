---
type: location
locationType: country
region: [[Southern Cities]]
tags: 
- location/country/mulfara
---

# Mulfara

| status	| [[College-Mulfara Conflict]] |
[Location::[[Southern Cities]]]


Tends to be home to "monster" races

Land was set aside after the three-dragons war / second sundering. 

Does slavaadi college want it back? Seems like it! 


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
