---
type: org
tags:
- orgs/political/the-circle
---

# The Circle
[Based in::[[Arkhosia]]]

The ruling body of [[Arkhosia]]. It has five members, who are elected via proportional representation.


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
