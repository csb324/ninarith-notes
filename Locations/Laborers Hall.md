---
type: location
locationType: place
tags: 
- location
- location/place
---
# Laborers Hall of Tinzelven

[Location::[[Tinzelven]]]
[Affiliation::[[The Providers]]]

Seems like [[The Providers]] and other political types organize here.

To do:
- [ ] Go to a party!


## NPCs
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