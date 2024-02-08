<%* const { Campaign } = window.customJS;
let title = tp.file.title;
let number = 0;
if(tp.file.title !== 'Untitled') {
	number = title.split('-')[1]
} else {
	number = Campaign.getLatestSession() + 1;
	title = "notes-" + number;
}
	console.log(title);

const folder = 'Session Notes'

await tp.file.move(`${folder}/${title}`);
-%>
---
type: detailed-notes
up: [[Session Log]]
prev: [[notes-<% number - 1 %>]]
---

# Detailed Notes: Session <% number %>

For recap, see also: [[session-<% number %>]]
