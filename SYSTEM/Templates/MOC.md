---
created: 2026-05-02 11:46
type: moc
tags: [moc]
cssclasses:
  - dashboard
  - nav-two
  - key-page
  - key-page-moc
obsidianUIMode: preview
---

# <% tp.file.title %>

`BUTTON[hub_nav_main_moc]` `BUTTON[hub_nav_home]`

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

```meta-bind-button
label: Домой
icon: lucide-home
hidden: true
id: hub_nav_home
style: primary
tooltip: Открыть Home
actions:
  - type: open
    link: "[[HUB/Home]]"
```

```meta-bind-button
label: К главному MOC
icon: lucide-map
hidden: true
id: hub_nav_main_moc
style: default
tooltip: Открыть Главный MOC
actions:
  - type: open
    link: "[[HUB/MOCs/Главный MOC|Главный MOC]]"
```
