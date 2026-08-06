# TURN DOWN THE MOON — 3:00 animatic

An animatic for a three-minute film assembled out of a real exhibition. The
footage, the score and the colour grade are all driven by crowd telemetry
recorded off a live installation.

**Download the cut from [Releases](../../releases/latest).** Two files, same edit:

| file | | |
|---|---|---|
| `turn-down-the-moon_animatic_MASTER_1080p.mp4` | 1920×1080, 30fps, 274 MB | the master |
| `turn-down-the-moon_animatic_REVIEW_720p.mp4` | 1280×720, 30fps, 33 MB | review and comments |
| `turn-down-the-moon_prompts.pdf` / `.txt` | 8 pages | the prompt sheet, one page per missing shot |
| `turn-down-the-moon_vo-script.pdf` / `.txt` | 7 pages | the voice-over recording script |

Runtime is exactly **180.000s / 5400 frames**, 44 segments.

---

## What this is

An animatic, not a finished film. Roughly four fifths is real footage cut for
real. The rest is slate cards standing in for shots that don't exist yet — each
card says what goes there, how long it runs, and, on this cut, carries the prompt
to generate it in a right-hand column.

The cards are colour-coded:

| | | |
|---|---|---|
| **GREEN** | REAL | real footage, in the cut now |
| **AMBER** | RENDER | renderable from our own system. No shoot, no generator |
| **RED** | GENERATE | needs an external generator. This is the shopping list |

A red card is a hole; a green stretch is close to final. There are seven red
cards totalling 33.5 seconds — under a fifth of the film.

## The chrome

An overlay runs across every frame: act, timecode, source label, and a live
number labelled VIBE.

That number is real crowd telemetry recorded at the exhibition, and it is not
decoration. It drives the score's arrangement and the colour grade frame by
frame — when the number falls the music thins and the picture drains, and when
it collapses the picture corrupts. Please keep it in frame in any recut. It is
the spine of the whole piece and the reason the film has an argument.

## The story, in one line

A wellness authority decides a celebration has exceeded its safe allocation of
energy, and turns it off.

The conflict is stated at **0:10** by an automated notice reading *YOU HAVE
EXCEEDED YOUR ENERGY QUOTA*, and paid off at **1:58** when a hand in a
sage-green sleeve pulls the main breaker. Everything in between is the thing
that gets switched off, measured by an instrument that is eventually deleted for
disagreeing.

Five acts: **The Flatline** (0:00), **The Ritual** (0:35), **The Signal Spreads**
(1:05), **The Softening** (1:35), **The Answer** (2:24).

## Audio

The score is synthesised from the same telemetry, so it is bound to picture
timing. If a section changes length the music has to be regenerated rather than
trimmed — please flag a timing change rather than cutting into it.

## The docs

- [`docs/turn-down-the-moon_prompts.pdf`](docs/turn-down-the-moon_prompts.pdf) —
  the prompt sheet that ships with the cut. One page per missing shot, styled
  like the film, carrying the exact string to paste into a generator. There's a
  [plain text version](docs/turn-down-the-moon_prompts.txt) too, which is the one
  you'll actually copy out of.
- [`docs/vo-script.md`](docs/vo-script.md) — the voice-over: 27 lines for a single
  speaker, timecoded to the cut, with direction notes and a recording spec. The
  [PDF](docs/turn-down-the-moon_vo-script.pdf) is the booth version.
- [`docs/generation-prompts.md`](docs/generation-prompts.md) — the same seven
  with more around them: a shared negative prompt for generators that take one,
  continuity rules, alternates, and priority order. Start here if you're
  filling holes.
- [`docs/outline.md`](docs/outline.md) — the long-form outline: act structure,
  which second of the source footage is used where, how the score is built out
  of telemetry, and how the grade is driven.

## What changed in this cut

- **The transformation is back in Act III.** The previous cut ran 0:30–0:34.5 of
  the source and then jumped to 0:42, which is the aftermath — a shredded coat
  and a surviving tie — so the moment the scientists become beasts happened off
  screen. It occupies 39.1–42.0 of the source and the turn itself is only 1.6
  seconds, alternating pale silhouettes with dark beasts so the figures resolve
  out of their own shadows while the coats come apart. It's now held at half
  speed over 3.2 seconds, with the BLOOD MOON trigger card in front of it and
  the aftermath macro behind, so the sequence reads as cause, event, consequence.
  This is the only speed change in the film.
- **The antagonist now surfaces in Act I** instead of at 1:35. The energy notice
  lands at 0:10 and its author is glimpsed at 0:24, unexplained, so his return at
  the party's peak reads as a recognition rather than an introduction. Previously
  the film ran half its length before it had a conflict.
- **New beat at 1:58 — THEY CUT THE POWER**, placed on the steepest fall in the
  telemetry. The number really does drop from 63 to 26 under that card.
- **New beat at 1:21 — THE METER IN THE DOORWAY**, so the apparatus measures the
  party at its peak before it moves against it.
- **The particle-field shots now read their own telemetry.** In the previous cut
  the Act IV field shot played over a VIBE reading of 0.0, because it had been
  rendered from a different part of the timeline than the one it was cut into.
  Both field shots are now rendered from the exact window they occupy — the
  retraction plays on a falling 18, and a second, dimmer field was rendered for
  the flatline at 2:14 where the reading really is 0.0. The windows are now
  derived from the edit itself, so that class of mismatch can't recur.
- **Slate copy quotes the actual telemetry** rather than approximations.
- **Prompts are on the cards**, so the animatic is self-describing without this
  repo open alongside it.
