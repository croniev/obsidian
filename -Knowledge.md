---
tags:
  - Knowledge
---
```dataview
table date
FROM !"Templates" AND !#Reads AND !#Text AND !#lev AND !#Projekt
WHERE thema
WHERE !contains(join(thema), "(") AND !contains(join(thema), "!")
SORT date desc
```

