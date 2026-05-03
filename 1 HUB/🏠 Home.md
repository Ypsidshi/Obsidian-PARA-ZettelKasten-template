---
type: home
cssclasses: [home, dashboard]
obsidianUIMode: preview
---

# Second Brain

> Обработка → Хранение → Связи → Запоминание

`BUTTON[open_daily]` `BUTTON[open_inbox]` `BUTTON[new_permanent]` `BUTTON[new_literature]` `BUTTON[review_cards]` `BUTTON[open_moc]` `BUTTON[open_search]`

> [!card] Inbox
> ```dataview
> LIST
> FROM "1 HUB/Inbox"
> SORT file.ctime DESC
> LIMIT 10
> ```

> [!card] Сейчас читаю
> ```dataview
> TABLE without id
>   file.link as "Заметка",
>   author as "Автор",
>   progress as "Прогресс"
> FROM "3 ZETTA/Literature"
> WHERE type = "literature" AND status = "reading"
> SORT file.mtime DESC
> ```

> [!card] Последние Permanent
> ```dataview
> LIST
> FROM ""
> WHERE type = "permanent"
>   AND !contains(file.path, "Templates")
> SORT file.ctime DESC
> LIMIT 7
> ```

> [!card] Карты тем
> ```dataview
> LIST
> FROM "1 HUB/MOCs"
> WHERE type = "moc"
> SORT file.name ASC
> ```

> [!card] Статистика
> ```dataview
> TABLE WITHOUT ID
>   type as "Тип",
>   length(rows) as "Кол-во"
> FROM ""
> WHERE type
>   AND !contains(file.path, "Templates")
> GROUP BY type SORT length(rows) DESC
> ```

```meta-bind-button
label: Daily
icon: lucide-calendar
hidden: true
id: open_daily
style: primary
actions:
  - type: command
    command: periodic-notes:open-daily-note
```
```meta-bind-button
label: Inbox
icon: lucide-inbox
hidden: true
id: open_inbox
style: default
actions:
  - type: open
    link: "[[1 HUB/Inbox]]"
```
```meta-bind-button
label: Permanent
icon: lucide-plus-circle
hidden: true
id: new_permanent
style: primary
actions:
  - type: command
    command: quickadd:choice:eb6a0a70-ee59-49c2-8637-98116698b379
```
```meta-bind-button
label: Literature
icon: lucide-book-open
hidden: true
id: new_literature
style: primary
actions:
  - type: command
    command: quickadd:choice:c3fb5b88-0a08-4e45-ada7-cf3f286c38af
```
```meta-bind-button
label: Карточки
icon: lucide-layers
hidden: true
id: review_cards
style: primary
actions:
  - type: command
    command: obsidian-spaced-repetition:srs-review-flashcards
```
```meta-bind-button
label: MOC
icon: lucide-map
hidden: true
id: open_moc
style: primary
actions:
  - type: open
    link: "[[1 HUB/MOCs/Главный MOC.md]]"
```
```meta-bind-button
label: Поиск
icon: lucide-search
hidden: true
id: open_search
style: default
actions:
  - type: command
    command: omnisearch:show-modal
```
