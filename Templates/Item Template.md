<%* 
let title = tp.file.title;
if(!tp.file.title) {
	title = await tp.system.prompt("Enter Name");
}

const folder = "Inventory/Items"
await tp.file.move(`${folder}/${title}`);
-%>
---
type: item
tags:
- item
---

#  <% title %>

[Owned by:: ]
[Origin:: ]

Item

