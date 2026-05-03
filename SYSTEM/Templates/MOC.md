---
created: 2026-05-02 11:46
type: moc
tags: [moc]
---

# <% tp.file.title %>

## :LiStickyNote: О теме
*Краткое описание области и зачем эта карта.*


## :LiFolderTree: Подтемы / разделы
*Иерархия темы. Заголовки = подтемы, под ними — ссылки на конкретные Permanent/Literature заметки.*

### 
- 

### 
- 

## :LiLink2: Связанные MOC
*Соседние области знания.*
- 

## :LiHash: Все заметки по теме (авто)
*Замени `тема` на свой тег.*
```dataview
LIST
FROM #тема  
WHERE !contains(file.path, "Templates")
SORT file.ctime DESC
```
