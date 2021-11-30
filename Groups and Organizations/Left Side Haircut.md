---
type: org
tags:
- orgs/left-side-haircut
---

# Left Side Haircut

[Based in::[[Redscale]]]

Band of students from [[Redscale]]. 

Singer / Tambourine: [[Juliette]]
Drums: [[Gunner]]
Lyre: some girl, idk, did i get her name? whatever.


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
