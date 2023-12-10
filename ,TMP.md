---
tags: orga
---
```dataview
table date
FROM #TMP AND !"Templates" AND !#Oldies
SORT date desc
```

## Old
```dataview
table date
FROM #TMP AND #Oldies AND !"Templates"
SORT date desc
```