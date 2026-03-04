# zQuestLogIssues
Issues for zQuestLog

# zQuestLog — Usage Guide

zQuestLog is a replacement for the default World of Warcraft quest tracker. It gives you a
resizable, scrollable window with full color, font, spacing, and sound customization, plus
support for multiple simultaneous tracker windows and a flexible tiling / anchoring system.

Open the settings panel at any time with:

```
/zql
```

---

## Table of Contents

1. [The Tracker Window](#the-tracker-window)
2. [Interacting with Quests](#interacting-with-quests)
3. [Categories](#categories)
4. [Multiple Trackers](#multiple-trackers)
5. [Quest Item Buttons](#quest-item-buttons)
6. [Settings — General](#settings--general)
7. [Settings — Trackers](#settings--trackers)
8. [Settings — Tiling](#settings--tiling)
9. [Settings — Appearance > Fonts](#settings--appearance--fonts)
10. [Settings — Appearance > Style](#settings--appearance--style)
11. [Settings — Appearance > Colors](#settings--appearance--colors)
12. [Settings — Appearance > Spacing](#settings--appearance--spacing)
13. [Settings — Appearance > Quest Items](#settings--appearance--quest-items)
14. [Settings — Sounds](#settings--sounds)
15. [Settings — Profiles](#settings--profiles)

---

## The Tracker Window

<!-- SCREENSHOT: Full tracker window with all title-bar buttons labeled -->

The tracker window consists of a **title bar** across the top and a **scrollable content area**
below it. The title bar holds several controls, described left to right.

### Title Bar Controls

#### Eye Toggle (far left)

The eye icon toggles **Show User-Hidden Quests**. When the eye is open, quests you have
previously hidden with Shift+click are shown in a dimmed state so you can still see them.
When the eye is closed they are fully hidden. This is a global setting shared across all
tracker windows.

#### Quest Count (next to the eye)

When the **Quests** category is active, a small `N/M` counter appears showing how many quests
are tracked versus your character's quest log cap. Clicking it toggles the same
Show User-Hidden Quests setting as the eye icon.

#### Title Text (center)

Displays the tracker's identity. You can control what appears here per tracker in
**Settings → Trackers → \[Tracker Name\]**:

- **Addon in Title** — shows the text *zQuestLog* in the title bar.
- **Categories in Title** — shows short category letters (e.g. *Q · W · S*) indicating which
  content types are displayed.

#### Dungeon Filter Button (right side, instance only)

This button only appears on the **Main Tracker** while you are inside a dungeon or raid. It
toggles the **Dungeon Quest Filter**, which hides quests that are unrelated to the current
instance so you only see the quests relevant to where you are.

#### Tiling Icon (right side, when tiling is active)

Appears when this tracker is part of a tile group. Click it to open a small menu with a
**Disable Tiling For This Tracker** option. Hovering shows a *Tile Group* tooltip.

#### Burger Menu (≡)

Opens a small dropdown menu with bulk header actions:

| Option | What it does |
|---|---|
| **Expand all headers** | Expands every collapsed zone/category header in this tracker. |
| **Collapse all headers** | Collapses every expanded zone/category header in this tracker. |
| **Collapse Quest Headers** | Collapses only the zone headers inside the Quests section. Only shown when the Quests category is active. |
| **Show Hidden Trackers** | Brings back any tracker windows you have closed via the X button. Only shown when at least one other tracker with content is currently hidden. |

<!-- SCREENSHOT: Burger menu open showing all four rows -->

#### Close Button (✕, far right)

Hides the tracker window. The window is not destroyed — you can bring it back through
**Show Hidden Trackers** in another tracker's burger menu, or by enabling
**Show Tracker** in Settings → Trackers → \[Tracker Name\].

---

## Interacting with Quests

<!-- SCREENSHOT: Quest row showing the supertrack glow indicator and << marker -->

### Quest Tiles

| Click | Action |
|---|---|
| **Left click** | Super-tracks the quest (places the minimap pin and route arrow on it). If the quest is fully complete and ready to turn in, shows the completion UI instead. |
| **Shift + Left click** | Toggles the quest as user-hidden. Hidden quests disappear from the tracker unless **Show User-Hidden Quests** is on. |
| **Ctrl + Left click** | Inserts a quest link into chat. |
| **Alt + Left click** | Opens the Quest Log to that quest's entry. |
| **Right click** | Opens the quest detail / turn-in frame. |

<!-- SCREENSHOT: Before/after Shift-click hiding a quest -->

### Achievement Tiles

| Click | Action |
|---|---|
| **Ctrl + Left click** | Inserts an achievement link into chat. |
| **Shift + Left click** | Toggles the achievement as user-hidden. |
| **Right click** | Opens the Achievements frame and navigates to that achievement. |

### Zone / Category Headers

**Left click** a header to collapse or expand the quests beneath it. The collapsed state is
saved per character and persists across sessions.

**Shift + Left click** a zone header in the Quests category to bulk-hide or bulk-unhide all
quests under it at once:

- If **any** quest under that header is currently hidden, Shift+click **unhides all** of them.
- If **no** quests are hidden, Shift+click **hides all** of them.

This only works on regular zone headers in the Quests section. World Quests, Bonus
Objectives, Scenario, and Achievement headers Shift+click normally (collapse/expand).
The `(N Hidden)` count on the header updates immediately to reflect the change.

**Campaign headers** also show a tooltip on hover with details about the current campaign
chapter.

---

## Categories

The tracker can display up to five categories of content. Each can be assigned to any tracker
window (see [Multiple Trackers](#multiple-trackers) below).

| Category | What it shows |
|---|---|
| **Quests** | All normal quests in your quest log, grouped by zone and campaign. Always assigned to the Main Tracker and cannot be moved. |
| **World Quests** | World quests available in the current zone. Optionally shows a live countdown timer on each title. |
| **Bonus Objectives** | Bonus objective tasks active in your current area. |
| **Scenario** | The current scenario or dungeon encounter tracker (stage name, objectives, progress bars). |
| **Achievements** | Achievements you have manually set to track in the Achievements UI. |

The vertical display order of categories within a tracker and the point at which separators
are drawn can be adjusted in **Settings → Trackers → General → Category Display Order**.

---

## Multiple Trackers

<!-- SCREENSHOT: Two trackers side by side, one with World Quests and one with Quests -->

zQuestLog supports up to five simultaneous tracker windows: the **Main Tracker** (slot 0) and
**Trackers 1 through 4**.

To set up an additional tracker:

1. Open **Settings → Trackers → General**.
2. Under **Category Assignment**, use the dropdown next to a category (World Quests, Bonus
   Objectives, Scenario, or Achievements) to assign it to a tracker slot.
3. The chosen tracker window will open automatically and display that category.

Each tracker has its own position, size, scroll bar, background, and title bar — all
configured independently under **Settings → Trackers → \[Tracker Name\]**.

Trackers can be anchored together using the [Tiling](#settings--tiling) system.

---

## Quest Item Buttons

<!-- SCREENSHOT: Quest row with an item button icon visible to the right of the title -->

When a quest has a usable item (a "quest item" that appears on your action bar in the default
UI), zQuestLog shows a clickable icon button for it directly in the tracker. You can use the
item by clicking the button, and a cooldown swipe displays when the item is on cooldown.

There are two ways these buttons can be displayed, controlled by **Show Inline** in
**Settings → Appearance → Quest Items**.

### Inline Mode (default)

Item buttons appear directly to the right of the quest title inside the tracker window. They
scroll with the content and clip to the visible scroll viewport, so they only appear when
their quest row is on screen.

### Panel Mode

When **Show Inline** is turned off, each tracker gets a dedicated floating panel that holds
all of that tracker's item buttons grouped together. The panel can be:

- **Anchored** to any of 8 positions around its tracker window (right, left, above, below,
  and the four corners)
- **Free-floating** — drag it anywhere and the position is saved
- Set to follow a **tile group's root or last tracker** instead of its own window

Buttons stack inside the panel in a direction of your choice, and the panel has its own
optional background texture and border.

### Quest Numbering

In panel mode you can enable **Denote Which Quest**, which places a small numbered badge
both on each item button and on the quest's title row in the tracker. Since the buttons live
outside the tracker in a separate panel, this lets you quickly match a button to its quest
without hovering. Numbers are stable across sessions.

### Combat Behavior

Because the game restricts changes to clickable action buttons while in combat, item buttons
won't move, update, or change their assigned item during a fight. They stay in place and keep
their last-set item for the duration of combat. You can still click and use them normally
-- updates just take effect once combat ends.

---

## Settings — General

Open with `/zql` then click the **General** tab.

### Display

| Setting | Description |
|---|---|
| **Lock All Frames** | Prevents all tracker windows from being dragged. |
| **Hide Default Tracker** | Hides the built-in WoW objective, scenario, and achievement tracker so it does not overlap zQuestLog. |
| **Show User-Hidden Quests** | Globally shows or hides quests you have Shift+clicked to hide. Same as the eye toggle on each tracker. |
| **Show World Quests** | Enables world quest display in the World Quests category. |
| **Show WQ Duration** | Appends a live `[HH:MM:SS]` countdown on each world quest title. Refreshes every 500 ms while active. |
| **Show Bonus Objectives** | Enables bonus objective display in the Bonus Objectives category. |
| **Show Completed Achievement Objectives** | Shows criteria that are already completed when displaying tracked achievements. |
| **Hide Completed Objectives** | Hides numbered "X/Y" objectives once the line reads *(Done)*. Text-only objectives are always shown. |
| **Dungeon Quest Filter** | When inside a dungeon, hides quests unrelated to the current instance. Also available as a title bar toggle. |

### Sorting and Tracking

| Setting | Description |
|---|---|
| **Sort Nearest Quests** | Re-orders quests by proximity to your character. Campaign quests always stay at the top. The zone header with the closest quest floats to the top, and quests within each zone are sorted closest-first. Mutually exclusive with Current Zone First. |
| **Auto Track Nearest Quest** | Automatically super-tracks the closest quest that has a known map location. Runs on its own separate timer. |
| **Current Zone First** | Moves the zone header that matches your current in-game zone to the top of the quest list. Campaign headers always remain above it. Has no effect if there are no quests under your current zone's header. Mutually exclusive with Sort Nearest Quests — enabling one disables the other. |
| **Sort Nearest Poll Rate** | How often (in seconds, 1–15) the distance sort re-evaluates. Default: 2 s. |
| **Auto Track Poll Rate** | How often (in seconds, 1–15) the auto-track re-evaluates which quest is closest. Default: 6 s. |

### Resets

- **Reset General Settings** — restores all settings on this tab to their defaults.
- **Reset Hidden Quests** — permanently clears your per-character list of Shift+hidden quests.
- **Show Debug Messages** — prints internal event and layout debug output to the chat window. Useful for troubleshooting.

---

## Settings — Trackers

Open with `/zql` then click the **Trackers** tab. It contains several sub-tabs.

### General Sub-Tab

**Category Assignment** — for each content category (World Quests, Bonus Objectives,
Scenario, Achievements) select which tracker slot should display it, or *None* to disable it
entirely. Quests are always on the Main Tracker and cannot be reassigned.

**Category Display Order** — use the up (▲) and down (▼) arrows to change the vertical order
categories appear in all trackers.

### Per-Tracker Sub-Tabs (Main Tracker, Tracker 1–4)

Each tracker has its own settings page.

#### Visibility

| Setting | Description |
|---|---|
| **Show Tracker** | Shows or hides this tracker window. Disabled when the tracker has no categories assigned. |
| **Addon in Title** | Includes the text *zQuestLog* in the title bar. |
| **Categories in Title** | Shows short category abbreviations in the title bar. |
| **Show Scroll Bar** | Displays a scroll bar when content overflows the window height. |
| **Hide When Empty** | Automatically hides the tracker when it has no content. Reappears as soon as content appears. |
| **Hide in Instance** | Hides this tracker window while inside any dungeon, raid, or instance. |

#### Size and Direction

| Setting | Description |
|---|---|
| **Dynamic Width** | Resizes the window width automatically to fit the longest line of text. |
| **Dynamic Height** | Resizes the window height automatically to fit all tracked entries. |
| **Max Window Width** | Upper limit on window width (100–2000 px), applied to both dynamic sizing and manual drag-resize. |
| **Max Window Height** | Upper limit on window height (100–2000 px). |
| **Min Window Width** | Lower limit on window width (50–1000 px); also sets the resize-drag minimum. |
| **Min Window Height** | Lower limit on window height (50–1000 px). |
| **Expand Left** | When Dynamic Width grows the window, it expands toward the left instead of the right. Only available when Dynamic Width is on. |
| **Expand Up** | When Dynamic Height grows the window, it expands upward instead of downward. Only available when Dynamic Height is on. |

#### Background

| Setting | Description |
|---|---|
| **Background Texture** | The texture used for the tracker window background (populated from LibSharedMedia). |
| **Color Overlay** | Enables a color tint drawn on top of the background texture. |
| **Overlay Color** | The color and opacity of that tint. Only available when Color Overlay is on. |

#### Resets

- **Reset Tracker Appearance** — restores size, max/min, and expand direction to defaults.
- **Reset Tracker Position** — moves the tracker back to its default screen position.
- **Reset Background** — restores background texture and overlay to defaults.

---

## Settings — Tiling

<!-- SCREENSHOT: Two trackers tiled vertically with the tiling icon visible in the title bar -->

The tiling system lets tracker windows be anchored to each other so they move together and
can optionally match each other's dimensions.

Open with `/zql` then click the **Tiling** tab.

### Global Settings

| Setting | Description |
|---|---|
| **Enable Tiling System** | Master toggle for the entire tiling system. Disabling it via the confirmation dialog detaches all trackers and restores their saved pre-tiling positions. |
| **Match Greatest Width** | All trackers in a tile group resize to match the widest currently-visible member. Overrides per-tracker Match Width. |
| **Match Greatest Height** | All trackers in a tile group resize to match the tallest currently-visible member. Overrides per-tracker Match Height. |
| **Constrict Height to Root** | Caps the combined vertical height of a tile group to the root tracker's Max Height. Requires the root to have Dynamic Height enabled. |

### Per-Tracker Tiling Settings

Each tracker slot has its own tiling sub-section.

| Setting | Description |
|---|---|
| **Enable Tiling** | Anchors this tracker's position relative to a chosen parent tracker. |
| **Parent Tracker** | Which tracker this tracker attaches to. Cannot create circular chains. |
| **Parent Anchor** | The attachment point on the parent tracker (e.g. *Bottom Left*, *Top Right*). |
| **Anchor Point** | The corresponding attachment point on this tracker. |
| **Offset X / Y** | A pixel offset applied on top of the anchor position. Useful for adding or removing gaps between tiled trackers. |
| **Match Width** | Resizes this tracker to match its parent's width. |
| **Match Height** | Resizes this tracker to match its parent's height. |

> **Tip:** A common setup is to tile the World Quests tracker to the bottom of the Main
> Tracker with *BOTTOMLEFT → TOPLEFT*, so they stack vertically and scroll independently.

---

## Settings — Appearance > Fonts

Open with `/zql` → **Appearance** → **Fonts**.

Controls the font size, face, and rendering style for each text type.

### Font Sizes

| Setting | Description |
|---|---|
| **Header Size** | Font size for zone and campaign header lines (5–32). |
| **Title Size** | Font size for quest and achievement title lines (5–32). |
| **Objective Size** | Font size for objective and criteria lines (5–32). |
| **Chapter Size** | Font size for campaign chapter sub-lines (5–32). |

### Font Faces

Each of the four text types (Header, Title, Objective, Chapter) has a dropdown that lists
every font registered with LibSharedMedia, including any fonts added by other addons.

### Rendering Style

Each text type also has a rendering dropdown:

| Option | Effect |
|---|---|
| **None** | Smooth, no outline (default). |
| **Outline** | Thin black outline. |
| **Thick Outline** | Heavier black outline. |
| **Monochrome** | Stops anti-aliasing; sharp pixel font with no gray edges. |
| **Outline + Monochrome** | Thin outline with no anti-aliasing. |
| **Thick Outline + Monochrome** | Heavy outline with no anti-aliasing. |

### Resets

Each font type has its own **Reset \[Type\] Font** button that restores both the face and the
rendering flag back to *Friz Quadrata TT* (the default WoW UI font) at the default size.

---

## Settings — Appearance > Style

Open with `/zql` → **Appearance** → **Style**.

### UI Accent Color

The accent color is used for the title bar text, the thin border line, the scroll bar thumb,
checkbox fills, and the quest count label.

| Setting | Description |
|---|---|
| **Use Class Color** | Sets the accent to your character's class color automatically. |
| **UI Accent Color** | Custom color and opacity. Disabled when Use Class Color is on. |

### Tracked Glow

When a quest is super-tracked (arrow/minimap pin is active), zQuestLog can visually highlight
that quest's title row.

| Setting | Description |
|---|---|
| **Show Tracked Indicator** | Appends a gold `<<` marker after the super-tracked quest's title. |
| **Show Tracked Glow** | Draws a color glow behind the super-tracked quest's title row. |
| **Glow Color** | The color and opacity of that glow. |

<!-- SCREENSHOT: Super-tracked quest with the glow and << indicator -->

### Separator

A decorative divider line can be drawn between category sections and below campaign groups.

| Setting | Description |
|---|---|
| **Show Category Separators** | Draws a separator between the Scenario, Quest, and Achievement sections. |
| **Use Texture** | Uses a texture graphic for the separator instead of a plain line. |
| **Use Border List** | Browse border textures instead of statusbar textures when picking the separator graphic. |
| **Separator Texture** | The specific statusbar or border texture to use. |
| **Use Class Color** | Colors the separator graphic with your class color. |
| **Overlay Color** | Custom color and opacity for the separator graphic. Disabled when Use Class Color is on. |
| **Show Campaign Separator** | Draws a separator line below each campaign quest group. |

---

## Settings — Appearance > Colors

Open with `/zql` → **Appearance** → **Colors**. Split into two sub-tabs: **Quests** and **Others**.

### Quests Sub-Tab

**Quest Colors**

| Color | What it applies to |
|---|---|
| **Header** | Zone and campaign header text. |
| **Objective** | In-progress objective text. |
| **Completed Objective** | Objective text for objectives marked *(Done)*. |
| **Color by Difficulty** | Automatically colors quest titles: mage-blue for quests ready to turn in, orange for in-progress quests. When this is on the Quest Title picker below is ignored. |
| **Quest Title** | Quest title text when Color by Difficulty is off. |
| **Completed Title** | Quest title text when the quest is ready to turn in (used in both modes). |

**Chapter Colors**

| Setting | What it applies to |
|---|---|
| **Campaign Chapter** | The chapter sub-line shown beneath a campaign header. |
| **Chapter Size** | Font size of chapter lines (5–32). |
| **Chapter Font** | Font face for chapter lines. |
| **Chapter Rendering** | Rendering style for chapter lines (same options as the Fonts tab). |

**World Quest Colors**

Controls the **Header**, **World Quest Title**, **Objective**, and **Completed Objective**
text colors for the World Quests section.

**Bonus Objective Colors**

Controls the **Header**, **Bonus Objective Title**, **Objective**, and **Completed Objective**
text colors for the Bonus Objectives section.

**Resets**

Individual reset buttons for Quest Colors, World Quest Colors, and Bonus Objective Colors.

---

### Others Sub-Tab

**Achievement Colors**

Controls the **Header**, **Achievement Title**, and **Objective** text colors for the
Achievements section.

**Scenario Colors**

| Color | What it applies to |
|---|---|
| **Header** | The Scenario Tracker section header. |
| **Stage / Dungeon Name** | The current stage or dungeon name line. |
| **Objective** | Scenario objective text. |
| **Completed Objective** | Scenario objective text when completed. |

**Progress Bar Colors**

| Color | What it applies to |
|---|---|
| **Progress Bar Fill** | The filled portion of progress bars (supports opacity). |
| **Progress Bar Segments** | The tick-mark divider lines on progress bars (supports opacity). |
| **Progress Bar Background** | The unfilled background of progress bars (supports opacity). |

**Resets**

Individual reset buttons for Achievement Colors, Scenario Colors, and Progress Bar Colors.

---

## Settings — Appearance > Spacing

Open with `/zql` → **Appearance** → **Spacing**.

All spacing values are in pixels, ranging from 0 to 30 in 0.5-pixel steps.

| Group | Top / Bottom | Description |
|---|---|---|
| **Tracked Header** | Both | Pixel gap above and below each zone/category header row. |
| **Tracked Title** | Both | Pixel gap above and below each quest, world quest, bonus objective, or achievement title row. |
| **Tracked Objective** | Both | Pixel gap above and below each objective or achievement criteria row. |
| **Tracked Object Buffer** | Single | Extra gap inserted between the last objective of one entry and the title of the next. Useful for visually separating quests when padding alone is not enough. |
| **Tracked Header Buffer** | Single | Extra gap pushed before a zone header when content already precedes it. |
| **Separator** | Both | Pixel gap above and below the category separator line. |
| **Progress Bar** | Both | Pixel gap above and below each progress bar row. |

Use **Reset Spacing** to restore all spacing values to their defaults at once.

---

## Settings — Appearance > Quest Items

Open with `/zql` → **Appearance** → **Quest Items**.

> **Note:** All settings on this tab are disabled during combat.

| Setting | Description |
|---|---|
| **Show Quest Items** | Master toggle. Shows a clickable icon button for any quest that has a usable quest item. |
| **Show Inline** | When on (default), item buttons appear next to the quest title inside the tracker window and scroll with the content. When off, buttons are moved to a separate floating panel. |

### Floating Panel

These settings appear when **Show Inline** is turned off.

| Setting | Description |
|---|---|
| **Attach To** | Which tracker window the panel follows: *Tracker Containing Quest*, *Tile Group Parent*, *Tile Group Last*, or *Free-Floating* (drag anywhere, position saved). |
| **Anchor Point** | Which edge or corner of the target tracker the panel snaps to. Choose from 8 positions: Right (Top/Bottom), Left (Top/Bottom), Top (Left/Right), Bottom (Left/Right). Hidden when Attach To is set to Free-Floating. |
| **Growth Direction** | The direction buttons stack inside the panel. *Auto* picks a sensible default based on the anchor; or choose Down, Up, Left, or Right explicitly. |
| **Button Size** | Size of each item button in pixels (1–512). |
| **Button Padding** | Space between the panel edge and the buttons in pixels (0–32). |

### Panel Background

| Setting | Description |
|---|---|
| **Show Background** | Draws a background texture behind the floating panel. |
| **Background Texture** | The texture to use (LibSharedMedia supported). |
| **Color Overlay** | Applies a color tint on top of the background texture. |
| **Overlay Color** | Color and opacity of that tint. Only available when Color Overlay is on. |

### Panel Border

| Setting | Description |
|---|---|
| **Show Border** | Draws a border around the floating panel. |
| **Border Thickness** | Thickness of the border in pixels (1–4). |
| **Border Color** | Color and opacity of the border. |

### Quest Numbering

| Setting | Description |
|---|---|
| **Denote Which Quest** | Shows a small numbered badge on each item button and on its corresponding quest title row in the tracker. Useful when the panel is floating away from the tracker and you need to match buttons to quests at a glance. Numbers are stable and persist across sessions. |
| **Badge Size** | Size of the number badge in pixels (8–32). |
| **Badge Attach Point** | Where the badge sits relative to its item button — 8 positions outside the button or 4 corner overlays on top of it. |

### Resets

- **Reset Quest Item Panel** — restores all settings on this tab to their defaults.

---

## Settings — Sounds

Open with `/zql` then click the **Sounds** tab.

zQuestLog can play a sound for three different quest events. All sound pickers use
LibSharedMedia and preview the selected sound immediately when you choose it.

| Section | Setting | Description |
|---|---|---|
| **Objective Increment** | Enable Objective Increment Sound | Plays a sound when a quest objective makes partial progress (e.g. 3/10 → 4/10). |
| | Objective Increment Sound | The sound to play. |
| **Objective Complete** | Enable Objective Complete Sound | Plays a sound when a single objective finishes but the quest itself is still in progress. |
| | Objective Complete Sound | The sound to play. |
| **Quest Completion** | Enable Quest Sound | Plays a sound when all objectives of a quest are done (ready to turn in). |
| | Quest Sound | The sound to play. |

---

## Settings — Profiles

Open with `/zql` then click the **Profiles** tab.

Profiles store all settings (except window position, which is saved per character) and are
shared account-wide. You can maintain separate profiles for different characters or
playstyles.

### Switching and Creating Profiles

| Control | Description |
|---|---|
| **Active Profile** | Dropdown to switch to an existing profile immediately. |
| **New Profile** | Type a name and press Enter to create a new profile and switch to it. |

### Copying Settings

Use **Copy From** to choose a source profile, then click **Copy Into Current Profile** to
overwrite your current profile's settings with those from the source. A confirmation dialog
prevents accidental overwrites.

### Deleting Profiles

Use **Profile to Delete** to select a profile, then click **Delete Profile**. You cannot
delete the currently active profile or the *Default* profile.

### Resetting

**Reset to Defaults** restores every setting in the current profile back to the addon's
built-in defaults. A confirmation dialog is shown first.

### Example Profile

**Reset Example Profile** recreates (or resets) the built-in *Example* profile, which
demonstrates a fully customized look and feel. Use it as a starting point or as a reference
for what the addon is capable of.

### Import / Export

You can share your profile with other players using a compressed text string.

**To export:** Click **Export Profile**. A dialog opens with the export string pre-selected.
Press Ctrl+C to copy it.

**To import:** Click **Import Profile**. Paste the export string into the top box, type a
name for the new profile in the bottom box, then click **Import**. The new profile is created
and activated immediately.

> **Note:** A version-mismatch warning is printed to chat if the exported string was created
> with a different version of zQuestLog, but the import still proceeds.

---

## Tips and Tricks

- **Re-show a closed tracker** — open the burger menu on any visible tracker and choose
  **Show Hidden Trackers** if it appears.
- **Instant layout reset** — use the individual Reset buttons in each Appearance sub-tab
  rather than the full profile reset to recover specific settings without losing everything.
- **Stacking trackers cleanly** — enable the Tiling system and set a child tracker's
  **Anchor Point** to *Top Left* and **Parent Anchor** to *Bottom Left* with Offset Y = 0 for
  a seamless stack with no gap.
- **Class-colored everything** — enable **Use Class Color** in both Style > UI Elements and
  Style > Separator to get a cohesive class-themed look without touching any color pickers.
- **Profiles as presets** — create a *Compact* profile with small fonts and tight spacing and
  a *Detailed* profile with larger fonts and buffers, then switch between them with the Active
  Profile dropdown.
