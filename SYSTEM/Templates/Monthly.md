<%*
const ts = tp.date.now("YYYY-MM-DD HH:mm");
const monthName = tp.date.now("MMMM YYYY");
const prevMonth = tp.date.now("YYYY-MM", "-1M");
const nextMonth = tp.date.now("YYYY-MM", "+1M");
const year = tp.date.now("YYYY");
const monthNum = tp.date.now("M");
-%>
---
created: <% ts %>
type: monthly
tags: [periodic/monthly]
prev-month: "[[DAILY/Monthly/<% prevMonth %>]]"
cssclasses:
  - dashboard
  - nav-two
  - periodic-monthly
obsidianUIMode: preview
---

# <% monthName %>

`BUTTON[nav_periodic_hub]` `BUTTON[hub_nav_home]`

> [!periodic-nav]
> [[DAILY/Monthly/<% prevMonth %>|← Прошлый месяц]] · **<% tp.date.now("YYYY-MM") %>** · [[DAILY/Monthly/<% nextMonth %>|Следующий месяц →]]

## :LiListChecks: Обещания прошлого месяца

*(из прошлого Monthly — блок «Что меняю в следующем месяце»)*

```dataview
LIST without id L.text
FROM [[DAILY/Monthly/<% prevMonth %>]]
FLATTEN file.lists as L
WHERE contains(L.section.subpath, "Что меняю")
```

## :LiTarget: Цели месяца


## :LiBarChart2: Статистика

```dataview
TABLE type as "Тип", length(rows) as "Создано"
FROM ""
WHERE file.cday.year = <% year %>
  AND file.cday.month = <% monthNum %>
  AND !contains(file.path, "Templates")
  AND type
GROUP BY type
SORT length(rows) DESC
```

## :LiFileText: Permanent за месяц

```dataview
LIST
FROM ""
WHERE type = "permanent"
  AND file.cday.year = <% year %>
  AND file.cday.month = <% monthNum %>
  AND !contains(file.path, "Templates")
SORT file.cday ASC
```

## :LiBookOpen: Прочитано в этом месяце

```dataview
LIST
FROM ""
WHERE type = "literature" AND status = "done"
  AND file.mday.year = <% year %>
  AND file.mday.month = <% monthNum %>
```

## :LiLightbulb: Главные уроки месяца

*Три–пять конкретных пунктов: что понял за месяц.*

- 

## :LiSquarePen: Что меняю в следующем месяце

*Конкретные изменения процесса, не общие пожелания.*

- 

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

