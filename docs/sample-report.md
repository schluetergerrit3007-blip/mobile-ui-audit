# Sample report – Mobile UI Audit

Game: our own test game (Roblox, HUD built in code) · Date: 2026-11-23

| Device | Screen | Findings |
|---|---|---|
| Samsung Galaxy A06 (small Android) | 705 × 338 | 1 |
| iPad (10th gen.) | 1179 × 819 | checked, device switch works |

## Findings – Galaxy A06
| # | Label | Element | Detail | Severity | Fix |
|---|---|---|---|---|---|
| 1 | TOPBAR_ZONE | `BRB_HUD.Compass` | 240×16, reaches 14 px into the top bar | low | Fine in the centre of the top bar (Roblox has no buttons there). If Roblox ever puts buttons in the centre, move it to `y = 0`. |

## What the first run showed (before the filters)
26 raw hits: 18 invisible 2×48 layout frames, 2 from Roblox's own touch controls, 6 children of the compass. The audit now skips containers that draw nothing, Roblox's own GUIs and children of an element already reported, so the report shows only what a player actually sees.

## Test page (deliberately broken buttons)
| Element | Expected | Found |
|---|---|---|
| Button 120×60 | none | none ✔ |
| Button 30×30 | SMALL_TARGET | SMALL_TARGET ✔ (plus TEXT_CLIPPED: "Tiny" does not fit) |
| Button past the right edge | OFFSCREEN | OFFSCREEN ✔ |
| Two overlapping buttons | TARGET_OVERLAP | TARGET_OVERLAP ✔ |
| Label with too much text | TEXT_CLIPPED | TEXT_CLIPPED ✔ |
| Label TextSize 8 | TINY_TEXT | TINY_TEXT ✔ |
| Hidden 10×10 button | none | none ✔ |

In the paid report you also get a screenshot per device with the outlines, and for "Audit + fixes" a copy of your place with the fixes applied.
