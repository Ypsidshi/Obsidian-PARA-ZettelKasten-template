---
type: guide
tags: [system, setup, installation]
cssclasses: [accent-nav-h2]
---

# Setup: Установка хранилища

Пошаговая инструкция для настройки нового хранилища ZettelKasten + PARA.

## 1. Базовая структура

Хранилище должно содержать папки:
- **HUB** — Dashboard и центральная навигация
- **PARA** — Projects, Areas, Resources, Archive
- **ZETTA** — Zettelkasten: `Permanent`, `Literature`, `Flashcards`, **`FLEETING`** (быстрые черновики; хаб `ZETTA/FLEETING/Fleeting hub.md`)
- **DAILY** — Ежедневные заметки
- **SYSTEM** — Шаблоны, гайды, настройки

## 2. Установка плагинов

Обязательные плагины:
- **Templater** — создание заметок по шаблонам
- **Dataview** — динамические списки и запросы
- **Periodic Notes** — автоматические ежедневные/еженедельные/ежемесячные заметки
- **Meta Bind** — интерактивные кнопки на Dashboard
- **QuickAdd** — быстрое создание заметок
- **Omnisearch** — полнотекстовый поиск
- **Custom Sort** — пользовательская сортировка папок
- **Homepage** — выбор начальной страницы

Дополнительные:
- **Datacore** — расширенные запросы к базе данных
- **Spaced Repetition** — интеграция flashcard-ов
- **Tag Wrangler** — управление тегами
- **Outliner** — улучшенная работа со списками

## 3. Настройка Periodic Notes

В Settings → Periodic Notes:
- **Daily**: Template path = `SYSTEM/Templates/Daily.md`, Format = `YYYY-MM-DD`
- **Weekly**: Template path = `SYSTEM/Templates/Weekly.md`, Format = `YYYY-[W]WW`
- **Monthly**: Template path = `SYSTEM/Templates/Monthly.md`, Format = `YYYY-MM`

## 4. Настройка Templater

В Settings → Templater:
- Folder for templates = `SYSTEM/Templates`
- Enabled в командной палитре

Создать hotkey для "Templater: Create new note from template"

## 5. Настройка QuickAdd

В Settings → QuickAdd (или через правку `.obsidian/plugins/quickadd/data.json`):
- Choice №1 **New Permanent** → `SYSTEM/Templates/Permanent.md` → папка `ZETTA/Permanent`
- Choice №2 **New Literature** → `SYSTEM/Templates/Literature.md` → папка `ZETTA/Literature`
- Choice №3 **New Fleeting** → `SYSTEM/Templates/Fleeting.md` → папка `ZETTA/FLEETING`, имя файла `{{VALUE:Название заметки}}`

У каждого из этих choice в JSON должно быть **`"command": true`** (в UI — молния «добавить в командную палитру»), иначе кнопки Meta Bind с `quickadd:choice:<uuid>` на Home не сработают.

Создать hotkey для быстрого открытия QuickAdd (`Ctrl+Shift+A`).

В **Settings → Files & links** (если включено «создавать новые заметки в папке»): папка по умолчанию = **`ZETTA/FLEETING`** (см. также `.obsidian/app.json`: `newFileFolderPath`).

## 6. Настройка Homepage

В Settings → Homepage:
- Homepage file = `HUB/Home`
- Open on startup = +
- Pin the homepage tab = +

## 7. Настройка Custom Sort

Порядок папок задаётся **либо** закладкой/группой в Obsidian (как у тебя с именем `sortspec`), **либо** текстовым файлом `.sortspec` в корне vault — не обязательно и то и другое; лишний файл в корне может перебить порядок из закладок.

Пример содержимого `.sortspec`, если выбираешь именно файл:
```
HUB
PARA
ZETTA
DAILY
SYSTEM
```

## 8. Настройка CSS

В `.obsidian/snippets/dashboard.css` добавить стили для Dashboard:
- Цвета: `#2459B8` (blue accent), `#e5e4e2` (platinum), `#0F1724` (dark text)
- Стили для Meta Bind кнопок
- Таблицы Dataview

Включить snippet в Settings → Appearance → CSS snippets

## 9. Создание шаблонов

Все шаблоны в папке `SYSTEM/Templates/`:
- `Daily.md` — ежедневная заметка
- `Weekly.md` — еженедельный обзор
- `Monthly.md` — ежемесячный обзор

Шаблоны Daily / Weekly / Monthly задают `cssclasses` для дашборда (`dashboard` + `periodic-daily` / `periodic-weekly` / `periodic-monthly`) и `obsidianUIMode: preview`; оформление и иконки секций — в `.obsidian/snippets/dashboard.css`. Сводки — **таблицы Dataview**.

Хаб **[[HUB/Periodic hub|Journal]]** (`cssclasses: dashboard, periodic-hub`): кнопки Meta Bind для открытия/создания текущих daily, weekly, monthly (команды Periodic Notes), оформление как на Home.
- `Permanent.md` — атомная заметка (Zettelkasten)
- `Literature.md` — заметка из источника
- `MOC.md` — карта содержания
- `Flashcard.md` — карточка для повторения
- `Fleeting.md` — быстрая заметка

## 10. Настройка Dataview

В Settings → Dataview:
- Render inline expressions = +
- Render inline field icons = +

Для использования в шаблонах:
```dataview
LIST
FROM "ZETTA"
WHERE type = "permanent"
SORT created DESC
LIMIT 5
```

## 11. Настройка Meta Bind

На Dashboard (`HUB/Home.md`) добавить кнопки:
```
BUTTON[id]
```

Кнопки (см. актуальные `id` в `HUB/Home.md`):
- Daily Note
- Открыть **Fleeting hub** (`[[ZETTA/FLEETING/Fleeting hub]]`, не вики на несуществующий файл)
- New Fleeting (QuickAdd choice)
- New Permanent / New Literature
- Flashcards (SRS)
- Главный MOC (`[[HUB/MOCs/Главный MOC|…]]` по имени файла)
- Omnisearch

## 12. Сортировка папок (без префиксов)

Используется Custom Sort плагин. Порядок берётся из твоей конфигурации плагина (закладки и/или `.sortspec`):
- HUB первая
- PARA вторая
- ZETTA третья
- DAILY четвёртая
- SYSTEM последняя

## 13. Первый запуск

1. Открыть хранилище в Obsidian
2. Перезагрузить плагины (Ctrl+F5)
3. Создать первую ежедневную заметку (Ctrl+D или через кнопку)
4. Проверить Dashboard на `HUB/Home.md`
5. Убедиться, что все кнопки работают
6. Добавить первую заметку в ZETTA через "New Permanent"

После этого система готова к использованию!
