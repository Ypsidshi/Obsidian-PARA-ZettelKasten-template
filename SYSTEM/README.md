---
cssclasses: [accent-nav-h2]
---

# Second Brain

Obsidian-шаблон: Zettelkasten + PARA, без задач (они в Microsoft To Do).

## Структура

```
HUB/      — Dashboard (⌂ Home), [[HUB/Periodic hub|Periodic hub]], MOCs
PARA/     — Projects · Areas · Resources · Archive
ZETTA/    — FLEETING (черновики) · Permanent · Literature · Flashcards
DAILY/    — Daily · Weekly · Monthly
SYSTEM/   — Templates · Excalidraw · Attachments · Setup.md · Guide.md
```

См. `SYSTEM/Setup.md` для установки и `SYSTEM/Guide.md` для горячих клавиш.

## Палитра дашборда

CSS-сниппет: `.obsidian/snippets/dashboard.css`.

- **Home:** `cssclasses: [home, dashboard]` — заголовок Second Brain, панель кнопок, секции.
- **Ключевые hub-страницы** (тот же синий акцент, карточки Dataview, без эмодзи): `cssclasses: [dashboard, key-page, key-page-fleeting]` для [[ZETTA/FLEETING/Fleeting hub|Fleeting hub]] и `[dashboard, key-page, key-page-moc]` для [[HUB/MOCs/Главный MOC|Главный MOC]].
- **Документация SYSTEM:** `cssclasses: [accent-nav-h2]` — только синие H2 в духе Home, без скрытия frontmatter и без центрирования как у dashboard.


Не используется:

| Цвет      | Назначение                                            |
| --------- | ----------------------------------------------------- |
| `#2459B8` | Заголовки (H1, H2, названия callout-карточек, кнопки) |
| `#e5e4e2` | Фон дашбордов (callouts, panels, dataview-карточки)   |
| `#0F1724` | Текст таблиц: заголовки столбцов и содержимое ячеек   |

Чтобы изменить — правь переменные `--db-title`, `--db-panel`, `--db-table` в верху `dashboard.css`.
