<%* const { Campaign } = window.customJS;
let title = tp.file.title;
if(tp.file.title == "Untitled") {
	title = await tp.system.prompt("Enter Name");
}

const races = Campaign.getValues("People", "Race")
races.push("Other");
const raceTag = await tp.system.suggester(races, races);

const locations = await Campaign.getLocations();
locations.push('Other');
const location = await tp.system.suggester(locations, locations);
const folder = 'People';

const aliveStatusTag = await tp.system.suggester(Campaign.aliveStatuses, Campaign.aliveStatuses)
const relationshipTag = await tp.system.suggester(Campaign.relationships, Campaign.relationships)


await tp.file.move(`${folder}/${title}`);

const tags = 'tags';
const dataview = 'dataview';
-%>
---
type: npc
<% tags %>: 
- npc
---

# <% title %>
[Status::<% aliveStatusTag %>]
[Race::<% raceTag %>]
[Relationship::<% relationshipTag %>]
[Home::[[<% location %>]]]

Some quick description
