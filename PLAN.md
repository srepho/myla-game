# Myla's Magic Kingdom — Development Plan

A browser game for Myla (almost 5) and her little sister Leah (2).

## Design principles (age 4–5, pre-reader)

1. **No reading required** — navigation is by big pictures; instructions are *spoken*
   (browser speech synthesis) and reinforced with sound effects.
2. **No fail states, no timers, no scores** — a wrong answer gets a friendly wobble and
   an encouraging voice line, never a buzzer. Everything a child does produces reward.
3. **Huge touch targets** — every interactive element is a minimum of ~56px, most far
   larger, with extra invisible padding around moving targets.
4. **Immediate cause-and-effect** — every tap makes something sparkle, bounce, or sing.
   This is the core loop that holds a 4–5 year old.
5. **Sibling-safe** — a dedicated toddler mode (Leah, 2) where *any* tap anywhere is a
   correct answer.
6. **Parent-friendly** — one HTML file, zero installs, zero network requirements at play
   time, no ads/links/purchases, and a mute button.

## v1 — SHIPPED (this session)

Single self-contained `index.html` (emoji + inline SVG art, WebAudio synth sound,
speech-synthesis voice prompts — no external assets needed to play).

| Game | Skill it exercises | Loop |
|---|---|---|
| ⭐ Star Pop | hand-eye coordination | pop floaters → musical notes → fill rainbow meter → unicorn flyby celebration |
| 🦄 Dress-Up | creativity, choice-making | mane colours, 3 hats, wings, 3 backgrounds; tap unicorn → happy bounce |
| 🏰 Castle Stickers | creativity, spatial play | pick sticker → stamp on castle scene → broom clears |
| 🔤 Letter Bubbles | letter recognition (pre-reading) | spoken prompt → find letter among 4 → spells MYLA, LEAH, STAR, PONY |
| 👶 Leah's Sparkles | toddler cause-and-effect | any tap = fireworks + chime; every 4th tap a friendly animal bounces in |

## v2 ideas (next sessions)

- **Counting game**: "Can you tap 3 butterflies?" — spoken numbers, 1–10.
- **Colour-match game**: "Find something pink!"
- **Memory pairs**: 6 face-down cards with unicorn/princess emoji.
- **Save Myla's creations**: persist dress-up + sticker scenes to localStorage,
  add a "gallery" screen.
- **Record-a-cheer**: let a parent record their own voice for celebrations
  (MediaRecorder), stored locally.
- **Drawing/colouring pad**: finger painting canvas with big crayon buttons.
- **More letters**: lowercase mode; letter → word-with-picture ("M is for Moon 🌙").
- **Install as app**: add PWA manifest + service worker so it can be added to an
  iPad home screen and launched fullscreen offline.

## Technical notes

- Vanilla HTML/CSS/JS in one file; no build step, no dependencies.
- Art: emoji + hand-drawn inline SVG (unicorn, castle). Sound: WebAudio oscillators
  (pentatonic scale so random notes always sound pleasant). Voice: `speechSynthesis`.
- Google Font "Baloo 2" loads when online and degrades gracefully offline.
- Works with mouse or touch (pointer events); double-tap zoom disabled.
- Sound preference persisted in localStorage (`mk-sound`).
