---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
type: permanent
tags: []
status: seed
cssclasses:
  - dashboard
  - nav-two
obsidianUIMode: preview
---

`BUTTON[hub_nav_main_moc]` `BUTTON[hub_nav_home]`

# <% tp.file.title %>

## :LiLightbulb: Идея
*Сформулируй своими словами в 1–3 предложениях. Одна заметка — одна мысль.*


## :LiBrain: Развёрнуто


## :LiLink: Связи
- **Из чего следует:** 
- **Что из этого следует:** 
- **Похоже на:** 
- **Противоречит:** 

## :LiLayers: Карточки
*Опционально. Добавляй только если идею нужно запоминать. Формат: `Q:: A::`*



## :LiLibrary: Источники
- 

```meta-bind-button
label: К главному MOC
icon: lucide-map
hidden: true
id: hub_nav_main_moc
style: primary
tooltip: Открыть Главный MOC
actions:
  - type: open
    link: "[[HUB/MOCs/Главный MOC|Главный MOC]]"
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
