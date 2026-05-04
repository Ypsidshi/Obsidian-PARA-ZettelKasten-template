---
created: <% tp.date.now("YYYY-MM-DD HH:mm") %>
type: flashcard
tags: [flashcards]
deck: 
cssclasses:
  - dashboard
  - nav-two
obsidianUIMode: preview
---

`BUTTON[review_cards]` `BUTTON[hub_nav_home]`

# <% tp.file.title %>

#flashcards/deck

## :LiLayers: Карточка

Q:: 

A:: 

## :LiLink2: Связано с
- 

```meta-bind-button
label: Повторение карточек
icon: lucide-layers
hidden: true
id: review_cards
style: primary
tooltip: Начать повторение Spaced Repetition
actions:
  - type: command
    command: obsidian-spaced-repetition:srs-review-flashcards
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
