# Atelier Memoria

A spaced-repetition flashcard app for memorizing facial features and their locations on the face. Built as a single self-contained HTML file — no build step, no dependencies, no install.

## Location URL
https://donhenton.github.io/memoria/

## What it does

35 cards covering face anatomy (forehead, nose, mouth, ear, neck landmarks). Each session alternates between two directions:

- **Pin → name**: a pin appears on a face diagram, you name the feature
- **Name → pin**: you're given a feature name, then check where it sits on the diagram

Reviews are scheduled with the SM-2 algorithm — the same one Anki used for years. Rate each card Forgot / Hard / Good / Easy and the next review pushes out from a day to weeks based on how well you knew it.

## Usage

Visit the hosted page (or open `index.html` locally). Tap **Begin Session**. Rate cards honestly — the algorithm only works if your ratings reflect actual recall difficulty, not how the card "felt."

On mobile, use your browser's "Add to Home Screen" option to make it behave like an installed app.

## ⚠️ Progress is per-browser, per-device

This is the most important thing to know.

Progress is stored in `localStorage`, which is **scoped to a single browser on a single device**. That means:

- Open it in Safari on your phone today, Chrome on your laptop tomorrow → the laptop sees a fresh deck
- Clear browser data, switch browsers, or use incognito → progress is gone
- iOS and Android, work and personal devices → all separate

There's no sync, no account, no cloud. If cross-device study matters to you, the right tool is Anki, which has real sync and the same underlying algorithm.

**Recommendation:** pick one browser on one device and commit to it. Treat that as your "study device."

## Recommended schedule

**Once a day, every day.** Ten minutes or less, usually much less.

The algorithm schedules each card individually — some come back tomorrow, some in a week, some in a month. Your job isn't to study on a fixed cadence; it's to show up daily and clear whatever is due *that* day. Most days will be a handful of cards. After a few weeks, many days will be zero cards because nothing has come due yet.

A few notes on why daily:

- **Daily is the floor, not a target.** Twice a day is fine if you want, but won't speed things up — cards that aren't due yet won't appear. You can't out-grind the schedule.
- **Once a week is too sparse.** You'll consistently miss the optimal review window for cards in the early "learning" phase (1-day, 3-day, 6-day intervals). Reviews that arrive after the memory has decayed don't strengthen it the same way — you end up re-learning instead of reinforcing.
- **Skipping days is fine, occasionally.** Missing a day or two doesn't break anything; the cards just pile up briefly. Missing weeks at a time will make the next session miserable and erode retention.
- **Don't binge after a gap.** If you come back to 30 due cards, do 10–15 and let the rest wait. Plowing through everything at once turns the session into a slog and your ratings get unreliable when you're tired.

There is no streak police. The streak counter is motivational, not algorithmic — the algorithm doesn't care whether you studied yesterday, only when each card is next due.

## Editing the deck

Open `index.html` in any editor and search for `const DECK_SEED =`. Each card looks like:

```js
{"id": 17, "name": "Columella", "x": 43, "y": 57, "where": "The strip of tissue between the two nostrils."}
```

- `x` and `y` are percentages (0–100) of the diagram image, top-left origin
- `name` is what shows as the answer
- `where` is the location description

Edit, save, reload. To re-place a pin by clicking on the diagram, paste this into your browser DevTools console:

```js
document.addEventListener('click', (e) => {
  const img = document.querySelector('.diagram-wrap');
  if (!img || !img.contains(e.target)) return;
  const r = img.getBoundingClientRect();
  const x = ((e.clientX - r.left) / r.width * 100).toFixed(1);
  const y = ((e.clientY - r.top) / r.height * 100).toFixed(1);
  console.log(`x: ${x}, y: ${y}`);
}, true);
```

Click anywhere on the diagram and the coordinates print to the console.

## What this is not

It is not a substitute for drawing practice. Memorizing feature names trains recognition and vocabulary; it does not train your hand to place them on a page or your eye to notice them on a real face. The deck is most useful as a working-memory aid — knowing the names so you can think about features while drawing without breaking flow to consult a reference.

## Stack

Plain HTML, CSS, and JavaScript. No frameworks. No build. The face diagram is embedded as a base64 data URL so the file is fully portable.
