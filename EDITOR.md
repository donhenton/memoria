# Pin Editor — Usage

`editor.html` is a standalone tool for repositioning the pins on your face diagram. Open it in any browser. It does not modify `index.html` directly — you copy the updated deck out and paste it back in yourself. This keeps the workflow auditable.

## Quick start

1. Open `editor.html` in a browser (double-click, or open via GitHub Pages if you've hosted it)
2. Click **Use Built-in Deck** to start from the original 35 cards
3. Drag any pin on the diagram to reposition it. The selected pin shows green; others stay red
4. When you're happy with the changes, click **Copy to Clipboard** and paste the updated array into `index.html`, replacing the existing `DECK_SEED`

## The three ways to move a pin

- **Drag** — point at any pin, click and drag. Works on desktop and touch
- **Click on the diagram** — click anywhere on the face (not on a pin) and the *selected* pin jumps there. Useful for big repositioning
- **Arrow keys** — once a pin is selected, arrow keys nudge by 1%. Hold Shift for 5%. Useful for fine-tuning after a rough drag

The selected pin is whichever one you most recently clicked, dragged, or selected from the card list on the right.

## Loading a custom deck

If you've already edited `index.html` and want the editor to start from your current state (not the built-in original):

1. Open `index.html` in a text editor
2. Find `const DECK_SEED = [...]` — copy everything between (and including) the square brackets
3. Paste into the **Load Deck** textarea in the editor
4. Click **Load Pasted JSON**

The editor will use that as its starting point and remember it as the "original" for diff purposes.

## Saving changes back to index.html

The editor never writes to your files. To apply changes:

1. Click **Copy to Clipboard** (copies the full `DECK_SEED` array, pretty-printed one card per line)
2. Open `index.html` in a text editor
3. Find the line starting with `const DECK_SEED =`
4. Select from the `[` to the matching `]` (the entire array) and replace with what you copied
5. Save `index.html`. Reload your study app

If you only want to see what changed (not the full array), expand **Show only changed cards** in the Export panel. It shows the before-and-after coordinates for any pins you've moved, which is useful as a sanity check before pasting.

## Card list panel

The right-hand list shows every card sorted by id. The currently selected card is highlighted dark. Cards you've moved show a small bullet (•) next to the name and the changed-count pill turns orange.

Click any card to select it and bring its pin into focus on the diagram.

## A few things that aren't obvious

**The editor doesn't preserve the `where` description.** It only edits `x` and `y`. If you want to change a feature's location text, edit `index.html` directly — the editor leaves those fields untouched as it round-trips the data.

**The editor and `index.html` don't share state.** They both have their own copy of the deck. Edits in the editor don't appear in the study app until you copy-paste. Edits in `index.html` don't appear in the editor until you paste them in. This is deliberate — the editor is a one-way export tool.

**LocalStorage is not involved.** Your pin edits live in the editor's page memory only. Refresh the page and they're gone unless you've copied the export. Copy early, copy often.

**The exported coordinates are floating-point now.** The original had integer percentages like `47`. After editing, you'll see values like `47.3`. That's fine — the study app handles either. If you want to round them yourself for cleanliness, do it manually after pasting.

## Workflow recommendation

Don't try to perfect every pin in one session. Open the study app, run a session, and notice which pins feel wrong (too far from the actual feature). Note those, open the editor, fix only those few, paste back. Reload the study app. Repeat over a few days. You'll converge on accurate coordinates faster than trying to do all 35 in one sitting and second-guessing yourself on pins that are already fine.

## One honest limitation

The diagram is a 3D rendered head, not a real face, and not even a particularly anatomically accurate one. Some of the original "pinned" features on the source image (the red numbers visible in the diagram) sit at positions that aren't where the textbook landmark would actually be on a real face — the artist who annotated it took some liberties. If you find a pin position that "feels wrong" but matches the original number on the diagram, the original may itself be off. Your call which to trust.
