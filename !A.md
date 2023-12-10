---
tags: structure
---
## Knowledge
- [[-Recherche]]
```dataview
table 
FROM #knowledge
SORT date asc
```
## Personal
```dataview
table 
FROM #personal 
SORT file.name asc
```
## Orga
- [[_transactions]], [[_ledger]]
```dataview
table 
FROM #orga
SORT file.name asc
```
## Projects
```dataview
table 
FROM #project
SORT file.name asc
```
## Structure
```dataview
table 
FROM #structure
SORT file.name asc
```
## Uni Module
```dataview
table semester
FROM #Modul and !"Templates"
WHERE semester
SORT semester desc
```