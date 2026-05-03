---
type: guide
tags: [system, guide, hotkeys, workflows]
---

# Guide: Как работать с хранилищем

Практическое руководство по использованию ZettelKasten + PARA в Obsidian.

## 🎯 Основные горячие клавиши

| Действие | Hotkey |
|----------|--------|
| Открыть Dashboard | `Ctrl+Home` |
| Создать Daily Note | `Ctrl+Shift+D` |
| QuickAdd (быстрое меню) | `Ctrl+Shift+A` |
| Поиск (Omnisearch) | `Ctrl+K` |
| Command Palette | `Ctrl+P` |
| Создать новую заметку | `Ctrl+N` |
| Переключить режим Reading/Edit | `Ctrl+E` |
| Вставить ссылку | `Ctrl+[` |
| Создать встроенный запрос | Templater commands |

> Customize в Settings → Hotkeys

## 📅 Workflow: День, Неделя, Месяц

### Ежедневный workflow

1. **Утром** (при открытии Obsidian)
   - Открывается Dashboard автоматически
   - Нажми "Daily Note" или используй `Ctrl+Shift+D`
   - Увидишь: inbox, план на день, заметки из вчера

2. **В течение дня**
   - Быстрая идея? → QuickAdd (Fleeting Note)
   - Прочитал интересное? → Literature Note
   - Разработал мысль? → Permanent Note
   - Все заметки автоматически появляются в Inbox на Daily Note

3. **Вечером**
   - Обзор Daily Note
   - Перевести важные Fleeting → Permanent или Literature
   - Добавить рефлексию в раздел "Reflection"

### Еженедельный обзор

- **Каждый понедельник** (или выбранный день недели)
- Создай Weekly Note через Periodic Notes
- Просмотри все заметки прошлой недели
- Рефлексия: что выучил, что получилось, что улучшить

Структура Weekly:
- Обзор: ключевые события
- Статистика: сколько заметок создано
- Связи: какие идеи соединились
- План: цели на следующую неделю

### Ежемесячный обзор

- **1-го числа месяца**
- Обзор Monthly Note
- Чего я обещал улучшить в прошлом месяце?
- Статистика обучения
- План на месяц вперёд

## 🗂️ PARA структура

Используй для организации проектов и идей:

### Projects (Проекты)
Что-то с конечной датой завершения.
- Написать статью
- Пройти курс
- Реализовать feature в коде

Структура: `PARA/[Project Name]/` с подпапками для заметок по проекту

### Areas (Области)
Долгосрочные зоны ответственности.
- Здоровье
- Карьера
- Образование
- Финансы

Структура: `PARA/[Area Name]/` — постоянные заметки по теме

### Resources (Ресурсы)
Информация для справки.
- Списки инструментов
- Шпаргалки
- Справочники

Структура: `PARA/Resources/[Topic]/`

### Archive (Архив)
Завершённые проекты и неактуальные области.

## 🔗 Zettelkasten в ZETA

Принципы создания атомных заметок:

### Что такое атомная заметка
- **Одна идея** — одна заметка
- **Автономная** — понятна без контекста
- **Связная** — ссылается на другие заметки
- **Переиспользуемая** — может быть включена в разные контексты

### Формат Permanent Note

```
---
type: permanent
status: seed | growing | mature
created: YYYY-MM-DD
---

# Заголовок: Суть идеи

## Идея
[Основная мысль в 1-2 предложениях]

## Развитие
[Как идея расширяется, примеры, следствия]

## Связи
- **Похожие**: [[Link]], [[Link]]
- **Противоположные**: [[Link]], [[Link]]
- **Предшествующие**: [[Link]], [[Link]]
- **Следующие**: [[Link]], [[Link]]

## Источники
- [[Literature Note Name]]
```

### Статусы заметок

- **seed** — новая идея, едва начатая
- **growing** — развивается, добавляются связи
- **mature** — полная, установлены связи с соседними идеями

## 📚 Literature Notes

Заметки из книг, статей, видео.

### Формат Literature Note

```
---
type: literature
source-type: book | article | video | course
author: 
status: reading | read
progress: 0-100%
rating: 1-5
---

# [Автор] — [Название]

## Основная информация
[Источник, ссылка, год выпуска]

## Ключевые идеи
- Идея 1
- Идея 2

## Цитаты
> "Цитата из источника"

## Размышления
[Твои мысли об этом]

## Permanent Notes
Заметки, извлечённые в ZETA:
- [[Permanent Note 1]]
```

## 🗺️ MOCs (Maps of Content)

Карты содержания — индексы для навигации.

### Когда создавать MOC
- Когда накопилось 5-10 заметок на одну тему
- Для начинающих тем (как входная точка)
- Для сложных многоуровневых тем

### Структура MOC

```
---
type: moc
---

# [Название темы]

## Описание
[О чём эта область, зачем нужна]

## Основные подтемы

### Подтема 1
- [[Note 1]]
- [[Note 2]]

### Подтема 2
- [[Note 3]]
- [[Note 4]]

## Связанные MOCs
- [[MOC Name]]
- [[MOC Name]]
```

## 🎓 Spaced Repetition (Flashcards)

Для запоминания важного материала.

### Формат Flashcard

```
---
type: flashcard
deck: [Topic]/[Subtopic]
---

# Тема

Q:: Вопрос?

A:: Ответ
```

### Использование
1. Создай flashcard с Fleeting Note
2. Плагин Spaced Repetition покажет в нужное время
3. Повторяй по алгоритму Лейтнера

## ⚙️ Полезные настройки

### Dataview запросы на Dashboard

Показать недавние заметки:
```dataview
LIST
FROM "ZETA"
WHERE type = "permanent"
SORT created DESC
LIMIT 5
```

Показать незавершённые проекты:
```dataview
LIST
FROM "PARA"
WHERE status != "archived"
GROUP BY status
```

### Фильтры поиска

- `tag:#to-process` — заметки в обработке
- `type:permanent` — только постоянные заметки
- `status:seed` — новые идеи
- `created >= 2026-05-01` — за последний месяц

### Автолинкование

Включи в Settings → Editor:
- Auto-link text fragments = ✓
- Ignore accents in search = ✓

## 📖 Источники и ссылки

### Документация плагинов
- [Templater](https://silentvoid13.github.io/Templater/)
- [Dataview](https://blacksmithgu.github.io/obsidian-dataview/)
- [Periodic Notes](https://github.com/liamcain/obsidian-periodic-notes)
- [Meta Bind](https://www.metabind.io/)
- [QuickAdd](https://quickadd.io/)

### Zettelkasten методология
- Luhmann's Zettelkasten (оригинальная система)
- Методика из "How to Take Smart Notes" (Ahrens)
- PKM (Personal Knowledge Management)

### Obsidian сообщество
- [Obsidian Forum](https://forum.obsidian.md/)
- [Obsidian Help](https://help.obsidian.md/)
- Плагины: Community Plugins в Settings

## 🐛 Troubleshooting

### Dashboard показывается по-разному
**Проблема**: Разное отображение при открытии вручную vs при запуске
**Решение**: Это Reading vs Edit view. В frontmatter Home.md должно быть `obsidianUIMode: preview`

### Кнопки на Dashboard не работают
**Проблема**: "Button ID not found"
**Решение**: Определения кнопок должны быть в начале файла, обёрнуты в `<div style="display:none">`

### Папки отображаются в алфавитном порядке
**Проблема**: Нет нужной сортировки
**Решение**: Custom Sort должен использовать `.sortspec` файл в корне

### Заметки не индексируются в Dataview
**Проблема**: Dataview не видит заметки
**Решение**: Проверь frontmatter синтаксис, перезагрузи плагин (Ctrl+F5)

## 💡 Советы для продуктивности

1. **Inbox Zero подход**
   - Каждый день перерабатывай Fleeting → Permanent/Literature
   - Inbox должен быть пустым к концу дня

2. **Batch создание заметок**
   - Собирай идеи весь день через QuickAdd
   - Обработай их вечером одновременно

3. **Регулярные обзоры**
   - Daily: 5-10 минут
   - Weekly: 30 минут
   - Monthly: 1 час

4. **Не перфекционизируй**
   - Лучше создать 10 seed заметок, чем 1 идеальную
   - Заметки будут расти со временем

5. **Используй теги умно**
   - `#to-process` — в обработке
   - `#todo` — действия
   - `#question` — нерешённые вопросы

---

**Помни**: это твоя система, адаптируй её под себя!
