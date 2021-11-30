---
type: org
tags:
- orgs/arkhosian-delegate
---


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
