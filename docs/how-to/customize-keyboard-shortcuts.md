---
title: Customize keyboard shortcuts
layout: default
parent: How-To Recipes
nav_order: 7
---

# Customize keyboard shortcuts

Remap any command to the key combination you prefer — or add a second binding for the same command.

**Time:** ~5 minutes  
**Skill level:** Intermediate

---

## Opening the Shortcuts editor

Go to **Settings** (<kbd>Ctrl</kbd> + <kbd>,</kbd>) → **Shortcuts**.

The editor shows every available command with its current key binding.

---

## Remapping a command

1. Find the command you want to change (use the search box at the top to filter by name)
2. Click the key binding shown next to it
3. Press your new key combination
4. The binding updates immediately — no restart required

**Example:** Remap **Toggle preview panel** from <kbd>Ctrl</kbd> + <kbd>P</kbd> to <kbd>F4</kbd>:

1. Search for `preview`
2. Click the binding next to **Toggle preview panel**
3. Press <kbd>F4</kbd>

---

## Adding a second binding

Each command can have one primary binding. To use an alternate key (e.g. for a different keyboard layout), remap the command to the key you want to use. The previous binding is released and becomes available for other commands.

---

## Conflict detection

If you try to assign a key that is already in use, SPAN Finder shows a conflict warning with the name of the command currently using that key. You can:

- **Reassign anyway** — the other command loses its binding
- **Cancel** — keep the original binding

---

## Keys that cannot be rebound

Some keys are reserved by Windows or by SPAN Finder's core navigation and cannot be used as shortcuts:

**System-reserved (Windows handles these):**

| Key | System action |
|-----|--------------|
| <kbd>Win</kbd> + anything | Windows system shortcuts |
| <kbd>Alt</kbd> + <kbd>F4</kbd> | Close window |
| <kbd>Alt</kbd> + <kbd>Tab</kbd> | App switcher |
| <kbd>PrintScreen</kbd> | Screenshot |

**Structural keys (cannot be bare — must be combined):**

| Key | Reason |
|-----|--------|
| <kbd>Tab</kbd> | Focus navigation within UI |
| <kbd>Enter</kbd> | Confirm / open |
| <kbd>Esc</kbd> | Cancel |
| <kbd>Space</kbd> | Quick Look / selection |
| <kbd>Backspace</kbd> | Parent folder navigation |
| <kbd>Delete</kbd> | Delete file |
| Arrow keys | Item navigation |

These can be used as **part** of a combination (e.g. <kbd>Ctrl</kbd> + <kbd>Tab</kbd> is fine).

---

## Korean keyboard notes

Korean keyboards map certain keys to different virtual key codes. SPAN Finder handles this automatically for most shortcuts, but a few edge cases require manual remapping:

- **Ctrl + \`** (backtick for terminal): On Korean keyboards, the backtick key uses a different scan code. If this shortcut doesn't work, try **Ctrl + '** (single quote) — SPAN Finder adds this as an alternate binding automatically.
- **Ctrl + ,** (Settings): Works correctly on Korean keyboards via VK=188.

If a shortcut doesn't respond as expected on your keyboard layout, remap it in **Settings → Shortcuts** to a key that produces the correct key event on your hardware.

---

## Resetting to defaults

To reset a single command: click its binding and press <kbd>Esc</kbd> to cancel, then right-click the command → **Reset to default**.

To reset all shortcuts to defaults: scroll to the bottom of the Shortcuts settings page → **Reset all to defaults**.

---

## Tips

- **Document shortcut** — There is a built-in shortcut reference: press <kbd>Shift</kbd> + <kbd>?</kbd> inside the app to overlay a cheat sheet of all current bindings.
- **F-key shortcuts** — <kbd>F1</kbd>–<kbd>F12</kbd> are good candidates for frequently used commands since they require no modifier keys.
- **Laptop keyboards** — On laptops where <kbd>Fn</kbd> + <kbd>F-key</kbd> is required, consider using <kbd>Ctrl</kbd> + letter combinations instead.

---

## Complete shortcut reference

See the [Keyboard Shortcuts](../../shortcuts/) page for the full list of every command and its default binding.

---

## See also

- [Keyboard Shortcuts](../../shortcuts/) — Full default shortcut reference
- [Basic Navigation](../../getting-started/basic-navigation/) — Core navigation keys explained
