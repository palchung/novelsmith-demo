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


---

## Step 1: Prepare Your Canvas
The Dashboard Builder doesn't force you into a specific file. It puts the chart exactly where your cursor is.
1. Open any note in Obsidian (it could be your daily note, a dedicated "Progress" note, or an empty canvas).
2. Click where you want the chart to appear.

## Step 2: Open the Builder
1. Go to the right NovelSmith panel, click the **🔧 Tools** icon (the wrench), and select **Insert dashboard** (the bar chart icon). 
2. Alternatively, press `Ctrl+P` (or `Cmd+P`), type "Dashboard", and hit Enter.

## Step 3: Choose What to Analyze (The Chips)
A beautiful window will pop up. The first thing you'll see is a cluster of buttons (Chips). 
* These chips are **dynamic**. NovelSmith actually reads your novel's database and lists every single attribute you've ever used (like `POV`, `Status`, `Rhythm`).
* **Combine data:** You can click multiple chips! For example, click `[POV]` and `[Players]` together. NovelSmith will instantly merge them so you can analyze all character appearances at once!

## Step 4: Choose Your Chart Type
How do you want to see the data? You have three powerful options:

1. 🥧 **Pie Chart:** Best for seeing proportions. (E.g., "What percentage of my novel is told from Alice's POV vs. Bob's POV?")
2. 📊 **Bar Chart:** Best for leaderboards. (E.g., "Who are the top 5 most frequently appearing characters?")
3. 🗂️ **Data Table:** Best for detailed reading. 
   * *If you choose Data Table, a secret option appears:*
     * **Progress List:** Groups the data by *Chapter*. Perfect for making a master list of what scenes still need to be written.
     * **Stats List:** Groups the data by the *Attribute*. Perfect for seeing a list of characters and exactly which scenes they appeared in.

## Step 5: Tweak the Settings (Advanced Magic)
Depending on what chart you picked, you'll see a few extra toggles to make your data perfect:
* **Smart Flattening:** If a scene has `Players:: Alice, Bob`, turning this ON tells the system to count Alice and Bob separately. (Usually, you want this ON!)
* **Limit Results:** Don't want a list of 100 minor characters? Change this to "Only show the most recent 3 times". This is *incredibly* useful for checking a character's continuity (e.g., "Where was Alice the last 3 times she appeared?").

## Step 6: Insert and Enjoy
Read the "human language" summary at the bottom of the window to confirm what you are about to do. 
1. Click **✨ Insert Chart Here**.
2. NovelSmith will type out a block of complex code into your editor.
3. Click away from the code block, and Obsidian will instantly render your beautiful, interactive chart!

*Note: You can insert as many dashboards as you want into a single note. Have fun analyzing your masterpiece!*

