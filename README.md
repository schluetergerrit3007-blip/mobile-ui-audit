# Mobile UI Audit (Roblox Studio plugin)

One click in Roblox Studio shows the UI problems your **phone players** hit: buttons too small to tap, text that is cut off, panels hiding under the top bar or past the screen edge.

**Real result on a real game** (Samsung Galaxy A06 in the Device Simulator):

```
1 issue(s)
[OFFSCREEN] BRB_HUD.Compass · 240x16 at 232,-14 · screen 705x280 (partly outside or under the top bar)
```

The compass sat 14 px under Roblox's top bar on small phones. Nobody noticed it on screenshots.

## Checks
| Label | Finds |
|---|---|
| `OFFSCREEN` | visible elements crossing the screen edge or under the top bar |
| `SMALL_TARGET` | buttons smaller than 44 × 44 px |
| `TEXT_CLIPPED` | text that does not fit its box |
| `TINY_TEXT` | text under 11 px |
| `TARGET_OVERLAP` | buttons covering each other |

Toolbar buttons:
- **Audit**: red outline and label on each finding, plus a list in the Output.
- **Next phone**: cycles the Device Simulator through Galaxy A06, iPhone 16, iPad, then off.
- **Clear**: removes the outlines.

Works in Edit mode (StarterGui) and in Play mode (your live PlayerGui, including UI created by scripts).

It only reads: your UI is never changed. Empty layout frames and Roblox's own touch controls are skipped, so only real problems show up.

## Price and status
**$4.99** one-time, planned for the Roblox Creator Store. **Not on sale yet.**
Want it? Give a 👍 on [issue #1](../../issues/1). That is how we count interest. No payment or email is collected here.
