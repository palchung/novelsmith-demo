# 📊 The Ultimate Dashboard (Dataview Magic)

> [!tip] Data-Driven Writing
> NovelSmith is not just a writing editor; it is a **powerful story data engine**.
> Every time you edit a scene, change a card's color, or update a plot status, NovelSmith silently synchronizes a master database in the background (`_Scene_Database.md`).
> 
> By combining this with Obsidian's powerful Dataview plugin, you can easily build an auto-updating "visual dashboard" that makes the entire structure of your novel clear at a glance!

---

### 🛠️ Prerequisites
To activate the data magic below, you only need to install and enable one community plugin in Obsidian:
* **Dataview** (Used to transform your plot data into clean, readable tables)
*(Note: This tutorial uses the most basic DQL syntax. Even if you don't know how to code, you can easily modify it. There is no need to enable DataviewJS!)*

---

## ⏳ 1. The Chronological Timeline
*The order in which you write your chapters isn't always the order in which the story actually happens. This table automatically ignores your chapter sorting and arranges every scene by its actual `Time` attribute, helping you easily spot any timeline bugs!*


```dataview
TABLE WITHOUT ID
  L.Time AS "⏰ Time",
  L.Scene AS "🎬 Scene Name",
  L.POV AS "👁️ POV",
  L.Color AS "🎨 Theme Color"
FROM "NovelSmith_Demo_Vault/_Backstage/_Scene_Database.md"
FLATTEN file.lists AS L
WHERE L.Scene
SORT L.Time ASC
```


### DQL Code

\`\`\`dataview
TABLE WITHOUT ID
  L.Time AS "⏰ Time",
  L.Scene AS "🎬 Scene Name",
  L.POV AS "👁️ POV",
  L.Color AS "🎨 Theme Color"
FROM "NovelSmith_Demo_Vault/_Backstage/_Scene_Database.md"
FLATTEN file.lists AS L
WHERE L.Scene
SORT L.Time ASC
\`\`\`

---

## 👁️ 2. POV Distribution Matrix
*Want to know which character is getting the most screen time? This table groups and tallies all scenes by their Point of View (POV). Even scenes that haven't been assigned a POV yet will be automatically categorized under "Unassigned"—nothing slips through the cracks.*


```dataview
TABLE WITHOUT ID
  key AS "👁️ Point of View (POV)",
  length(rows) AS "🎬 Scene Count"
FROM "NovelSmith_Demo_Vault/_Backstage/_Scene_Database.md"
FLATTEN file.lists AS L
WHERE L.Scene
GROUP BY choice(L.POV, L.POV, "👻 Unassigned")
SORT length(rows) DESC
```


### DQL Code

\`\`\`dataview
TABLE WITHOUT ID
  key AS "👁️ Point of View (POV)",
  length(rows) AS "🎬 Scene Count"
FROM "NovelSmith_Demo_Vault/_Backstage/_Scene_Database.md"
FLATTEN file.lists AS L
WHERE L.Scene
GROUP BY choice(L.POV, L.POV, "👻 Unassigned")
SORT length(rows) DESC
\`\`\`

---

## 🔵 3. Theme / Color Filter
*The colors you assign to your cards in the outline panel can play a huge role here! For example, if you tag all "High Conflict / Villain" plots with blue, you can use the `contains()` function to pull them all out for a focused review.*

```dataview
TABLE WITHOUT ID
  L.Scene AS "🎬 Scene Name",
  L.POV AS "👁️ POV",
  L.Time AS "⏰ Time"
FROM "NovelSmith_Demo_Vault/_Backstage/_Scene_Database.md"
FLATTEN file.lists AS L
WHERE L.Scene AND contains(L.Color, "🔵")
```

### DQL Code

\`\`\`dataview
TABLE WITHOUT ID
  L.Scene AS "🎬 Scene Name",
  L.POV AS "👁️ POV",
  L.Time AS "⏰ Time"
FROM "NovelSmith_Demo_Vault/_Backstage/_Scene_Database.md"
FLATTEN file.lists AS L
WHERE L.Scene AND contains(L.Color, "🔵")
\`\`\`

---
> **💡 Customization Tip:** > These codes are completely open! If you add custom attributes to your scene cards (e.g., `Location:: Coffee Shop`), simply add a line like `L.Location AS "📍 Location",` right under `TABLE WITHOUT ID` to enrich your dashboard. Organizing your writing has never been this simple.