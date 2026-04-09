# DnD Map Maker
**Cartographer's Workshop v1.4**

A self-contained, browser-based map maker for tabletop RPG sessions. No installation, no account, no internet required after download. Open `dnd-map-maker.html` in any modern browser and start drawing.

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
| `S` | Select tool — click and drag tokens, markers, or doors |
| `P` | Paint tool |
| `F` | Fill (flood fill) tool |
| `E` | Erase tool |
| `M` | Marker tool |
| `T` | Token tool |
| `G` | Add Fog tool |
| `V` | Vision Reveal tool |
| `D` | Door tool |
| `1` – `9` | Select terrain by number |
| `+` / `=` | Zoom in |
| `-` | Zoom out |
| `0` | Fit map to window |
| `Ctrl+S` | Save map (browser storage) |
| `Ctrl+Z` | Undo |
| Middle mouse button | Pan the map |
| Right-click on any object | Remove it (token, marker, or door) |

---

## Tools

**Select** — Click any token, marker, or door and drag it to a new position. Works on all object types without needing to switch colors or settings first. The selected object is highlighted while dragging.

**Paint** — Click and drag to paint terrain tiles. Use the terrain palette to pick a surface type. Brush size is adjustable.

**Fill** — Flood-fills a contiguous region with the selected terrain. Good for filling large open rooms quickly.

**Erase** — Paints void (empty) tiles. Same as painting with the Void terrain.

**Marker** — Places named markers on the map. Pick the marker type from the Markers panel first, then click to place. Click the same marker type again on the same tile to remove it. Markers are hidden from players by fog.

**Token** — Click to place a token. Click the same tile again to remove it. Choose a player token color (circular, numbered) or an enemy token color (square, unlabeled) from the token panels. Clicking an enemy color automatically switches to the Token tool.

**Add Fog** — Paints fog of war over tiles. Use in conjunction with the Fog of War mode buttons.

**Vision Reveal** — Hover over the map to preview what the party can see from that position, including wall-aware line of sight. Click to commit the reveal. Radius and presets are in the Vision Reveal panel.

**Door** — Left-click an empty tile to place a door. Left-click an existing door to toggle it open or closed. Right-click a door to remove it. Orientation is auto-detected from surrounding walls.

---

## Fog of War

The **Fog of War** section in the sidebar has two view modes:

- **DM View** — Fog is shown as a blue hatched tint so you can see all terrain underneath. Use this for map preparation.
- **Player View** — Fog is solid black. Nothing is visible beneath it. Use this when sharing your screen with players.

The **☁ Fog All** and **☀ Reveal All** buttons sit in the top bar above the canvas, clearly separated from the Vision Reveal tool. Use **Fog All** at the start of a session to cover the entire map, then switch to Player View and use Vision Reveal to uncover areas as the party explores.

---

## Vision Reveal & Line of Sight

1. Press `V` to select the Vision Reveal tool.
2. Hover over the party's current position — an amber preview circle shows exactly which tiles will be revealed, with shadowed areas behind walls.
3. Click once to commit the reveal. One click = one turn of exploration.
4. The **Wall-aware LOS** checkbox makes vision block through Wall and Cave Rock tiles, and through closed doors. Uncheck it for a simple circular reveal.

**Presets:**

| Preset | Radius | Typical use |
|--------|--------|-------------|
| Torch | 3 tiles | Underground, low light |
| Darkvision | 5 tiles | Standard adventurer sight |
| Scout | 7 tiles | Open terrain, daylight |

The radius slider lets you set any value from 1–12 tiles. The hint below it always shows the exact distance and movement cost at your current scale.

---

## Doors

- **Place:** Select the Door tool (`D`) and left-click any empty tile.
- **Toggle open/closed:** Left-click an existing door.
- **Remove:** Right-click a door (works with any tool active).
- Closed doors block Line of Sight. Open doors let vision through.
- Orientation (horizontal or vertical bar) is auto-detected from adjacent wall tiles.
- Generated dungeons and buildings auto-place doors at all doorways and corridor junctions.

---

## Tokens

**Player tokens** are circular and numbered (1–9, A–Z). Pick a color from the Player Tokens panel, then use the Token tool to place them. Each color is independent — you can have multiple tokens of the same color at different numbers.

**Enemy tokens** are square with an X mark and carry no label. Clicking any enemy color swatch in the Enemy Tokens panel automatically switches to the Token tool. Because they're unlabeled, the number of enemies is never spoiled if a player glimpses the screen.

Both token types are hidden from players when their tile is under fog.

To **move** any token without worrying about what color is selected, use the **Select tool** (`S`) — click the token and drag it directly.

---

## Scale & Distance

Set how many metres or feet each tile represents in the **Scale & Distance** panel. The map shows a live scale bar in the bottom-left corner with alternating segments and tick labels.

**Default DnD 5e:** 1 tile = 5 ft (1.5 m). One move action = 6 tiles (30 ft).

Quick presets: **5 ft**, **10 ft**, **5 m**, **10 m**. The Vision Reveal hint updates automatically to show how many tiles equal one movement action at the current scale.

---

## Saving & Loading

**Browser saves** (💾 Save Map) store your map in the browser's local storage. They persist between sessions as long as you use the same browser on the same device. Each person who opens the file has their own isolated storage — saves are not shared.

**JSON export/import** (📤 / 📥) saves a portable `.json` file you can back up, share, or load on any device. This is the recommended way to transfer maps between machines or keep permanent backups. Scale settings, doors, markers, and tokens are all included.

**PNG download** exports the current canvas as an image. **Download (No Fog)** exports the DM version with all fog removed and all markers visible — useful for printing or sharing a finished map image.

---

## Frequently Asked Questions

**Can I run this offline?**
Yes. The file has no external dependencies. Download `dnd-map-maker.html` and open it directly in Chrome, Firefox, Safari, or Edge. No internet connection needed.

**How do I share it with my players?**
Host the file for free on Netlify Drop (drag and drop at netlify.com/drop) or GitHub Pages. Players open the link in their browser. Each person's saves are local to their own device.

**My saves disappeared — what happened?**
Browser local storage is tied to the specific browser and device. If you cleared your browser data or switched browsers, saves will be gone. Use **Export JSON** regularly to keep portable backups.

**Can two people edit the same map at the same time?**
No — this is a single-user local tool. There's no real-time sync. To share a map with a co-DM, export it as JSON and send the file.

**How do I show the map to players without revealing everything?**
Use **Player View** (fog is solid black) and share your screen. Use the Vision Reveal tool to uncover areas turn by turn. Markers, tokens, and unexplored tiles are all hidden by fog in Player View.

**The vision reveal isn't blocking on walls — why?**
Make sure the **Wall-aware LOS** checkbox is ticked in the Vision Reveal panel. Also confirm the tiles you expect to block are painted as Wall or Cave Rock — other terrain types like Stone Floor or Dirt do not block LOS.

**How do I remove a token, marker, or door?**
Right-click it with any tool active. You can also use the Select tool and right-click.

**How do I move a token without switching colors?**
Use the Select tool (`S`). Click any token and drag it to a new tile — no need to know its color or number.

**Can I resize the map after I've already drawn on it?**
Yes. Changing the Grid Size preserves existing tiles — it crops if you go smaller, or pads with void tiles if you go larger.

**How do I print a map?**
Click **⬇ Download (No Fog)** to get a PNG, then print from any image viewer. For best print quality, zoom in before downloading to get a higher-resolution canvas export.

**Why does right-click not open a context menu on the map?**
Right-click is captured by the canvas to remove objects. It works normally outside the canvas area.

---

## Terrain Reference

| # | Terrain | LOS blocking |
|---|---------|-------------|
| 0 | Void | No |
| 1 | Stone Floor | No |
| 2 | Dirt | No |
| 3 | Grass | No |
| 4 | Water | No |
| **5** | **Wall** | **Yes** |
| 6 | Wood Floor | No |
| 7 | Sand | No |
| 8 | Lava | No |
| 9 | Ice | No |
| 10 | Road | No |
| **11** | **Cave Rock** | **Yes** |
| 12 | Swamp | No |
| 13 | Magic Floor | No |
| 14 | Deep Water | No |
| 15 | Carpet | No |

---

## Marker Reference

| Marker | Use |
|--------|-----|
| 🟢 Entrance | Party starting point — surrounding tiles auto-reveal when placed |
| 🔴 Exit | Portal, escape route, or session objective |
| 💰 Loot | Treasure chest or item of interest |
| ⚠ Trap | Hidden or known hazard |
| 💀 Boss | Major encounter location |
| 🔮 Secret | Hidden door, passage, or secret area |
| ⬇ Stairs Down | Descending stairs or ladder |
| ⬆ Stairs Up | Ascending stairs or ladder |
| 📝 Note | General DM note or point of interest |

All markers are hidden from players when covered by fog.

---

## Changelog

### v1.4
- **Select tool** (`S`) — click and drag any token, marker, or door to reposition it without needing to match colors or switch settings
- **Right-click to remove** — right-clicking any token, marker, or door removes it, regardless of active tool
- **Enemy tokens** — new unlabeled square tokens with an X mark; clicking an enemy color swatch auto-selects the Token tool; count is never shown so hidden enemies aren't spoiled
- **Fog All / Reveal All moved** to a dedicated top bar above the canvas, clearly separated from the Vision Reveal tool and Vision section
- **Door left-click simplified** — left-click an empty tile to place, left-click an existing door to toggle open/closed (right-click to remove)
- Player token section renamed and clarified; enemy token section added below it

### v1.3
- **Doors** — place doors that render as horizontal or vertical bars; auto-detect orientation from adjacent walls; toggle open/closed
- **Wall-aware Line of Sight** — Vision Reveal now raycasts through the map; walls and closed doors block vision; LOS shadow shown in preview
- Generated dungeons and buildings auto-place doors at doorways and corridor junctions
- Right-click (v1.3 behavior, now superseded by v1.4) toggled door state
- LOS toggle checkbox added to Vision Reveal panel

### v1.2
- **Vision Reveal tool** (`V`) — hover to preview a radius-based reveal with amber overlay and tile count; click to commit; one click per turn workflow
- **Wall-aware LOS** foundation (completed in v1.3)
- **Scale & Distance panel** — metres or feet per tile, quick presets, live scale bar drawn on canvas with alternating segments and tick labels
- **Entrance auto-reveal** — placing an Entrance marker clears a 2-tile radius of fog automatically; green dashed halo shows the boundary
- Scale bar saved with map in JSON exports and localStorage

### v1.1
- **Markers** — 9 marker types: Entrance, Exit, Loot, Trap, Boss, Secret, Stairs Down, Stairs Up, Note; each with distinct canvas-drawn icons
- **Fog of War redesigned** — DM View (blue tint), Player View (solid black), and former Reveal Mode (replaced by Vision tool in v1.2)
- Markers and tokens hidden by solid fog in Player View
- Generated maps auto-place relevant markers (entrance at start, exit at end, loot in mid rooms, traps in dungeons)
- Token color picker added
- JSON export/import added
- Download (No Fog) export added
- Undo (Ctrl+Z) up to 30 steps

### v1.0
- Initial release
- Tile-based canvas map editor with 16 terrain types and texture patterns
- Fog of war paint and reveal brushes
- Token placement with color selection and auto-labeling
- Procedural map generation: Cave, Dungeon, Building, Forest, Village, Ruins, Coastal (7 types)
- Zoom (scroll wheel, +/−), middle-mouse pan
- Grid size selection (20×20 to 80×80)
- Browser localStorage saves with name and date
- PNG download
- Keyboard shortcuts for all tools
