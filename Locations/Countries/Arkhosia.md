---
type: location
locationType: country
tags: 
- location/country/arkhosia
---

# Arkhosia
Country, [Location::[[Southern Cities]]]

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


# Politics

* Not currently at war
	* Currently *involved* in the war between the [[Slavaadi College]] and [[Mulfara]], on the side of the college.
* Current ruling party: [[The Guardians]]
* Ruling body: [[The Circle]] 
	* Currently 3 guardians, 2 providers
* Proportional representation.
* Each party has ~100 [[Arkhosian Delegates|Arkhosian Delegates]]


#### Suffrage
* Land owners > 800 acres 
* Land owners < 800 acres AND able to pay 2,000 gold tax
* [[The Providers]] don't like this, by the way. 


## Political Parties of Arkhosia

|name 				| major	 | basic position |
|-------------------|--------|-----------------|
|[[The Guardians]]	| Major	 | Conservative		|
|[[The Providers]]	| Major	 | Expanded voting rights |
|Kingmakers			| Minor	 | They want [[Faedwan Drumsbea]] to become queen of Arkhosia. She does not seem to want this. 	|
|Insurgency			| Minor	 | Radical! Violent! They want a big parliament! They're down to assassinate people. Sort of a boogeyman. Maybe a rumor, invented by [[The Guardians]] to make the other guys look bad. But pamphlets exist. 	|
|Dairymen			| Minor	 | These dudes love yaks, and farming. They just want the government to make it easier and more profitable to raise yaks. 
|Dovetails			| Minor	| Radical pacifists. |
|Hawktails			| Minor	| Violently radical pacifists. It's illegal to be this pacifist. |

# Economy
Yaks.
