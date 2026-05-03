---
type: hub
tags: [system, fleeting]
cssclasses: [dashboard, key-page, key-page-fleeting]
obsidianUIMode: preview
---

# FLEETING

> Входящий слой ZETTA: быстрые черновики до разбора в permanent или literature.

`BUTTON[hub_nav_home]`

## :LiList: Очередь

```dataview
LIST
FROM "ZETTA/FLEETING"
WHERE file.name != this.file.name
SORT file.ctime DESC
```

## :LiSparkles: Как создавать

- Кнопка **Fleeting** на [[HUB/Home|Домой]]
- QuickAdd: **New Fleeting**

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
