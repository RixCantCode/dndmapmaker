# DnD Map Maker
**Cartographer's Workshop v1.3**

A self-contained, browser-based map maker for tabletop RPG sessions. No installation, no account, no internet required after download. Open `dnd-map-maker.html` in any modern browser and start drawing.

---

## Keyboard Shortcuts

| Key | Action |
|-----|--------|
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
| Right-click | Toggle door open / closed (works with any tool active) |

---

## Tools

**Paint** — Click and drag to paint terrain tiles. Use the terrain palette to pick a surface type. Brush size is adjustable.

**Fill** — Flood-fills a contiguous region with the selected terrain. Good for filling large open rooms quickly.

**Erase** — Paints void (empty) tiles. Same as painting with the Void terrain.

**Marker** — Places named markers on the map. Pick the marker type from the Markers panel first, then click to place. Click the same marker type again on the same tile to remove it. Markers are hidden from players by fog.

**Token** — Click to place a lettered token for a player, NPC, or monster. Click again to remove. Choose token color from the Token Color panel.

**Add Fog** — Paints fog of war over tiles. Use in conjunction with the Fog of War mode buttons.

**Vision Reveal** — Hover over the map to preview what the party can see from that position. Click to commit the reveal. Radius and presets are in the Vision Reveal panel. Respects wall-aware LOS when enabled.

**Door** — Left-click to place or remove a door. Right-click any door to toggle it open or closed. Orientation is auto-detected from surrounding walls.

---

## Fog of War

The sidebar has two modes:

- **DM View** — Fog is shown as a blue hatched tint. You can see all terrain underneath. This is for map preparation.
- **Player View** — Fog is solid black. Nothing is visible beneath it. Use this when sharing your screen with players.

Switch between them freely at any time. Use **☁ Fog Entire Map** before a session to cover everything, then switch to Player View and use the Vision Reveal tool to uncover areas as the party explores.

---

## Vision Reveal & Line of Sight

1. Press `V` to select the Vision Reveal tool.
2. Hover over the party's current position on the map — an amber preview shows exactly which tiles will be uncovered.
3. Click to reveal that area. One click = one turn of exploration.
4. The **Wall-aware LOS** checkbox (in the Vision Reveal panel) makes vision block realistically through wall tiles and closed doors. Disable it for a simpler circular reveal.

**Presets:**
| Preset | Radius | Notes |
|--------|--------|-------|
| Torch | 3 tiles | Close quarters, underground |
| Darkvision | 5 tiles | Standard adventurer sight |
| Scout | 7 tiles | Open terrain, daylight |

You can also drag the radius slider for any value from 1–12 tiles.

---

## Doors

- **Place:** Select the Door tool (`D`) and left-click any tile.
- **Remove:** Left-click a door again with the Door tool.
- **Toggle open/closed:** Right-click a door with any tool active.
- Closed doors block Line of Sight. Open doors let vision through.
- Door orientation (horizontal or vertical bar) is auto-detected from surrounding wall tiles.
- Generated dungeons and buildings auto-place doors at doorways.

---

## Scale & Distance

Set how many metres (or feet) each tile represents in the Scale & Distance panel. The map displays a live scale bar in the bottom-left corner.

**Default DnD 5e:** 1 tile = 5 ft / 1.5 m. One move action = 6 tiles (30 ft).

Quick presets: **5 ft**, **10 ft**, **5 m**, **10 m**. The Vision Reveal hint updates automatically to show how many tiles equal one movement action at your current scale.

---

## Saving & Loading

**Browser saves** (💾 Save Map) store your map in the browser's local storage. They persist between sessions as long as you use the same browser on the same device. Each person who opens the file has their own isolated storage.

**JSON export/import** (📤 / 📥) saves a portable `.json` file you can back up, share, or load on any device. This is the recommended way to transfer maps between machines.

**PNG download** exports the current canvas view. "Download (No Fog)" exports the DM version with all fog removed and all markers visible — useful for printing or sharing a finished map.

---

## Frequently Asked Questions

**Can I run this offline?**
Yes. The file has no external dependencies. Download `dnd-map-maker.html` and open it directly in Chrome, Firefox, Safari, or Edge. No internet connection needed.

**How do I share it with my players?**
Host the HTML file for free on Netlify Drop (drag and drop at netlify.com/drop) or GitHub Pages. Players open the link in their browser. Each person's saves are local to their own browser.

**My saves disappeared — what happened?**
Browser local storage is tied to the specific browser and device. If you cleared your browser data or switched browsers, saves will be gone. Use **Export JSON** regularly to keep portable backups.

**Can two people edit the same map at the same time?**
No — this is a single-user local tool. There's no real-time sync. If you want to share a map with a co-DM, export it as JSON and send them the file.

**How do I show the map to players without revealing my notes?**
Use **Player View** mode (fog is solid black) and share your screen or use the Vision Reveal tool to uncover areas in real time. Markers, tokens, and unexplored terrain are all hidden by fog in Player View.

**The vision reveal isn't blocking on walls — why?**
Make sure the **Wall-aware LOS** checkbox is ticked in the Vision Reveal panel. Also check that the tiles you expect to block are painted as Wall (dark square) or Cave Rock terrain — other terrain types like Stone Floor or Dirt don't block LOS.

**Can I change what counts as a wall for LOS?**
Not through the UI currently — the blockers are Wall (tile 5) and Cave Rock (tile 11). If you want a thick stone pillar to block LOS, paint it as Wall.

**How do I remove all fog at once?**
Click **☀ Reveal Entire Map** in the Fog of War panel.

**Can I resize the map after I've already drawn on it?**
Yes. Changing the Grid Size preserves existing tiles — it crops if you go smaller, or pads with void tiles if you go larger.

**Why does right-click not open a context menu?**
Right-click is captured by the map canvas to toggle doors. Right-clicking outside the map canvas works normally.

**How do I print a map?**
Click **⬇ Download (No Fog)** to get a PNG with all fog removed, then print from any image viewer. For best results, zoom in before downloading to get a higher-resolution export.

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
| 🟢 Entrance | Where the party starts — surrounding tiles auto-reveal when placed |
| 🔴 Exit | Portal, door out, or objective |
| 💰 Loot | Treasure chest or item of interest |
| ⚠ Trap | Hidden or known hazard |
| 💀 Boss | Major encounter |
| 🔮 Secret | Hidden door, secret passage, or hidden area |
| ⬇ Stairs Down | Descending stairs or ladder |
| ⬆ Stairs Up | Ascending stairs or ladder |
| 📝 Note | General DM note or point of interest |

All markers are hidden from players when those tiles are under fog.
