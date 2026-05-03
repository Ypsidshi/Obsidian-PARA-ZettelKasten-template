---
type: system-doc
cssclasses: [no-inline-title]
---

# 📖 Guide / Руководство

## 🇷🇺 Русский

### Горячие клавиши

Назначаются в Settings → Hotkeys.

| Действие | Клавиши |
|---|---|
| Открыть Daily | `Ctrl+Shift+D` |
| Открыть Weekly | `Ctrl+Shift+W` |
| Открыть Monthly | `Ctrl+Shift+M` |
| Открыть Homepage | `Ctrl+H` |
| Создать Permanent (QuickAdd) | `Ctrl+Alt+P` |
| Создать Literature (QuickAdd) | `Ctrl+Alt+L` |
| Templater: вставить шаблон | `Ctrl+Shift+I` |
| Spaced Repetition: повторение | `Ctrl+Shift+R` |
| Omnisearch: поиск | `Ctrl+Shift+F` |
| Quick Switcher | `Ctrl+O` |
| Command Palette | `Ctrl+P` |
| Переключить Edit/Reading View | `Ctrl+E` |
| Закрепить вкладку | ПКМ по вкладке → Pin |

### Рабочий процесс

**Ежедневно:**
1. Утром — открой Home (`Ctrl+H`), посмотри Inbox и сегодняшнюю Daily.
2. В течение дня — кидай мысли в Inbox через кнопку или `Ctrl+N` (если стоишь в HUB/Inbox).
3. Создаёшь идею своими словами → Permanent (`Ctrl+Alt+P`).
4. Конспектируешь книгу/статью → Literature (`Ctrl+Alt+L`).
5. Вечером — повторение карточек (`Ctrl+Shift+R`).

**Еженедельно:**
- Открой Weekly (`Ctrl+Shift+W`) — увидишь все заметки недели.
- Разбери оставшиеся Inbox → перенеси в Permanent / Literature / удали.
- Заполни рефлексию.

**Ежемесячно:**
- Открой Monthly (`Ctrl+Shift+M`) — увидишь "что ты обещал изменить в прошлом месяце".
- Заполни главные уроки и план изменений на следующий месяц.

### Правила Zettelkasten

1. **Атомарность** — одна заметка = одна идея.
2. **Связи важнее иерархии** — ставь `[[ссылки]]` на смежные заметки.
3. **Своими словами** — не копируй, пересказывай. Это и есть процесс понимания.
4. **MOC по теме** — когда накопится 5+ связанных Permanent-заметок, собери их в MOC.

### Карточки Spaced Repetition

Синтаксис: `Вопрос::Ответ` (в любой заметке).
Двусторонняя: `Вопрос:::Ответ` (тестирует и в обратную сторону).
Cloze-карточка: `Текст с ==выделенным== словом` (выделение скрывается при тесте).

В Permanent-заметку добавляй карточку **только если идею нужно запоминать наизусть** (термин, формула, факт). Концепции, которые ты понял, повторять не нужно.

### Полезные настройки

- **Reading View по умолчанию** — для дашборда: добавь `obsidianUIMode: preview` в frontmatter заметки.
- **CSS Snippets** — Settings → Appearance → подключи свои `.css` файлы из `.obsidian/snippets/`.
- **Тег `#to-process`** — ставь fleeting-заметкам, разберёшь в weekly review.
- **Графовый вид** (`Ctrl+G`) — визуализация связей между заметками.
- **Pinned tabs** — ПКМ по вкладке → Pin tab. Закрепи Home как первую вкладку.

### Кастомизация

- **Цвет акцента** — Settings → Appearance → Accent color. Все заголовки и иконки на дашборде унаследуют его автоматически.
- **Тема** — Settings → Appearance → Themes. Минотавр, Things, Catppuccin — популярные.
- **Своя кнопка на Home** — добавь блок `meta-bind-button` (с `id`, `hidden: true`) внизу `🏠 Home.md`, затем вставь `` `BUTTON[id]` `` в строку с кнопками вверху.
- **Своя секция Dataview** — скопируй существующий блок ` ```dataview `, поменяй `FROM` и `WHERE`. Документация: blacksmithgu.github.io/obsidian-dataview.

### Если что-то сломалось

| Проблема | Решение |
|---|---|
| Кнопки на Home отображаются как `BUTTON[...]` | Включи плагин **Meta Bind** |
| QuickAdd-кнопки не работают | Проверь UUID-id в `.obsidian/plugins/quickadd/data.json`, обнови в Home |
| Dataview показывает ошибку | Проверь, что путь в `FROM "..."` существует |
| Daily не создаётся | Отключи встроенный плагин Daily Notes |
| Иконки не отображаются | Версия Obsidian слишком старая (нужна 1.4+) |

---

## 🇬🇧 English

### Hotkeys

Set in Settings → Hotkeys.

| Action | Keys |
|---|---|
| Open Daily | `Ctrl+Shift+D` |
| Open Weekly | `Ctrl+Shift+W` |
| Open Monthly | `Ctrl+Shift+M` |
| Open Homepage | `Ctrl+H` |
| New Permanent (QuickAdd) | `Ctrl+Alt+P` |
| New Literature (QuickAdd) | `Ctrl+Alt+L` |
| Templater: insert template | `Ctrl+Shift+I` |
| Spaced Repetition: review | `Ctrl+Shift+R` |
| Omnisearch | `Ctrl+Shift+F` |
| Quick Switcher | `Ctrl+O` |
| Command Palette | `Ctrl+P` |
| Toggle Edit/Reading View | `Ctrl+E` |
| Pin tab | Right-click tab → Pin |

### Workflow

**Daily:**
1. Morning — open Home (`Ctrl+H`), check Inbox and today's Daily.
2. Throughout the day — drop thoughts into Inbox.
3. Got an idea in your own words → Permanent (`Ctrl+Alt+P`).
4. Reading something → Literature (`Ctrl+Alt+L`).
5. Evening — review flashcards (`Ctrl+Shift+R`).

**Weekly:**
- Open Weekly (`Ctrl+Shift+W`) — see all notes from the week.
- Process remaining Inbox → move to Permanent / Literature / delete.
- Fill in reflection.

**Monthly:**
- Open Monthly (`Ctrl+Shift+M`) — see "what you promised to change last month".
- Write key lessons and changes for next month.

### Zettelkasten rules

1. **Atomicity** — one note = one idea.
2. **Links over hierarchy** — use `[[wikilinks]]` to related notes.
3. **In your own words** — don't copy, rephrase. That's the understanding process.
4. **MOCs for topics** — when 5+ related Permanents accumulate, collect them in a MOC.

### Spaced Repetition cards

Syntax: `Question::Answer` (in any note).
Two-way: `Question:::Answer` (also tests in reverse).
Cloze: `Text with ==highlighted== word` (highlight is hidden during test).

Add a card to a Permanent **only if the idea needs rote memorization** (term, formula, fact). Concepts you've understood don't need repetition.

### Useful settings

- **Default Reading View** — for dashboards: add `obsidianUIMode: preview` to frontmatter.
- **CSS Snippets** — Settings → Appearance → enable your `.css` from `.obsidian/snippets/`.
- **Tag `#to-process`** — mark fleeting notes, sort during weekly review.
- **Graph view** (`Ctrl+G`) — visualize note connections.
- **Pinned tabs** — right-click tab → Pin. Pin Home as the first tab.

### Customization

- **Accent color** — Settings → Appearance → Accent color. All dashboard headings and icons inherit automatically.
- **Theme** — Settings → Appearance → Themes. Minotaur, Things, Catppuccin are popular.
- **Custom button on Home** — add a `meta-bind-button` block (with `id`, `hidden: true`) at the bottom of `🏠 Home.md`, then insert `` `BUTTON[id]` `` in the buttons row at the top.
- **Custom Dataview section** — copy an existing ` ```dataview ` block, change `FROM` and `WHERE`. Docs: blacksmithgu.github.io/obsidian-dataview.

### Troubleshooting

| Problem | Solution |
|---|---|
| Buttons on Home show as `BUTTON[...]` | Enable **Meta Bind** plugin |
| QuickAdd buttons don't work | Check UUID id in `.obsidian/plugins/quickadd/data.json`, update Home |
| Dataview shows error | Verify path in `FROM "..."` exists |
| Daily doesn't create | Disable built-in Daily Notes core plugin |
| Icons don't render | Obsidian version too old (need 1.4+) |
