---
type: org
tags:
- orgs/wayfinders
---

# Wayfinders


The guild of travelers who escort people from city to city. Hired as protection.


## NPCs

```dataviewjs

let affiliated = dv.pages('"People"')
  .where(p => p.Affiliation )
  .where(p => p.Affiliation.path )
  .where((p) => {
  	if(dv.isArray(p.Affiliation)) {
		return p.Affiliation.path.includes(dv.current().file.name)	
	} else {
		return p.Affiliation.path == dv.current().file.name
	}
  });

dv.list(affiliated
  .sort(p => p.file.name, 'asc')
  .map(k => `[[${k.file.name}]]`)
);
```
