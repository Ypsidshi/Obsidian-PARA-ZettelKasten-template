---
created: 2026-05-02
type: moc
tags: [moc, moc/root]
cssclasses: [dashboard, key-page, key-page-moc]
obsidianUIMode: preview
---

# Главный MOC

> Точка входа в темы и карты содержания.

`BUTTON[hub_nav_home]`

## :LiMap: Тематические карты

*По мере роста базы добавляй ссылки на MOC по крупным темам.*

- 

## :LiLayoutGrid: Все MOC

```dataview
LIST
FROM "HUB/MOCs"
WHERE type = "moc" AND file.name != this.file.name
SORT file.name ASC
```

```meta-bind-button
label: Домой
icon: lucide-home
hidden: true
id: hub_nav_home
style: primary
tooltip: Открыть Home
actions:
  - type: open
    link: "[[HUB/Home]]"
```
