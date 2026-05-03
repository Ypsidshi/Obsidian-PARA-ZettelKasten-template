---
type: hub
tags: [system, fleeting]
cssclasses: [dashboard, key-page, key-page-fleeting]
obsidianUIMode: preview
---

# FLEETING

> Входящий слой ZETTA: быстрые черновики до разбора в permanent или literature.
>
> Куда дальше: [[HUB/🏠 Home|Домой]] — [[HUB/MOCs/Главный MOC|Главный MOC]]

## Очередь

```dataview
LIST
FROM "ZETTA/FLEETING"
WHERE file.name != this.file.name
SORT file.ctime DESC
```

## Как создавать

- Кнопка **Fleeting** на [[HUB/🏠 Home|Домой]]
- QuickAdd: **New Fleeting**
