---
tags:
  - Knowledge
aliases:
---
**Procedural Knowledges**
- [[Nvim Knowledge|NVIM]]
	- [[Nvim_Shortcuts.png]]
- [[Bash Knowledge|BASH]]
- [[Git Knowledge|GIT]]
- [[Regular expressions|REGEX]]
- [[SQL Knowledge|SQL]]
- [[(I) Python]]
	- [[Py.Numpy Knowledge|NUMPY]]

> [!info]+ <font color="cc55cc" size=4px>Themen</font>
> ```dataview
> table 
> FROM !"Templates"
> WHERE startswith(file.name, "(I)")
>SORT file.name asc
> ```

## <font color="teal">Knowledge</font>
```dataview
table Thema, date
FROM !"Templates"
WHERE contains(join(thema), "(I)") or contains(join(thema), "!Informatik")
SORT thema, file.name asc
```
## <font color="#339955">Reads</font>
```dataview
table erscheinungsdatum as Jahr, Autor, Thema, seiten
FROM #Reads and !"Templates"
WHERE contains(join(thema), "(I)") or contains(join(thema), "!Informatik")
SORT thema, erscheinungsdatum desc
```
### Files
```query
path:Reads/Tech
```
## <font color="#ff3500">Personen</font>
```dataview
table Geburtsdatum, Tod, Thema, Aliases
FROM #Person
WHERE contains(join(thema), "(I)") or contains(join(thema), "!Informatik")
SORT geburtsdatum desc
```