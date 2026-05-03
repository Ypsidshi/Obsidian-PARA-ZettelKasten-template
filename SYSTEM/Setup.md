---
type: guide
tags: [system, setup, installation]
---

# Setup: Установка хранилища

Пошаговая инструкция для настройки нового хранилища ZettelKasten + PARA.

## 1. Базовая структура

Хранилище должно содержать папки:
- **HUB** — Dashboard и центральная навигация
- **PARA** — Projects, Areas, Resources, Archive
- **ZETA** — Zettelkasten (атомные заметки)
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

В Settings → QuickAdd:
- Choice №1: Permanent Note → Template: `SYSTEM/Templates/Permanent.md`
- Choice №2: Literature Note → Template: `SYSTEM/Templates/Literature.md`
- Choice №3: Fleeting Note → Template: `SYSTEM/Templates/Fleeting.md`

Создать hotkey для быстрого открытия QuickAdd

## 6. Настройка Homepage

В Settings → Homepage:
- Homepage file = `HUB/🏠 Home`
- Open on startup = ✓
- Pin the homepage tab = ✓

## 7. Настройка Custom Sort

Создать файл `.sortspec` в корне хранилища:
```
HUB
PARA
ZETA
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
- `Permanent.md` — атомная заметка (Zettelkasten)
- `Literature.md` — заметка из источника
- `MOC.md` — карта содержания
- `Flashcard.md` — карточка для повторения
- `Fleeting.md` — быстрая заметка

## 10. Настройка Dataview

В Settings → Dataview:
- Render inline expressions = ✓
- Render inline field icons = ✓

Для использования в шаблонах:
```dataview
LIST
FROM "ZETA"
WHERE type = "permanent"
SORT created DESC
LIMIT 5
```

## 11. Настройка Meta Bind

На Dashboard (`HUB/🏠 Home.md`) добавить кнопки:
```
BUTTON[id]
```

Кнопки:
- Daily Note
- Quick Inbox
- New Permanent
- New Literature
- Flashcards
- MOCs
- Omnisearch

## 12. Сортировка папок (без префиксов)

Используется Custom Sort плагин. Папки автоматически сортируются по `.sortspec`:
- HUB первая
- PARA вторая
- ZETA третья
- DAILY четвёртая
- SYSTEM последняя

## 13. Первый запуск

1. Открыть хранилище в Obsidian
2. Перезагрузить плагины (Ctrl+F5)
3. Создать первую ежедневную заметку (Ctrl+D или через кнопку)
4. Проверить Dashboard на `HUB/🏠 Home.md`
5. Убедиться, что все кнопки работают
6. Добавить первую заметку в ZETA через "New Permanent"

После этого система готова к использованию!
