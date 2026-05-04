<%*
const today = tp.date.now("YYYY-MM-DD");
const week = tp.date.now("YYYY-[W]WW");
const month = tp.date.now("YYYY-MM");
const heading = tp.date.now("dddd, DD MMMM YYYY");
const ts = tp.date.now("YYYY-MM-DD HH:mm");
-%>
---
created: <% ts %>
type: daily
tags: [periodic/daily]
journal: personal
journal-start-date: <% tp.file.title %>
journal-end-date: <% tp.file.title %>
journal-section: day
week: "[[DAILY/Weekly/<% week %>]]"
month: "[[DAILY/Monthly/<% month %>]]"
cssclasses:
  - dashboard
  - nav-two
  - periodic-daily
obsidianUIMode: preview
---

# <% heading %>

`BUTTON[nav_periodic_hub]` `BUTTON[hub_nav_home]`

```calendar-nav
```

## :LiCircleDot: Фокус дня

*Одно–два намерения на день (не список задач).*

## :LiPenLine: Заметки и мысли


## :LiInbox: Fleeting сейчас

```dataview
LIST
FROM "ZETTA/FLEETING"
WHERE file.name != "Fleeting hub"
SORT file.ctime ASC
```

## :LiCalendarPlus: Создано сегодня

```dataview
LIST
FROM ""
WHERE file.cday = date(this.file.name)
  AND file.name != this.file.name
  AND !contains(file.path, "Templates")
SORT file.ctime ASC
```

## :LiLayers: Карточки на сегодня

*Spaced Repetition: горячая клавиша из настроек плагина.*

## :LiNotebookPen: Итог дня


```meta-bind-button
label: Journal
icon: lucide-notebook-pen
hidden: true
id: nav_periodic_hub
style: primary
tooltip: Хаб Daily / Weekly / Monthly (Periodic Notes)
actions:
  - type: open
    link: "[[HUB/Periodic hub]]"
```

```meta-bind-button
label: Домой
icon: lucide-home
hidden: true
id: hub_nav_home
style: default
tooltip: Открыть Home
actions:
  - type: open
    link: "[[HUB/Home]]"
```
