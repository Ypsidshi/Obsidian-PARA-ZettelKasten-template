<%*
const ts = tp.date.now("YYYY-MM-DD HH:mm");
const month = tp.date.now("YYYY-MM");
const title = tp.file.title;
let prevW = "", nextW = "", weekStart = "", weekEnd = "";
try {
  const moment = window.moment;
  if (moment && /^\d{4}-W\d{2}$/i.test(title)) {
    const base = moment(title, "GGGG-[W]WW", true);
    if (base.isValid()) {
      prevW = base.clone().subtract(1, "week").format("GGGG-[W]WW");
      nextW = base.clone().add(1, "week").format("GGGG-[W]WW");
      weekStart = base.clone().startOf("isoWeek").format("YYYY-MM-DD");
      weekEnd = base.clone().endOf("isoWeek").format("YYYY-MM-DD");
    }
  }
} catch (e) {}
-%>
---
created: <% ts %>
type: weekly
tags: [periodic/weekly]
month: "[[DAILY/Monthly/<% month %>]]"
cssclasses:
  - dashboard
  - nav-two
  - periodic-weekly
obsidianUIMode: preview
---

# Неделя <% title %>

`BUTTON[nav_periodic_hub]` `BUTTON[hub_nav_home]`

<%* if (prevW && nextW) { -%>
> [!periodic-nav]
> [[DAILY/Weekly/<% prevW %>|← Прошлая неделя]] · **<% title %>** · [[DAILY/Weekly/<% nextW %>|Следующая неделя →]]
<%* } else { -%>
*Ссылки «прошлая / следующая неделя» появятся, когда имя файла в формате `YYYY-Www`.*
<%* } -%>

## :LiTarget: Цели недели


## :LiFiles: Заметки за неделю

*Permanent и literature за интервал ISO-недели (даты подставляются при создании заметки из шаблона).*

<%* if (weekStart && weekEnd) { -%>
```dataview
LIST
FROM ""
WHERE (type = "permanent" OR type = "literature")
  AND file.cday >= date("<% weekStart %>")
  AND file.cday <= date("<% weekEnd %>")
  AND !contains(file.path, "Templates")
SORT file.cday ASC
```
<%* } else { -%>
*Не удалось вычислить границы недели по имени файла — проверь формат `YYYY-Www` или открой заметку заново из Periodic Notes.*
<%* } -%>

## :LiMessagesSquare: Рефлексия

**Что получилось:**

- 

**Что не получилось:**

- 

**Что вынести дальше:**

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

