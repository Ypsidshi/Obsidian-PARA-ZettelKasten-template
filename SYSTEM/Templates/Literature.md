---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
type: literature
source-type: 
author: 
title: 
url: 
status: to-read
progress: 
rating: 
tags: [literature]
cssclasses:
  - dashboard
  - nav-two
---

`BUTTON[hub_nav_literature_hub]` `BUTTON[hub_nav_home]`

# <% tp.file.title %>

> [!info] Источник
> **Автор:** 
> **Тип:** book / article / video / course / podcast
> **Ссылка:** 
> **Статус:** to-read / reading / done
> **Прогресс:** 

## :LiStickyNote: О чём
*1–2 предложения: про что это вообще.*


## :LiKey: Ключевые идеи
- 

## :LiQuote: Цитаты
> 

## :LiBrain: Мои мысли
*Что зацепило, с чем согласен/не согласен, что хочется развить.*


## :LiSprout: Что вынести в Permanent
*Идеи, которые стоит превратить в свои атомарные заметки.*
- [ ] 

## :LiLink2: Связано с
- 

```meta-bind-button
label: Перейти в Literature hub
icon: lucide-book-open
hidden: true
id: hub_nav_literature_hub
style: primary
tooltip: Открыть хаб Literature
actions:
  - type: open
    link: "[[ZETTA/Literature/Literature hub]]"
```

```meta-bind-button
label: Домой
icon: lucide-home
hidden: true
id: hub_nav_home
style: default
tooltip: Открыть Home
actions:
  - type: open
    link: "[[HUB/Home]]"
```
