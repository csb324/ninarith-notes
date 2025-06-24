<%* const { Campaign } = window.customJS;
let title = tp.file.title;
let number = 0;
if(tp.file.title.substring(0, 8) !== 'Untitled') {
	number = title.split('-')[1]
} else {
	number = await tp.system.prompt("Enter Session number");
	title = "session-" + number;
}
number = parseInt(number);
console.log(title);

const folder = 'Session Recaps';

await tp.file.move(`${folder}/${title}`);
-%>
---
type: session
up: [[Session Log]]
prev: [[session-<% number - 1 %>]]
---

# Session <% number %>

For detailed recap, see [[notes-<% number %>]]