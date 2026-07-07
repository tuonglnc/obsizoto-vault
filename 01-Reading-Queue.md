# 📚 Reading Queue

This is your research papers reading dashboard. The table below automatically aggregates your paper notes from the `02-Papers/` folder.

> [!TIP]
> Make sure to install and enable the **Dataview** plugin in Obsidian to let this dashboard update automatically.

## 🔄 Automatic Reading Queue (Requires Dataview Plugin)

```dataview
TABLE authors AS "Authors", year AS "Year", venue AS "Venue", rating AS "Rating", status AS "Status", keywords AS "Keywords", gap AS "Research Gap"
FROM "02-Papers"
SORT year DESC
```

## 📋 Manual Reading Queue (Fallback)

| Paper | Authors | Year | Venue | Status | Rating | Keywords | Research Gap |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| [[Paper Link]] | Author Name | Year | Venue | Status | Rating | Keywords | Research Gap |
