---
created: 2026-05-02 11:46
type: weekly
tags: [periodic/weekly]
month: "[[2026-05]]"
---

# [WEEK] Неделя 2026-W18

← [[2026-W17|Прошлая неделя]] | [[2026-W19|Следующая неделя]] →

## [GOALS] Цели недели


## [NOTES] Заметки за неделю
```dataview
LIST
FROM ""
WHERE (type = "permanent" OR type = "literature")
  AND !contains(file.path, "Templates")
WHERE file.cday >= date(this.file.name + "-1", "YYYY-'W'ww-c")
  AND file.cday <= date(this.file.name + "-7", "YYYY-'W'ww-c")
SORT file.ctime ASC
```

## [REFLECTION] Рефлексия

**Что получилось:**
- 

**Что не получилось:**
- 

**Что вынести:**
- 
