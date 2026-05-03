<%*
const today = tp.date.now("YYYY-MM-DD");
const yesterday = tp.date.now("YYYY-MM-DD", -1);
const tomorrow = tp.date.now("YYYY-MM-DD", 1);
const week = tp.date.now("YYYY-[W]ww");
const month = tp.date.now("YYYY-MM");
const heading = tp.date.now("dddd, DD MMMM YYYY");
const ts = tp.date.now("YYYY-MM-DD HH:mm");
-%>
---
created: <% ts %>
type: daily
tags: [periodic/daily]
week: "[[<% week %>]]"
month: "[[<% month %>]]"
---

# [DATE] <% heading %>

← [[<% yesterday %>|Вчера]] | [[<% tomorrow %>|Завтра]] →

## [FOCUS] Фокус дня
*Что сегодня главное? Одна-две вещи. Не задачи, а намерение.*


## [NOTES] Заметки и мысли


## [FLEETING] Fleeting сейчас
```dataview
LIST
FROM "ZETTA/FLEETING"
WHERE file.name != "Fleeting hub"
SORT file.ctime ASC
```

## [LINKS] Заметки, созданные сегодня
```dataview
LIST
FROM ""
WHERE file.cday = date("<% today %>")
  AND file.name != this.file.name
  AND !contains(file.path, "Templates")
SORT file.ctime ASC
```

## [CARDS] Карточки на сегодня
*`Ctrl+Shift+R` — начать повторение*

## [SUMMARY] Итог дня
