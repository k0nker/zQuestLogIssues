# zQuestLogIssues
Issues for zQuestLog

# zQuestLog — Usage Guide

zQuestLog is a replacement for the default World of Warcraft quest tracker. It gives you a
resizable, scrollable window with full color, font, spacing, and sound customization, plus
support for multiple simultaneous tracker windows and a flexible tiling and anchoring system.

Open the settings panel at any time with:

```
/zql options
```

---

## Table of Contents

1. [The Tracker Window](#the-tracker-window)
2. [Interacting with Quests](#interacting-with-quests)
3. [Categories](#categories)
4. [Multiple Trackers](#multiple-trackers)
5. [Quest Item Buttons](#quest-item-buttons)
6. [Slash Commands](#slash-commands)
7. [Keybinds](#keybinds)
8. [Settings — General](#settings--general)
9. [Settings — Trackers](#settings--trackers)
10. [Settings — Tiling](#settings--tiling)
11. [Settings — Appearance > Fonts](#settings--appearance--fonts)
12. [Settings — Appearance > Style](#settings--appearance--style)
13. [Settings — Appearance > Colors](#settings--appearance--colors)
14. [Settings — Appearance > Spacing](#settings--appearance--spacing)
15. [Settings — Appearance > Quest Items](#settings--appearance--quest-items)
16. [Settings — Sounds](#settings--sounds)
17. [Settings — Profiles](#settings--profiles)
18. [Tips and Tricks](#tips-and-tricks)

---

## The Tracker Window

The tracker window has a **title bar** across the top and a **scrollable content area** below
it. The title bar holds several controls described left to right.

### Title Bar Controls

#### Minimize Button (far left)

Collapses the content area down to just the title bar. Click again to restore.

#### Eye Toggle (second from left)

Toggles **Show User-Hidden Quests**. When the eye is open, quests you have previously hidden
with Shift+click appear in a dimmed state. When closed they are fully invisible. This is a
global setting shared across all tracker windows.

#### Dungeon Filter Button (third from left, Main Tracker only)

Toggles the **Dungeon Quest Filter**, which hides quests unrelated to your current dungeon so
you only see relevant quests inside instances. When active the icon turns red. Only present
on the Main Tracker.

#### Quest Count

When the **Quests** category is active, a small `N/M` read-only counter shows how many quests
are in your log versus your character's quest cap.

#### Title Text (center)

Displays the tracker's identity — the addon name, short category letters, or both, depending
on per-tracker settings.

#### Auto-Hide Title Buttons

If **Auto-Hide Title Buttons** is enabled in the Style settings, the title bar buttons fade
out when you are not hovering the title bar and fade back in when you move your cursor over
it.

#### Tiling Icon (right side, when tiling is active)

Appears when this tracker belongs to a tile group. Click it to open a menu with a
**Disable Tiling For This Tracker** option.

#### Burger Menu (≡, second from right)

Opens a small dropdown for bulk header actions:

| Option | What it does |
|---|---|
| **Expand all headers** | Expands every collapsed header in this tracker. |
| **Collapse all headers** | Collapses every expanded header in this tracker. |
| **Collapse Quest Headers** | Collapses only zone headers in the Quests section. |
| **Show Hidden Trackers** | Brings back any tracker windows you closed with the X button. Only shown when at least one other tracker with content is currently hidden. |

#### Close Button (✕, far right)

Hides the tracker window. Bring it back through **Show Hidden Trackers** in another
tracker's burger menu, or via **Show Tracker** in Settings → Trackers → [Tracker Name].

---

## Interacting with Quests

### Quest Tiles

| Click | Action |
|---|---|
| **Left click** | Super-tracks the quest (places the minimap pin). If the quest is fully complete, shows the completion UI instead. |
| **Shift + Left click** | Toggles the quest as user-hidden. |
| **Ctrl + Left click** | Inserts a quest link into chat. |
| **Alt + Left click** | Opens the Quest Log to that quest's entry. |
| **Right click** | Opens the quest detail / turn-in frame. |

### Achievement Tiles

| Click | Action |
|---|---|
| **Ctrl + Left click** | Inserts an achievement link into chat. |
| **Shift + Left click** | Toggles the achievement as user-hidden. |
| **Right click** | Opens the Achievements frame. |

### Recipe Tiles

Each tracked recipe appears as a title row showing the recipe name. When you have enough
reagents to craft at least one, the count is appended: `Recipe Name - [N]`. Below it, each
required reagent shows a progress line: `- [have/needed] Reagent Name`, colored red when
short and green when the requirement is met. Recraft entries are labelled accordingly.

Hovering a recipe tile shows the item tooltip for the recipe's output item.

| Click | Action |
|---|---|
| **Shift + Left click** | Untracks the recipe (removes it from the tracker). |
| **Right click** | Opens the professions UI to that recipe's entry. Not available for recraft entries. |

### Zone / Category Headers

**Left click** a header to collapse or expand it. The collapsed state persists across
sessions per character.

**Shift + Left click** a zone header in the Quests category to bulk-hide or bulk-unhide all
quests under it:

- If **any** quest under that header is currently hidden, Shift+click **unhides all** of them.
- If **none** are hidden, Shift+click **hides all** of them.

The `(N Hidden)` count on the header updates immediately.

**Campaign headers** show a tooltip on hover with the current chapter name and completion
state.

### Quest Tooltips

Hovering over a quest tile shows a tooltip with reward previews — items, experience, money,
and reputation. If **Show Party Quest Progress** is enabled and you are in a group, the
tooltip also shows each party member's current progress on that quest.

---

## Categories

| Category | What it shows |
|---|---|
| **Quests** | All normal quests in your quest log, grouped by zone and campaign. Always on the Main Tracker. |
| **World Quests** | World quests available in the current zone. Optional live countdown timer on each entry. |
| **Bonus Objectives** | Bonus objective tasks active in your current area. |
| **Scenario** | The current scenario or dungeon encounter: stage name, objectives, progress bars, and Mythic+ timer block. |
| **Achievements** | Achievements you have set to track in the Achievements UI. |
| **Recipes** | Crafting recipes currently tracked in your professions UI, with per-reagent progress lines and a craftable count. |

The vertical display order of categories and where separators are drawn can be changed under
**Settings → Trackers → Category Display Order**.

---

## Multiple Trackers

zQuestLog supports up to five simultaneous tracker windows: the **Main Tracker** (slot 0)
and **Trackers 1 through 4**.

To set up an additional tracker:

1. Open **Settings → Trackers**.
2. Under **Category Assignment**, use the dropdown next to a category (World Quests, Bonus
   Objectives, Scenario, or Achievements) to assign it to a tracker slot.
3. The chosen tracker window opens automatically.

Each tracker has its own position, size, scroll bar, background, and title bar — all
configured independently under **Settings → Trackers → [Tracker Name]**.

Trackers can be anchored together using the [Tiling](#settings--tiling) system.

---

## Quest Item Buttons

When a quest has a usable item, zQuestLog shows a clickable icon button for it. A cooldown
swipe displays when the item is on cooldown. There are two display modes.

### Inline Mode (default)

Item buttons appear directly to the right of the quest title inside the tracker window. They
scroll with the content.

### Panel Mode

When **Show Inline** is turned off, each tracker gets a dedicated floating panel for its
item buttons. The panel can be:

- **Anchored** to any of 8 positions around the tracker window
- **Free-floating** — drag it anywhere, and the position is saved

Buttons stack in a configurable direction, and the panel has its own optional background
and border.

### Quest Numbering

In panel mode, **Show Quest Numbering** places a small numbered badge on each item button
and on the corresponding quest title row. Because the panel lives outside the tracker window,
this lets you match a button to its quest at a glance. Assigned numbers are stable across
sessions.

### Combat Behavior

Item buttons will not move, update, or re-assign their item during combat. They hold their
last state for the duration of the fight. You can still click and use them normally — updates
take effect when combat ends.

---

## Slash Commands

| Command | Description |
|---|---|
| `/zql options` | Open the settings panel. |
| `/zql lock` | Toggle frame lock. Prevents all tracker windows from being dragged or resized. |
| `/zql show <0-4>` | Show a tracker window by ID (0 = Main Tracker). |
| `/zql listtrackers` | Print all active trackers and their assigned categories to chat. |
| `/zql refresh` | Force-rebuild all active tracker windows. |
| `/zql info` | Print addon version and credits to chat. |
| `/zql debug` | Toggle debug mode. |

---

## Keybinds

zQuestLog registers nine bindings in the WoW **Key Bindings** panel under the **zQuestLog**
header. All bindings are unbound by default — assign keys from
**Escape → Key Bindings → scroll to the zQuestLog section**.

| Binding | Action |
|---|---|
| **Toggle Main Tracker** | Show or hide the Main Tracker (slot 0). |
| **Toggle Tracker 1** | Show or hide Tracker 1. |
| **Toggle Tracker 2** | Show or hide Tracker 2. |
| **Toggle Tracker 3** | Show or hide Tracker 3. |
| **Toggle Tracker 4** | Show or hide Tracker 4. |
| **Toggle All Trackers** | Smart toggle: if any tracker with assigned content is currently hidden, shows all of them; if all are visible, hides all. |
| **Toggle Hidden Quests** | Toggles the global **Show User-Hidden Quests** setting — identical to clicking the eye button on the title bar. |
| **Toggle Dungeon Mode** | Toggles the **Dungeon Quest Filter** — identical to the dungeon button on the Main Tracker title bar. |
| **Collapse/Expand All Trackers** | Smart toggle: if any tracker is expanded, minimizes all; if all are already minimized, expands all. |

> Bindings that target a specific tracker (Toggle Main Tracker, Toggle Tracker 1–4) do
> nothing if that tracker has no categories assigned to it.

---

## Settings — General

Open with `/zql options` then click the **General** tab.

The General tab has a root set of toggles plus two sub-sections, **Sorting** and
**Tracking**, accessible from the sidebar.

### Root Toggles

| Setting | Description |
|---|---|
| **Lock All Frames** | Prevents all tracker windows from being dragged or resized. |
| **Smooth Scrolling** | Animates scroll movement to glide to each new position instead of jumping. |
| **Show Default Tracker** | Shows or hides the built-in WoW objective tracker. |
| **Show User-Hidden Quests** | Globally shows quests you have Shift+clicked to hide. Same as the eye toggle on each title bar. |
| **Dungeon Quest Filter** | When inside a dungeon, hides quests unrelated to the current instance. Also available as a title bar toggle. |
| **Pixel Perfect Scale** | Scales tracker windows to align with the physical pixel grid, improving sharpness on high-DPI displays. |
| **Show Party Quest Progress** | When in a group, adds each party member's current progress on the hovered quest to its tooltip. |
| **Show TomTom Waypoint** | When TomTom is loaded, super-tracking a quest also sets a TomTom arrow for its next objective. Only visible when TomTom is active. |

**Resets:**
- **Reset General Settings** — restores all root General settings to their defaults.
- **Reset Hidden Quests** — permanently clears your per-character list of Shift+hidden quests.

---

### General > Sorting

Click **Sorting** in the sidebar under the General tab.

| Setting | Description |
|---|---|
| **Use Blizzard Quest Order** | Zone headers follow Blizzard's quest log ordering instead of alphabetical. Sorting modifiers (zone-first, nearest) still apply on top. |
| **Current Zone First** | Moves the zone header matching your current zone to the top of the quest list. Campaign headers always appear above it. |
| **Current Quest Area** | Groups quests whose objective area you are currently standing in under a *Current Area* header below campaigns. Highlights quests immediately relevant to your position. |
| **Area Above Campaigns** | Moves the Current Area section above campaign headers. Only available when Current Quest Area is on. |
| **Sort Nearest Quests** | Re-orders quests by proximity: the zone with the closest quest floats first, and quests within each zone sort closest-first. Campaign headers remain at the top. |
| **Use Polling** | Enables a fixed-interval distance check rather than relying on event-driven updates alone. Only available when Sort Nearest Quests is on. |
| **Sort Nearest Poll Rate** | How often (1–30 seconds) the distance sort re-evaluates when polling is on. Default: 2 s. |

**Reset:** **Reset Sorting** — restores all Sorting settings to defaults.

---

### General > Tracking

Click **Tracking** in the sidebar under the General tab.

| Setting | Description |
|---|---|
| **Use WoW Tracking** | When enabled, only quests that are actively tracked in the WoW quest log are shown — your per-quest Shift+click show/hide state is ignored entirely. This mirrors the behavior of the default Blizzard tracker and is useful when you want precise control over which quests appear by tracking or untracking them directly in the quest log. |
| **Track Old Campaigns** | Groups quests from older expansion campaigns under their own campaign headers instead of treating them as regular zone quests. A confirmation dialog appears before the change takes effect. |
| **Show Mythic+ Info** | Displays the keystone timer, death count, and active affixes below the Scenario tracker when a Mythic+ key is in progress. |
| **Auto Track Nearest Quest** | Automatically super-tracks the closest quest that has a known map location. Runs on its own separate timer. |
| **Use Polling** | Enables a fixed-interval check for the nearest quest rather than relying on events alone. Only available when Auto Track Nearest Quest is on. |
| **Auto Track Poll Rate** | How often (1–30 seconds) auto-track re-evaluates when polling is on. Default: 6 s. |

#### Tracked Glow

Controls the visual indicator on the currently super-tracked quest's title row.

| Setting | Description |
|---|---|
| **Show Super Track Indicator** | Appends a gold `<<` marker after the super-tracked quest's title. |
| **Show Super Track Glow** | Draws a color glow behind the super-tracked quest's title row. |
| **Super Track Glow Color** | Color and opacity of the glow. |

#### Tracked Elements

Controls which supplementary data lines appear for tracked quests.

| Setting | Description |
|---|---|
| **Show Quest Level** | Displays a `[level]` bracket before each quest title. |
| **Show Completed Objectives** | Shows objectives that are already marked *(Done)*. When off, completed objectives are hidden. |
| **Location Hint** | Shows routing hints on all quests. When off, the hint only appears on the currently super-tracked quest. |
| **Show Completed Criteria** | Shows achievement criteria that have already been completed. |
| **Show WQ Duration** | Shows a live countdown timer on each World Quest title. |

**Resets:** Reset Tracking Settings, Reset Tracked Glow, Reset Tracked Elements.

---

## Settings — Trackers

Open with `/zql options` then click the **Trackers** tab.

### Category Assignment

The root content of the Trackers tab lets you assign categories to tracker slots.

- **Quests** is permanently assigned to the Main Tracker.
- **World Quests**, **Bonus Objectives**, **Scenario**, **Achievements**, and **Recipes**
  each have a dropdown to assign them to the Main Tracker, Tracker 1–4, or *None* to
  disable them.

**Category Display Order** — drag entries to change the vertical order categories appear
across all trackers. The default order is: Scenario → World Quests → Bonus Objectives →
Quests → Achievements.

### Per-Tracker Sub-Tabs

A sub-tab appears for each active tracker (Main Tracker, Tracker 1–4). Tracker slots with
no assigned categories are hidden from the list.

#### Visibility

| Setting | Description |
|---|---|
| **Show Tracker** | Shows or hides this tracker window. Disabled when no categories are assigned. |
| **Addon in Title** | Includes the text *zQuestLog* in the title bar. |
| **Categories in Title** | Shows short category abbreviations in the title bar. |
| **Show Title Bar** | Shows or hides this tracker's title bar. When off, the bar is collapsed and content fills the window. In Unified Title Bar mode, the topmost visible tracker in a tile group still shows the shared bar. |
| **Show Scroll Bar** | Displays a scroll bar when content overflows the window height. |
| **Show When Empty** | When enabled (the default), the tracker remains visible even when it has no content. Disable this to auto-hide the tracker when empty and reappear when content exists. |
| **Show in Instance** | When enabled (the default), the tracker is visible inside dungeons and raids. |

#### Size and Growth

| Setting | Description |
|---|---|
| **Dynamic Width** | Resizes the window width automatically to fit the longest content line. |
| **Dynamic Height** | Resizes the window height automatically to fit all tracked entries. |
| **Expand Left** | When Dynamic Width grows the window, it expands toward the left. Only available when Dynamic Width is on. |
| **Expand Up** | When Dynamic Height grows the window, it expands upward. Only available when Dynamic Height is on. |
| **Max Window Width** | Upper limit on window width (100–2000 px). |
| **Max Window Height** | Upper limit on window height (100–2000 px). |
| **Min Window Width** | Lower limit on window width (50–1000 px). |
| **Min Window Height** | Lower limit on window height (50–1000 px). |

#### Background

| Setting | Description |
|---|---|
| **Background Texture** | The texture for the tracker window background (LibSharedMedia supported). |
| **Color Overlay** | Enables a color tint layered on top of the background texture. |
| **Overlay Color** | Color and opacity of that tint. Only available when Color Overlay is on. |

#### Resets

- **Reset Tracker Appearance** — restores size limits and growth direction to defaults.
- **Reset Tracker Position** — moves this tracker to its default screen position.
- **Reset Background** — restores the background texture and overlay to defaults.

---

## Settings — Tiling

The tiling system lets tracker windows anchor to each other so they reposition as a group
and optionally match each other's dimensions.

Open with `/zql options` then click the **Tiling** tab.

### Global Settings

| Setting | Description |
|---|---|
| **Enable Tiling System** | Master toggle. Disabling it via the confirmation dialog detaches all trackers and restores their saved pre-tiling positions. |
| **Match Greatest Width** | All trackers in a tile group resize to match the widest visible member. |
| **Match Greatest Height** | All trackers in a tile group resize to match the tallest visible member. |
| **Constrict Height to Root** | Caps the combined vertical height of a tile group to the root tracker's Max Height. Requires the root tracker to have Dynamic Height enabled. |
| **Unified Title Bar** | Uses one shared title bar per tile group: the topmost visible tracker shows the full bar, while other members collapse to separator-only bars. |

### Unified Title Bar Options

These options are available when both **Enable Tiling System** and **Unified Title Bar** are on.

| Setting | Description |
|---|---|
| **Show Eye Toggle** | Shows the eye button in the unified bar. Only has effect when Tracker 0 is in the tile group. |
| **Show Dungeon Toggle** | Shows the dungeon filter button in the unified bar. Only has effect when Tracker 0 is in the tile group. |
| **Show Quest Count** | Shows the quest `N/M` count label in the unified bar. Only has effect when Tracker 0 is in the tile group. |
| **Show Addon Prefix** | Includes `zQuestLog` in the unified title text. |
| **Show Category Letters** | Includes the merged category abbreviation string in the unified title text. |

### Per-Tracker Tiling (Main Tracker, Tracker 1–4)

| Setting | Description |
|---|---|
| **Enable Tiling** | Anchors this tracker's position relative to a chosen parent tracker. Disabled when the global tiling system is off. |
| **Parent Tracker** | Which tracker this tracker attaches to. Circular chains are not allowed. |
| **Parent Anchor** | The attachment point on the parent tracker (9 positions). |
| **Child Anchor** | The attachment point on this tracker that snaps to the parent anchor point. |
| **Offset X / Y** | A pixel offset applied on top of the anchor. Useful for adding a gap between stacked trackers. |
| **Match Parent Width** | Resizes this tracker to match its parent's current width. |
| **Match Parent Height** | Resizes this tracker to match its parent's current height. |

> **Tip:** A common setup is to tile the World Quests tracker below the Main Tracker using
> *BOTTOMLEFT → TOPLEFT* so they stack vertically and scroll independently.

---

## Settings — Appearance > Fonts

Open with `/zql options` → **Appearance** → **Fonts**.

### General

Each of the three text types (Header, Title, Objective) has its own size, font face, and
rendering controls.

| Setting | Description |
|---|---|
| **Header / Title / Objective Font Size** | Point size for zone headers, quest titles, and objective lines respectively (5–32). |
| **Font Face** | Font face for each type, populated from LibSharedMedia. Default: Friz Quadrata TT. |
| **Font Flags** | Rendering style: None, Outline, Thick Outline, Monochrome, Outline + Monochrome, or Thick Outline + Monochrome. |

**Resets:** Reset Header Font, Reset Title Font, Reset Objective Font — each restores its
section independently.

### Campaign Fonts

Campaign headers and their chapter sub-lines have their own separate font controls:

| Setting | Description |
|---|---|
| **Campaign Header Size / Font / Font Flags** | Font controls for the campaign name header line. |
| **Campaign Chapter Size / Font / Font Flags** | Font controls for the chapter sub-line beneath each campaign header. |

**Resets:** Reset Campaign Header Fonts, Reset Campaign Chapter Fonts.

### Progress and Timer Bar Fonts

Progress bars and timer bars each have their own font size, face, and rendering controls,
plus X and Y label offsets and anchor positions for fine-tuning label placement.

**Resets:** Reset Progress Bar Font, Reset Timer Bar Font.

---

## Settings — Appearance > Style

Open with `/zql options` → **Appearance** → **Style**.

### UI Elements

| Setting | Description |
|---|---|
| **Show Button Backdrop** | Shows a border and background behind each title bar button. |
| **Auto-Hide Title Buttons** | Hides the title bar buttons until you hover over the title bar. |
| **Use Class Color** | Sets the UI accent color to your character's class color automatically. |
| **UI Color** | Custom accent color used for title text, scroll bar thumb, borders, and UI controls. Disabled when Use Class Color is on. |

### Quest Icons

| Setting | Description |
|---|---|
| **Show Quest Icon** | Shows an icon to the left of each quest title. |
| **Native Quest Icon Style** | Uses the default WoW quest icon style instead of the custom style. |
| **Quest Icon Size** | Size of the icon in pixels (8–64). |
| **Quest Icon Y-Offset** | Vertical offset for fine-tuning the icon's position (-20–20). |

### Progress and Timer Bars

| Setting | Description |
|---|---|
| **Progress Bar Percent** | Shows the completion percentage centered on each progress bar and omits it from the objective text below. |
| **Achievement Bar Percent** | Shows the completion percentage on achievement progress bars. |
| **Progress Bar Height** | Height of objective progress bars in pixels (4–32). |
| **Progress Bar Texture** | The statusbar texture for objective progress bars (LibSharedMedia supported). |
| **Enable Timer Bar** | Shows a timer bar beneath quests with an active countdown. |
| **Timer Bar Height** | Height of the timer bar in pixels (4–32). |
| **Timer Bar Texture** | The statusbar texture for the timer bar (LibSharedMedia supported). |

### Separator

| Setting | Description |
|---|---|
| **Show Category Separators** | Draws a dividing line between content sections (e.g. between the Scenario block and the Quest list). |
| **Use Texture** | Uses a texture graphic instead of a plain line. |
| **Use Border Texture** | Browse border textures instead of statusbar textures when picking the separator graphic. Only available when Use Texture is on. |
| **Separator Texture / Border** | The texture to use for the separator. |
| **Class Color Separator** | Colors the separator with your class color. |
| **Separator Color** | Custom color and opacity. Disabled when Class Color Separator is on. |
| **Show Campaign Separator** | Draws a separator below each campaign quest group. |
| **Show Between Campaigns** | Draws an additional separator between individual campaign groups. Only available when Show Campaign Separator is on. |

**Resets:** Reset UI Elements, Reset Quest Icons, Reset Bars, Reset Separator.

---

## Settings — Appearance > Colors

Open with `/zql options` → **Appearance** → **Colors**. Split into two sub-tabs: **Quests**
and **Others**.

### Quests Tab

**Quest Colors**

| Color | What it applies to |
|---|---|
| **Quest Header** | Zone and category header text. |
| **Objective Color** | In-progress objective text. |
| **Completed Objective** | Objective text for objectives marked *(Done)*. |
| **Color by Difficulty** | Automatically colors quest titles based on relative difficulty and completion state. When on, disables the Quest Title color picker. |
| **Quest Title** | Quest title text. Disabled when Color by Difficulty is on. |
| **Completed Quest Title** | Quest title text when the quest is ready to turn in. |

**Campaign Colors**

| Color | What it applies to |
|---|---|
| **Campaign Header** | Campaign name header text. |
| **Campaign Chapter** | Chapter sub-line beneath each campaign header. |

**World Quest Colors** — WQ Header, WQ Title, WQ Objective, and WQ Completed Objective.

**Bonus Objective Colors** — Bonus Header, Bonus Title, Bonus Objective, and Bonus Completed
Objective.

**Resets:** Reset Quest Colors, Reset World Quest Colors, Reset Bonus Objective Colors.

### Others Tab

> **Note:** This tab is hidden when **Color by Difficulty** is on. It reappears when Color
> by Difficulty is turned off.

**Achievement Colors** — Achievement Header, Achievement Title, and Achievement Objective.

**Scenario Colors**

| Color | What it applies to |
|---|---|
| **Scenario Header** | The Scenario section header. |
| **Scenario Stage** | The current stage or dungeon name line. |
| **Scenario Objective** | Scenario objective text. |
| **Scenario Completed** | Scenario objective text when completed. |

**Progress Bar Colors**

| Color | What it applies to |
|---|---|
| **Completion Color** | The color the bar changes to when the objective is complete. |
| **Progress Fill** | The filled portion of progress bars. |
| **Progress Segment** | The tick-mark dividers on progress bars. |
| **Progress Background** | The unfilled background of progress bars. |

**Timer Bar Colors**

| Color | What it applies to |
|---|---|
| **Timer Completion Color** | The color the bar changes to when the timer expires. |
| **Timer Fill** | The filled portion of the timer bar. |
| **Timer Segment** | The tick-mark dividers on the timer bar. |
| **Timer Background** | The unfilled background of the timer bar. |

**Recipe Colors** — Recipe Header, Recipe Title, Recipe Objective, and Recipe Completed
Objective.

**Resets:** Reset Achievement Colors, Reset Scenario Colors, Reset Progress Bar Colors,
Reset Timer Bar Colors, Reset Recipe Colors.

---

## Settings — Appearance > Spacing

Open with `/zql options` → **Appearance** → **Spacing**. All values are in pixels, 0–30 in
0.5-pixel steps.

| Group | Description |
|---|---|
| **Tracked Header** | Gap above and below each zone or category header row. |
| **Campaign Header** | Gap above and below each campaign name header row. |
| **Campaign Chapter** | Gap above and below each chapter sub-line. A separate **Pad First Chapter Title** toggle adds extra top padding to the first chapter of a campaign. |
| **Tracked Title** | Gap above and below each quest, world quest, bonus objective, or achievement title row. |
| **Tracked Objective** | Gap above and below each objective or criteria row. |
| **Object Buffer** | Extra gap between the last objective of one entry and the title of the next. |
| **Header Buffer** | Extra gap pushed before a zone header when other content already precedes it. |
| **Separator** | Gap above and below the category separator line. |
| **Progress Bar** | Gap above and below each progress bar row. |

Individual reset buttons are available for each group.

---

## Settings — Appearance > Quest Items

Open with `/zql options` → **Appearance** → **Quest Items**.

> Item button settings are disabled during combat.

### Core Settings

| Setting | Description |
|---|---|
| **Show Quest Items** | Master toggle. Shows clickable icon buttons for quests that have a usable item. |
| **Show Inline** | When on (default), item buttons appear beside the quest title inside the tracker. When off, buttons move to a floating panel. |
| **Show When Minimized** | When on (default), the floating panel stays visible when the tracker window is minimized. Only shown when **Show Inline** is off. |

### Floating Panel

These settings appear when **Show Inline** is off.

| Setting | Description |
|---|---|
| **Attach Mode** | Which tracker the panel follows, or *Free Float* to drag it anywhere (position saved). |
| **Anchor Side** | Which edge or corner of the target tracker the panel snaps to (8 positions). Hidden when free-floating. |
| **Growth Direction** | Direction buttons stack inside the panel: Auto, Down, Up, Left, or Right. |
| **Scale** | Scale of the entire floating panel as a percentage (1–512). |
| **Padding** | Space between items in the panel (0–32 px). |

### Panel Background

| Setting | Description |
|---|---|
| **Enable Background** | Draws a background texture behind the floating panel. |
| **Background Texture** | The texture to use (LibSharedMedia supported). |
| **Color Overlay** | Applies a color tint on top of the texture. |
| **Overlay Color** | Color and opacity of that tint. Disabled when Color Overlay is off. |

### Panel Border

| Setting | Description |
|---|---|
| **Enable Border** | Draws a border around the floating panel. |
| **Border Thickness** | Thickness in pixels (1–4). |
| **Use UI Color** | Colors the border with the current UI accent color. |
| **Border Color** | Custom color and opacity. Disabled when Use UI Color is on or border is off. |

### Quest Numbering

These settings are only visible when **Show Inline** is off.

| Setting | Description |
|---|---|
| **Show Quest Numbering** | Places a small numbered badge on each item button and on the corresponding quest title row, so you can match panel buttons to their quests at a glance. |
| **Denote Size** | Size of the numbered badge on the item button (8–32 px). |
| **Denote Attach Point** | Where the badge sits relative to the item button — 8 outside positions or 4 corner overlays. |

**Reset:** **Reset Quest Items** — restores all settings on this tab to defaults.

---

## Settings — Sounds

Open with `/zql options` then click the **Sounds** tab.

All sound pickers use LibSharedMedia and preview the selected sound immediately on selection.

| Section | Setting | Description |
|---|---|---|
| **Objective Increment** | Enable | Plays a sound when a quest objective makes partial progress (e.g. 3/10 → 4/10). |
| | Sound | The sound to play. |
| **Objective Complete** | Enable | Plays a sound when a single objective finishes but the quest is still in progress. |
| | Sound | The sound to play. |
| **Quest Completion** | Enable | Plays a sound when all objectives of a quest are done. |
| | Sound | The sound to play. |

**Reset:** **Reset Sounds** — restores all sound settings to defaults.

---

## Settings — Profiles

Open with `/zql options` then click the **Profiles** tab.

Profiles store all settings account-wide. Window positions are saved per character separately
and are not included in profiles.

### Active Profile

| Control | Description |
|---|---|
| **Current Profile** | Dropdown to switch to an existing profile immediately. |
| **New Profile** | Type a name and press Enter to create a copy of the current profile with that name and switch to it. |

### Copy From Another Profile

Choose a source profile and click **Copy Profile** to overwrite your current profile with
that source's settings. A confirmation dialog prevents accidental overwrites.

### Delete a Profile

Select a profile and click **Delete Profile**. You cannot delete the currently active
profile.

### Reset Current Profile

- **Reset Profile** — restores every setting in the current profile to the built-in defaults.
  A confirmation dialog is shown first.
- **Reset Example Profile** — recreates (or resets) the built-in *Example* profile, which
  demonstrates a fully customized look and feel. Useful as a starting point for a custom
  layout.

### Import / Export

You can share your profile using a compressed text string.

**To export:** Click **Export Profile**. A dialog opens with the export string pre-selected.
Press Ctrl+C to copy it.

**To import:** Click **Import Profile**. Paste the string into the top box, type a name for
the new profile in the bottom box, then click **Import**. The new profile is created and
activated immediately.

### Account Defaults

**Global Default Profile** — the profile that new characters start on when they first load
the addon.

---

## Tips and Tricks

- **Re-show a closed tracker** — open the burger menu on any visible tracker and choose
  **Show Hidden Trackers** if it appears.
- **Instant section reset** — use the individual Reset buttons in each Appearance sub-tab
  rather than a full profile reset to restore specific settings without losing everything else.
- **Stacking trackers cleanly** — enable tiling and set the child tracker's **Child Anchor**
  to *Top Left* with **Parent Anchor** *Bottom Left* and Offset Y = 0 for a seamless stack.
- **Class-colored everything** — enable **Use Class Color** in Style and **Class Color
  Separator** in the Separator section for a cohesive class theme without touching individual
  color pickers.
- **Profiles as layouts** — create a *Compact* profile with small fonts and tight spacing and
  a *Detailed* profile with larger fonts and more padding, then switch between them instantly.
- **Auto-hide buttons for a cleaner look** — enable **Auto-Hide Title Buttons** to keep the
  title bar minimal until you need controls.
- **Current Quest Area for dense hubs** — enable **Current Quest Area** when doing packed
  outdoor quest hubs to instantly see only the quests relevant to where you are standing.
- **TomTom arrow** — if you use TomTom, enable **Show TomTom Waypoint** so super-tracking a
  quest automatically pulls up the navigation arrow.
