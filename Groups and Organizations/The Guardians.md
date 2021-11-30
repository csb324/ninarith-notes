---
type: org
tags:
- orgs/political/the-guardians
---

### The Guardians

[Based in::[[Arkhosia]]]

> The Guardians stand for the status quo. Arkhosia is a very successful nation, and they see little need for things to change. They've quashed attempts at reform, strengthened the power of the landed aristocracy, and worked to keep the franchise from expanding. Dragonborn make up the majority of the aristocracy in Arkhosia, and dominate the Guardian party.

Most popular policy: Don't change shit.

SOME Guardians want Arkhosia to further lean into the [[College-Mulfara Conflict]], I think to piss off Eberron.

Important people:
- [[Quillette Guruden]]

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
