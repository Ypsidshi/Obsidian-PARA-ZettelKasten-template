---
created: 2026-05-02
type: moc
tags: [moc, moc/root]
cssclasses: [dashboard, key-page, key-page-moc]
obsidianUIMode: preview
---

# Главный MOC

> Точка входа в темы и карты содержания.
>
> Куда дальше: [[HUB/Home|Домой]] — [[HUB/Periodic hub|Цикл]] — [[ZETTA/FLEETING/Fleeting hub|Fleeting hub]]

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
