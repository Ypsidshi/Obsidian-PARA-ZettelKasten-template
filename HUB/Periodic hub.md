---
type: hub
tags: [system, periodic]
cssclasses: [dashboard, periodic-hub]
obsidianUIMode: preview
---

# Цикл

> Открыть **текущую** daily, weekly или monthly: Periodic Notes создаст файл по шаблону, если его ещё нет.

`BUTTON[hub_nav_home]`

`BUTTON[pn_daily]` `BUTTON[pn_weekly]` `BUTTON[pn_monthly]`

## :LiInfo: Подсказка

Те же действия доступны из палитры команд: *Periodic Notes: Open daily note*, *Open weekly note*, *Open monthly note*.


```meta-bind-button
label: Daily
icon: lucide-calendar
hidden: true
id: pn_daily
style: primary
tooltip: Открыть или создать daily на сегодня
actions:
  - type: command
    command: periodic-notes:open-daily-note
```

```meta-bind-button
label: Weekly
icon: lucide-calendar-range
hidden: true
id: pn_weekly
style: primary
tooltip: Открыть или создать weekly на эту неделю
actions:
  - type: command
    command: periodic-notes:open-weekly-note
```

```meta-bind-button
label: Monthly
icon: lucide-calendar-days
hidden: true
id: pn_monthly
style: primary
tooltip: Открыть или создать monthly на этот месяц
actions:
  - type: command
    command: periodic-notes:open-monthly-note
```

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
