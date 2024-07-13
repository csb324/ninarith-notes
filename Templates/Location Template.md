<%* const { Campaign } = window.customJS;
let title = tp.file.title;
if(!tp.file.title || tp.file.title == "Untitled") {
	title = await tp.system.prompt("Enter Name");
}

const locationType = await tp.system.suggester(Campaign.locationTypes, Campaign.locationTypes);

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

const folder = Campaign.getLocationFolder(locationType, parent);

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
const { DisplayHelpers } = customJS; DisplayHelpers.listNPCs(dv);
```

## Points of Interest
```dataviewjs
const { DisplayHelpers } = customJS; DisplayHelpers.listPointsOfInterest(dv);
```
