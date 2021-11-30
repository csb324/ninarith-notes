---
type: location
locationType: city
tags: 
- location/city/tinzelven
---
# Tinzelven
**City, [Location::[[Arkhosia]]]**
Outside of [[Jalantar]]

* The kids at [[Redscale]] called it twiddletown because it's very small
* Stores
	* There's an armory run by a [[dwarf who seems to like us]] (and [[Hugh]] in particular)
	* Clothing store run by a [[Victor]] (who is afraid of [[Hugh]] but likes us anyway) ([[Needley store or someshit]])
	* [[Tack & Trade]]: Insane corner store that tried to sell us a keychain for like forty bucks. 


## NPCs

```dataviewjs

dv.list(dv.pages('"People"')
  .where(p => p.type == "npc")
  .where(p => p.Home )
  .where(p => p.Home.path == dv.current().file.name)
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`))
  
```


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
