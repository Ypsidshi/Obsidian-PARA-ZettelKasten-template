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
prev-month: "[[<% prevMonth %>]]"
---

# 🗓️ <% monthName %>

← [[<% prevMonth %>|Прошлый месяц]] | [[<% nextMonth %>|Следующий месяц]] →

## 🔄 Что я обещал изменить в прошлом месяце
*(подтягивается из прошлого Monthly — перечитай и оцени)*
```dataview
LIST without id L.text
FROM [[<% prevMonth %>]]
FLATTEN file.lists as L
WHERE contains(L.section.subpath, "Что меняю")
```

## 🎯 Цели месяца


## 📊 Статистика
```dataview
TABLE length(rows) as "Создано"
FROM ""
WHERE file.cday.year = <% year %>
  AND file.cday.month = <% monthNum %>
  AND !contains(file.path, "Templates")
GROUP BY type
```

## 📝 Permanent-заметки месяца
```dataview
LIST
FROM ""
WHERE type = "permanent"
  AND file.cday.year = <% year %>
  AND file.cday.month = <% monthNum %>
  AND !contains(file.path, "Templates")
SORT file.ctime ASC
```

## 📚 Прочитано в этом месяце
```dataview
LIST
FROM ""
WHERE type = "literature" AND status = "done"
  AND file.mday.year = <% year %>
  AND file.mday.month = <% monthNum %>
```

## 🌟 Главные уроки месяца
*3–5 пунктов. Что я понял, чего не знал месяц назад. Конкретно.*
- 

## 🔄 Что меняю в следующем месяце
*Конкретные изменения. Не "буду больше читать", а "ставлю напоминание читать 20 минут после завтрака".*
- 
