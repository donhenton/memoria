# Usage Guide

A practical guide to using the study tool day-to-day. For setup and editing, see `README.md`. For repositioning pins, see `EDITOR.md`.

## What to expect from daily 10-minute sessions

Roughly what actually happens with daily 10-minute sessions:

**Day 1.** All 35 cards are "due" (new cards default to due immediately). You probably won't get through all 35 in one sitting — and you shouldn't try. Do 10–15. The rest stay due.

**Day 2.** Yesterday's 10–15 cards rated "Good" come back (1-day interval for first review). Plus the 20–25 you didn't touch yet. Maybe 30+ due. Do another 10–15.

**Day 3–4.** You've now seen all 35 at least once. Cards rated "Good" twice are scheduled 6 days out. Cards rated "Forgot" reset and come back tomorrow. Daily due count starts dropping into the single digits.

**Week 2.** Most cards are sitting on 6-day or longer intervals. Many days you'll open the app and see 2–5 cards due, sometimes zero. The mature cards aren't gone — they're just not due yet. The deck status panel still shows all 35 under New / Learning / Mature.

The thing that surprises people: by week 2 you'll feel like you're "barely studying" because daily sessions are tiny. That's the point. The algorithm stretches intervals as your retention proves itself. A card you rate Good repeatedly will go 1d → 6d → ~15d → ~37d. After a month, well-known cards won't show up for weeks at a time.

## Running a session

Open the page. Tap **Begin Session**. The button is disabled when nothing is due — that's fine, come back tomorrow.

Each card shows one of two things:

- **A pin on the diagram** — name the feature out loud or in your head before tapping Reveal Answer
- **A feature name** — picture where it sits on the diagram before tapping Reveal Answer

The session alternates directions automatically. Don't skip the "think first" step — passively reading the answer doesn't build retention, only retrieval does.

After Reveal, four buttons appear:

- **Forgot** — you blanked, or peeked before trying. Card resets, comes back within a day
- **Hard** — you got it but it took real effort, or you were unsure
- **Good** — you recalled it with normal effort. The default for most cards once you know them
- **Easy** — instant, zero hesitation. Use sparingly — overusing this stretches intervals so far that cards get hard again before they come back

The numbers under each button (`<1d`, `6d`, `15d`, etc.) preview when that card will next appear if you pick that rating.

## Rating honestly

This is the part that determines whether the system works.

The algorithm uses your ratings to model your individual forgetting curve. If you rate dishonestly, you're not gaming the system in your favor — you're feeding it bad data, and it gives you back a worse schedule. Two common failure modes:

**Inflating ratings to feel productive.** You half-remembered, but it felt close enough, so you hit Good. Result: the card pushes out to 6 days, you've genuinely forgotten by then, and now it cycles as a Forgot. You added a week of delay before relearning it.

**Hitting Easy on cards you saw five seconds ago.** Recognition decays, and "this feels familiar" is a notoriously bad proxy for "I will recall this in two weeks." If you had to look at it for more than a beat, it's not Easy.

The honest rule of thumb: imagine someone asked you this card cold tomorrow. If you'd nail it instantly, that's Easy. If you'd get it after a moment, that's Good. If you'd struggle but get there, that's Hard. If you'd blank, that's Forgot — even if right now, in this moment, you're sure you know it.

## Don't binge

When you see a pile of due cards, the instinct is to clear them. Resist this past about 15 cards in a sitting.

Tired brains rate inconsistently. After ten minutes of focused recall, your judgment of "good vs. hard" gets noisy, you start reading answers without genuinely retrieving first, and the data you're feeding the algorithm degrades. Better to stop at 15 with sharp ratings and let the rest wait until tomorrow than to grind through 30 with sloppy ones.

If you've taken a multi-day break and find 30+ cards due, do 10–15 and close the app. The pile will shrink over the next few days as you work through it.

## Don't review when nothing's due

There's no "study extra" button, intentionally. Reviewing a card before it's due collapses the spacing — the very thing that makes the schedule work. If you want to *look* at the deck out of curiosity, use **Manage Deck** on the home screen. It lists every card with its rep count and next-review date but doesn't reschedule anything.

## When to stop a session

You're done when:

- The session naturally ends (you've cleared all due cards)
- You've done 15 cards and your attention is fading
- You catch yourself rating a card without thinking about the answer first
- Your phone has been showing the same card for 30 seconds because you got distracted

Closing the app mid-session is fine. Your progress on cards you've already rated is saved. Cards you haven't reached yet stay due and will appear next time.

## When something feels wrong

**A card keeps coming back as Forgot.** That's the algorithm catching that you don't actually know it. It'll keep cycling on short intervals until something sticks. Try saying the answer out loud rather than just thinking it — verbalizing helps consolidation.

**A card feels too easy and won't go away.** You're probably rating it Good when it should be Easy, or it just hasn't matured yet. Three or four Good ratings in a row will push it out to multiple weeks.

**You forgot a "mature" card you thought you knew.** This is normal and expected — the algorithm pushes intervals out until you start forgetting again, then pulls them back in. Rate it honestly (Forgot or Hard) and let it re-mature.

**The pin location feels wrong.** The pin coordinates were eyeballed, not measured. Use `editor.html` to fix any that bug you. See `EDITOR.md`.

## What this won't do

It won't teach you to draw. It teaches you to recognize and name features. Naming what you see is a real benefit when sketching — vocabulary makes thought possible — but the hand-eye coordination of actually drawing is a separate skill trained by drawing.

It won't transfer perfectly to real faces. The diagram is a stylized 3D head. Real faces have proportions, lighting, and tissue distribution that this reference doesn't capture. After the deck is solid, practice naming features on real photographs to bridge the gap.

It won't sync across devices. Pick one browser on one device and stay there. See the warning in `README.md`.

## A reasonable definition of "done"

When most cards are sitting on month-plus intervals and you can answer a randomly-selected card in under two seconds without looking, the deck has done its job. That's typically 4–8 weeks in for someone studying daily. At that point, the value comes from:

- Brief weekly check-ins to keep mature cards from decaying
- Adding new cards as your sense of what matters in a portrait evolves
- Using the vocabulary on real faces and reference images, where the deck can't take you

The deck is scaffolding for an ongoing observation practice, not a course you complete.
