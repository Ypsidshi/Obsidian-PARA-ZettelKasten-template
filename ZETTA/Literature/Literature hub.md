---
type: hub
tags: [system, literature]
cssclasses: [dashboard, key-page, key-page-literature]
obsidianUIMode: preview
---

# LITERATURE

> Слой источников: книги, статьи, курсы — статусы и очередь чтения.

`BUTTON[hub_nav_home]`

## :LiList: К прочтению

```dataview
LIST
FROM "ZETTA/Literature"
WHERE type = "literature" AND status = "to-read" AND file.name != this.file.name
SORT file.ctime DESC
```

## :LiBookOpen: Читаю сейчас

```dataview
TABLE without id file.link as "Заметка", author as "Автор", progress as "Прогресс"
FROM "ZETTA/Literature"
WHERE type = "literature" AND status = "reading" AND file.name != this.file.name
SORT file.mtime DESC
```

## :LiBookMarked: Прочитано

```dataview
LIST
FROM "ZETTA/Literature"
WHERE type = "literature" AND status = "done" AND file.name != this.file.name
SORT file.mtime DESC
```

## :LiSparkles: Как создавать

- Кнопка **Literature** на [[HUB/Home|Домой]]
- QuickAdd: **New Literature** (если настроен)
- Хаб захвата: [[ZETTA/FLEETING/Fleeting hub|Fleeting hub]]

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
