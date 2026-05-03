# Second Brain

Obsidian-шаблон: Zettelkasten + PARA, без задач (они в Microsoft To Do).

## Структура

```
1 HUB/      — главный хаб, Inbox, MOCs
2 PARA/     — Projects · Areas · Resources · Archive
3 ZETTA/    — Permanent · Literature · Flashcards
4 DAILY/    — Daily · Weekly · Monthly
5 SYSTEM/   — Templates · Excalidraw · Attachments · Setup.md · Guide.md
```

См. `5 SYSTEM/Setup.md` для установки и `5 SYSTEM/Guide.md` для горячих клавиш.

## Палитра дашборда

CSS-сниппет: `.obsidian/snippets/dashboard.css`. Применяется к заметкам с `cssclasses: [dashboard]` в frontmatter.

| Цвет     | Назначение                                             |
| -------- | ------------------------------------------------------ |
| `#2459B8` | Заголовки (H1, H2, названия callout-карточек, кнопки)  |
| `#e5e4e2` | Фон дашбордов (callouts, panels, dataview-карточки)    |
| `#0F1724` | Текст таблиц: заголовки столбцов и содержимое ячеек    |

Чтобы изменить — правь переменные `--db-title`, `--db-panel`, `--db-table` в верху `dashboard.css`.
