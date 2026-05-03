---
type: guide
tags: [system, plugins, configuration]
---

# Конфигурация плагинов

Полный список плагинов и путей для корректной работы системы.

---

## 🔧 Ключевые плагины

### 1. **Templater** (v1.16.0+)
Создание заметок по шаблонам с динамическим содержимым.

**Путь к шаблонам (обязательно):**
```
SYSTEM/Templates
```

**Folder Templates (Templater):**
| Папка | Шаблон |
|-------|--------|
| DAILY/Daily | SYSTEM/Templates/Daily.md |
| ZETTA/Permanent | SYSTEM/Templates/Permanent.md |
| ZETTA/Literature | SYSTEM/Templates/Literature.md |
| ZETTA/Flashcards | SYSTEM/Templates/Flashcard.md |
| HUB/Inbox | SYSTEM/Templates/Fleeting.md |

**Иконки шаблонов:**
```json
"templates_pairs": [
  ["🏠", "HUB"],
  ["📝", "DAILY"],
  ["🔗", "ZETTA"],
  ["📚", "ZETTA/Literature"]
]
```

**Settings:**
- ✅ Trigger on file creation
- ✅ Enable folder templates
- ✅ Enable system commands (если нужны script commands)

---

### 2. **Periodic Notes** (v0.0.52+)
Автоматическое создание дневников, еженедельных и ежемесячных обзоров.

**Daily Notes:**
```json
{
  "format": "YYYY-MM-DD",
  "template": "SYSTEM/Templates/Daily.md",
  "folder": "DAILY/Daily",
  "enabled": true
}
```

**Weekly Notes:**
```json
{
  "format": "YYYY-[W]WW",
  "template": "SYSTEM/Templates/Weekly.md",
  "folder": "DAILY/Weekly",
  "enabled": true
}
```

**Monthly Notes:**
```json
{
  "format": "YYYY-MM",
  "template": "SYSTEM/Templates/Monthly.md",
  "folder": "DAILY/Monthly",
  "enabled": true
}
```

**Hotkeys:**
- Daily Note: `Ctrl+Shift+D`
- Weekly Note: `Ctrl+Shift+W`
- Monthly Note: `Ctrl+Shift+M`

---

### 3. **QuickAdd** (v10.0.0+)
Быстрое создание заметок с предустановленными шаблонами.

**Choice 1: New Permanent Note**
```json
{
  "type": "Template",
  "name": "New Permanent",
  "templatePath": "SYSTEM/Templates/Permanent.md",
  "folder": "ZETTA/Permanent",
  "fileNameFormat": "{{VALUE:Название заметки}}"
}
```

**Choice 2: New Literature Note**
```json
{
  "type": "Template",
  "name": "New Literature",
  "templatePath": "SYSTEM/Templates/Literature.md",
  "folder": "ZETTA/Literature",
  "fileNameFormat": "{{VALUE:Автор — Название}}"
}
```

**Choice 3: New Fleeting Note**
```json
{
  "type": "Template",
  "name": "New Fleeting",
  "templatePath": "SYSTEM/Templates/Fleeting.md",
  "folder": "HUB/Inbox",
  "fileNameFormat": "{{DATE:YYYY-MM-DD HH:mm}} {{VALUE:Суть идеи}}"
}
```

**Choice 4: New MOC**
```json
{
  "type": "Template",
  "name": "New MOC",
  "templatePath": "SYSTEM/Templates/MOC.md",
  "folder": "HUB/MOCs",
  "fileNameFormat": "{{VALUE:Название MOC}}"
}
```

**Choice 5: New Flashcard**
```json
{
  "type": "Template",
  "name": "New Flashcard",
  "templatePath": "SYSTEM/Templates/Flashcard.md",
  "folder": "ZETTA/Flashcards",
  "fileNameFormat": "{{DATE:YYYY-MM-DD}} {{VALUE:Тема}}"
}
```

**Hotkey:**
- Open QuickAdd menu: `Ctrl+Shift+A`

**Settings:**
- ✅ Input prompt: Single-line
- ✅ Use selection as capture value
- ✅ Announce updates: Major

---

### 4. **Homepage** (v3.5.0+)
Выбор стартовой страницы при открытии хранилища.

**Конфиг:**
```json
{
  "homepageFilePath": "HUB/🏠 Home",
  "openOnStartup": true,
  "pinHomepageTab": true,
  "hotkeyScope": "global"
}
```

**Hotkey:**
- Open homepage: `Ctrl+Home`

---

### 5. **Meta Bind** (v0.30.0+)
Создание интерактивных кнопок на Dashboard.

**Dashboard buttons в HUB/🏠 Home.md:**

Кнопки должны быть определены в начале файла:
```
BUTTON[id=daily-btn, label="📅 Daily Note", action="periodic-notes:open-daily"]
BUTTON[id=quick-btn, label="⚡ QuickAdd", action="quickadd:open-quick"]
BUTTON[id=perm-btn, label="🔗 New Permanent", action="quickadd:choice:New Permanent"]
```

**Использование в тексте:**
```
BUTTON[daily-btn]
BUTTON[quick-btn]
```

**Settings:**
- ✅ Preview mode rendering
- ✅ Highlight buttons on hover

---

### 6. **Dataview** (v0.5.47+)
Динамические запросы и списки в markdown.

**Примеры для Dashboard:**

Недавние заметки:
```dataview
LIST
FROM "ZETTA"
WHERE type = "permanent"
SORT created DESC
LIMIT 5
```

Заметки в обработке:
```dataview
LIST
FROM "HUB/Inbox"
WHERE contains(tags, "to-process")
```

Текущие проекты:
```dataview
TABLE status, created
FROM "PARA"
WHERE status != "archived"
GROUP BY status
```

**Settings:**
- ✅ Render inline expressions
- ✅ Render inline field icons
- ✅ Pretty rendering

---

### 7. **Custom Sort** (v1.1.0+)
Пользовательская сортировка папок (без цифровых префиксов).

**`.sortspec` файл в корне хранилища:**
```
HUB
PARA
ZETTA
DAILY
SYSTEM
```

**Settings:**
- Sort specs file: `.sortspec` (автоматически)
- Enable custom sorting: ✓

---

### 8. **Omnisearch** (v1.13.0+)
Полнотекстовый поиск по хранилищу.

**Hotkey:**
- Open search: `Ctrl+K`

**Settings:**
- ✅ Show in search modal
- ✅ Exclude extensions: `.obsidian`
- ✅ Render markdown in search results

**Exclude folders:**
```
.obsidian
.trash
```

---

## 📚 Вспомогательные плагины

### 9. **Spaced Repetition** (v1.11.0+)
Интеграция flashcard-ов для обучения.

**Flashcard folder:**
```
ZETTA/Flashcards
```

**Settings:**
- ✅ Show review intro
- ✅ Show correct/incorrect options
- ✅ Use scheduling (Leitner System)

---

### 10. **Tag Wrangler** (v0.5.8+)
Управление тегами и их переименование.

**Exclude tags:**
- `#system`
- `#hidden`

---

### 11. **Outliner** (v4.7.0+)
Улучшенная работа со списками и иерархией.

**Hotkeys:**
- Indent: `Tab`
- Dedent: `Shift+Tab`
- Move down: `Ctrl+↓`
- Move up: `Ctrl+↑`

---

### 12. **Note Toolbar** (v1.12.0+)
Кастомные кнопки в toolbar для быстрого доступа.

**Toolbar buttons:**
```json
[
  {
    "label": "Daily",
    "command": "periodic-notes:open-daily"
  },
  {
    "label": "Search",
    "command": "omnisearch:open-omnisearch"
  },
  {
    "label": "New Note",
    "command": "quickadd:open-quick"
  }
]
```

---

## 🎨 Стилизация и UI

### 13. **Obsidian Style Settings** (v0.4.12+)
Управление CSS переменными и темами.

**CSS snippet для Dashboard:**
```
.obsidian/snippets/dashboard.css
```

**Переменные:**
```css
--db-accent: #2459B8;        /* Blue headers/buttons */
--db-bg-panel: #e5e4e2;      /* Platinum panels */
--db-text-dark: #0F1724;     /* Dark text */
--db-text-light: #ffffff;    /* Light text */
```

---

### 14. **Minimal Theme Settings** (v6.3.0+)
Расширенная настройка minimal темы (если используется).

**Font sizes:**
- H1: 28px
- H2: 24px
- H3: 20px

---

## 📋 Чек-лист настройки

### Шаг 1: Templater
- [ ] Папка шаблонов: `SYSTEM/Templates`
- [ ] Folder Templates добавлены (5 шаблонов)
- [ ] Trigger on file creation включен

### Шаг 2: Periodic Notes
- [ ] Daily: Format `YYYY-MM-DD`, Folder `DAILY/Daily`
- [ ] Weekly: Format `YYYY-[W]WW`, Folder `DAILY/Weekly`
- [ ] Monthly: Format `YYYY-MM`, Folder `DAILY/Monthly`
- [ ] Все шаблоны указаны корректно

### Шаг 3: QuickAdd
- [ ] 5 choices созданы (Permanent, Literature, Fleeting, MOC, Flashcard)
- [ ] Все папки назначены корректно
- [ ] File name formats настроены

### Шаг 4: Homepage
- [ ] Путь: `HUB/🏠 Home`
- [ ] Open on startup включен
- [ ] Pin tab включен

### Шаг 5: Custom Sort
- [ ] `.sortspec` файл в корне хранилища
- [ ] Порядок: HUB, PARA, ZETTA, DAILY, SYSTEM

### Шаг 6: Hotkeys
- [ ] Ctrl+D → Daily Note
- [ ] Ctrl+Shift+A → QuickAdd
- [ ] Ctrl+K → Omnisearch
- [ ] Ctrl+Home → Homepage

### Шаг 7: CSS
- [ ] Snippet включен в Settings → Appearance
- [ ] Цвета применяются на Dashboard

### Шаг 8: Dataview
- [ ] Inline expressions включены
- [ ] Запросы работают на Dashboard

---

## 🐛 Troubleshooting

**Шаблоны не применяются при создании файла**
- Проверь: Templater folder = `SYSTEM/Templates`
- Включи: Settings → Templater → Trigger on file creation

**Periodic Notes не создаются**
- Проверь: Путь существует (`DAILY/Daily`)
- Проверь: Шаблон указан (`SYSTEM/Templates/Daily.md`)
- Перезагрузи: Ctrl+F5

**QuickAdd не видит шаблоны**
- Проверь: Template path имеет расширение `.md`
- Проверь: Папка для сохранения существует

**Кнопки на Dashboard не работают**
- Проверь: Meta Bind definitions в начале файла
- Проверь: `obsidianUIMode: preview` в frontmatter
- Перезагрузи: Ctrl+F5

---

**Готово к использованию после настройки всех пункт из чек-листа!**
