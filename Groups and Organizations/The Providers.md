---
type: org
tags:
- orgs/political/the-providers
---

### The Providers
[Based in::[[Arkhosia]]]

> The Providers are the loyal opposition party. Their message involves bringing more people into the political system, loosening restrictions on voting rights, and exploring land reform projects.

Most popular policy: Land redistribution

SOME Providers want arkhosia to join the [[Mulfara]] side of the [[College-Mulfara Conflict]].


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
