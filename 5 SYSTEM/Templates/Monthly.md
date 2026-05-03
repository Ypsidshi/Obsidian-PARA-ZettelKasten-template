---
created: 2026-05-02 12:40
type: monthly
tags: [periodic/monthly]
prev-month: "[[2026-05]]"
---

# 🗓️ May 2026

← [[2026-05|Прошлый месяц]] | [[2026-05|Следующий месяц]] →

## 🔄 Что я обещал изменить в прошлом месяце
*(подтягивается из прошлого Monthly — перечитай и оцени)*
```dataview
LIST without id L.text
FROM [[2026-05]]
FLATTEN file.lists as L
WHERE contains(L.section.subpath, "Что меняю")
```

## 🎯 Цели месяца


## 📊 Статистика
```dataview
TABLE length(rows) as "Создано"
FROM ""
WHERE file.cday.year = 2026
  AND file.cday.month = 5
  AND !contains(file.path, "Templates")
GROUP BY type
```

## 📝 Permanent-заметки месяца
```dataview
LIST
FROM ""
WHERE type = "permanent"
  AND file.cday.year = 2026
  AND file.cday.month = 5
  AND !contains(file.path, "Templates")
SORT file.ctime ASC
```

## 📚 Прочитано в этом месяце
```dataview
LIST
FROM ""
WHERE type = "literature" AND status = "done"
  AND file.mday.year = 2026
  AND file.mday.month = 5
```

## 🌟 Главные уроки месяца
*3–5 пунктов. Что я понял, чего не знал месяц назад. Конкретно.*
- 

## 🔄 Что меняю в следующем месяце
*Конкретные изменения. Не "буду больше читать", а "ставлю напоминание читать 20 минут после завтрака".*
- 
