# Second Brain

Obsidian-шаблон: Zettelkasten + PARA, без задач (они в Microsoft To Do).

## Структура

```
HUB/      — главный хаб, Inbox, MOCs
PARA/     — Projects · Areas · Resources · Archive
ZETTA/    — Permanent · Literature · Flashcards
DAILY/    — Daily · Weekly · Monthly
SYSTEM/   — Templates · Excalidraw · Attachments · Setup.md · Guide.md
```

См. `SYSTEM/Setup.md` для установки и `SYSTEM/Guide.md` для горячих клавиш.

## Палитра дашборда

CSS-сниппет: `.obsidian/snippets/dashboard.css`. Применяется к заметкам с `cssclasses: [dashboard]` в frontmatter.


Не используется:

| Цвет      | Назначение                                            |
| --------- | ----------------------------------------------------- |
| `#2459B8` | Заголовки (H1, H2, названия callout-карточек, кнопки) |
| `#e5e4e2` | Фон дашбордов (callouts, panels, dataview-карточки)   |
| `#0F1724` | Текст таблиц: заголовки столбцов и содержимое ячеек   |

Чтобы изменить — правь переменные `--db-title`, `--db-panel`, `--db-table` в верху `dashboard.css`.
