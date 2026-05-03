---
type: system-doc
cssclasses: [no-inline-title]
---

# 🛠️ Setup / Установка

## 🇷🇺 Русский

### Что это
Second Brain — твоя база знаний на Obsidian. Сочетает **Zettelkasten** (атомарные заметки + связи) и **PARA** (только верхний уровень).

### Структура папок
```
1 HUB/      — главный хаб, MOCs, Inbox
2 PARA/     — Projects · Areas · Resources · Archive
3 ZETTA/    — Permanent · Literature · Flashcards
4 DAILY/    — Daily · Weekly · Monthly заметки
5 SYSTEM/   — Templates · MOCs · Excalidraw · Attachments · документация
```
Цифровые префиксы — для порядка в сайдбаре (Obsidian сортирует алфавитно).

### Установка плагинов
Settings → Community plugins → Browse:

**Ядро:**
- Templater
- Dataview
- Periodic Notes
- Spaced Repetition
- Homepage
- QuickAdd
- Meta Bind

**Утилиты:**
- Omnisearch
- Excalidraw
- Tag Wrangler
- Paste Image Rename

### Базовая настройка

**Files & Links:**
- Default location for new notes: `1 HUB/Inbox`
- New attachments: `5 SYSTEM/Attachments`
- Use Wikilinks: ON

**Core plugins:** отключи `Daily notes` и `Templates` (заменены на Periodic Notes и Templater).

**Templater:**
- Template folder: `5 SYSTEM/Templates`
- Trigger Templater on new file creation: ON
- Folder Templates:
  - `1 HUB/Inbox` → `Fleeting.md`
  - `3 ZETTA/Permanent` → `Permanent.md`
  - `3 ZETTA/Literature` → `Literature.md`
  - `3 ZETTA/Flashcards` → `Flashcard.md`
  - `1 HUB/MOCs` → `MOC.md`

**Periodic Notes:**
- Daily — folder `4 DAILY/Daily`, format `YYYY-MM-DD`, template `5 SYSTEM/Templates/Daily.md`
- Weekly — folder `4 DAILY/Weekly`, format `YYYY-[W]ww`, template `Weekly.md`
- Monthly — folder `4 DAILY/Monthly`, format `YYYY-MM`, template `Monthly.md`

**Dataview:** включи JavaScript Queries и Inline JavaScript Queries.

**Spaced Repetition:**
- Flashcard tag: `#flashcards`
- Inline separator: `::`
- Reversed separator: `:::`

**QuickAdd:** создай два Choice типа Template — `New Permanent` (папка `3 ZETTA/Permanent`) и `New Literature` (папка `3 ZETTA/Literature`).

**Homepage:**
- Homepage: `1 HUB/🏠 Home`
- Open on startup: ON
- Open in mode: Reading view

**CSS:** Settings → Appearance → CSS Snippets → включи `dashboard`.

---

## 🇬🇧 English

### What this is
Second Brain is your Obsidian knowledge base. It combines **Zettelkasten** (atomic notes + links) and **PARA** (top level only).

### Folder structure
```
1 HUB/      — main dashboard, MOCs, Inbox
2 PARA/     — Projects · Areas · Resources · Archive
3 ZETTA/    — Permanent · Literature · Flashcards
4 DAILY/    — Daily · Weekly · Monthly journal
5 SYSTEM/   — Templates · MOCs · Excalidraw · Attachments · docs
```
Numeric prefixes enforce sidebar order (Obsidian sorts alphabetically).

### Install plugins
Settings → Community plugins → Browse:

**Core:** Templater · Dataview · Periodic Notes · Spaced Repetition · Homepage · QuickAdd · Meta Bind

**Utilities:** Omnisearch · Excalidraw · Tag Wrangler · Paste Image Rename

### Base configuration

**Files & Links:**
- Default new notes folder: `1 HUB/Inbox`
- New attachments: `5 SYSTEM/Attachments`
- Use Wikilinks: ON

**Core plugins:** disable `Daily notes` and `Templates` (replaced by Periodic Notes and Templater).

**Templater:**
- Template folder: `5 SYSTEM/Templates`
- Trigger on new file creation: ON
- Folder Templates:
  - `1 HUB/Inbox` → `Fleeting.md`
  - `3 ZETTA/Permanent` → `Permanent.md`
  - `3 ZETTA/Literature` → `Literature.md`
  - `3 ZETTA/Flashcards` → `Flashcard.md`
  - `1 HUB/MOCs` → `MOC.md`

**Periodic Notes:**
- Daily — `4 DAILY/Daily`, format `YYYY-MM-DD`
- Weekly — `4 DAILY/Weekly`, format `YYYY-[W]ww`
- Monthly — `4 DAILY/Monthly`, format `YYYY-MM`
- Templates from `5 SYSTEM/Templates/`

**Dataview:** enable JavaScript Queries + Inline JavaScript Queries.

**Spaced Repetition:**
- Flashcard tag: `#flashcards`
- Inline separator: `::`
- Reversed separator: `:::`

**QuickAdd:** create two Template choices — `New Permanent` (folder `3 ZETTA/Permanent`) and `New Literature` (folder `3 ZETTA/Literature`).

**Homepage:**
- Homepage: `1 HUB/🏠 Home`
- Open on startup: ON
- Open in mode: Reading view

**CSS:** Settings → Appearance → CSS Snippets → enable `dashboard`.
