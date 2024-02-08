<%* const { Campaign } = window.customJS;
let title = tp.file.title;
if(!tp.file.title) {
	title = await tp.system.prompt("Enter Name");
}

const folder = "Events"
await tp.file.move(`${folder}/${title}`);

const eventStatuses = ["Ongoing", "Upcoming", "Ended"]
const statusTag = await tp.system.suggester(eventStatuses, eventStatuses)

let secondHeading = "Possible outcomes"
if(statusTag == "Ended") {
	secondHeading = "Outcome"
}


const placeTag = `orgs/${Campaign.lowerKebab(title)}`
-%>
---
type: world-event
---

#  <% title %>
[Status::<% statusTag %>]

## <% secondHeading %>