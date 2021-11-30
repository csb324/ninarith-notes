<%* const { Campaign } = window.customJS;
let title = tp.file.title;
if(!tp.file.title) {
	title = await tp.system.prompt("Enter Name");
}

const locationType = await tp.system.suggester(Campaign.locationTypes, Campaign.locationTypes);

const folder = Campaign.getLocationFolder(locationType);
const parentType = Campaign.getLocationParent(locationType);

let parent = '';
if (parentType == "city" || parentType == "country") {
	let options;
	if(parentType == "country") {
		options = Campaign.getCountries();
	} else if (parentType == "city") {
		options = Campaign.getCities();
	}
	options.push("Other");
	parent = await tp.system.suggester(options, options);
}


await tp.file.move(`${folder}/${title}`);

const tags = 'tags';
const dataview = 'dataview';
const lowerType = locationType.toLowerCase();
const placeTag = `location/${lowerType}/${Campaign.lowerKebab(title)}`
-%>
---
type: location
locationType: <% lowerType %>
<% tags %>: 
- <% placeTag %>
---

# <% title %>
<% locationType %>, [Location::[[<% parent %>]]]

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
