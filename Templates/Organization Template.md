<%* const { Campaign } = window.customJS;
let title = tp.file.title;
if(!tp.file.title) {
	title = await tp.system.prompt("Enter Name");
}

const folder = "Groups\ and\ Organizations"
await tp.file.move(`${folder}/${title}`);

const placeTag = `orgs/${Campaign.lowerKebab(title)}`
-%>
---
type: org
tags:
- <% placeTag %>
---

# <% title %>

A description

## NPCs
```dataviewjs
const { DisplayHelpers } = customJS; DisplayHelpers.listAffiliations(dv);
```
