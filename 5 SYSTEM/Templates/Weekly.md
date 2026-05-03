<%*
const ts = tp.date.now("YYYY-MM-DD HH:mm");
const week = tp.date.now("YYYY-[W]ww");
const prevWeek = tp.date.now("YYYY-[W]ww", -7);
const nextWeek = tp.date.now("YYYY-[W]ww", 7);
const month = tp.date.now("YYYY-MM");
-%>
---
created: <% ts %>
type: weekly
tags: [periodic/weekly]
month: "[[<% month %>]]"
---

# 📆 Неделя <% week %>

← [[<% prevWeek %>|Прошлая неделя]] | [[<% nextWeek %>|Следующая неделя]] →

## 🎯 Цели недели


## 📝 Заметки за неделю
```dataview
LIST
FROM ""
WHERE (type = "permanent" OR type = "literature")
  AND !contains(file.path, "Templates")
WHERE file.cday >= date(this.file.name + "-1", "YYYY-'W'ww-c")
  AND file.cday <= date(this.file.name + "-7", "YYYY-'W'ww-c")
SORT file.ctime ASC
```

## 🤔 Рефлексия

**Что получилось:**
- 

**Что не получилось:**
- 

**Что вынести:**
- 
