# MOONSHOT — 3:00 animatic

An animatic for a three-minute film assembled out of a real exhibition. The
footage, the score and the colour grade are all driven by crowd telemetry
recorded off a live installation.

**Download the cut from [Releases](../../releases/latest).** Two files, same edit:

| file | | |
|---|---|---|
| `moonshot_animatic_MASTER_1080p.mp4` | 1920×1080, 30fps | the master |
| `moonshot_animatic_REVIEW_720p.mp4` | 1280×720, 30fps | review and comments |
| `moonshot_prompts.pdf` / `.txt` | one page per missing shot | the prompt sheet |
| `moonshot_vo-script.pdf` / `.txt` | 36 lines, two speakers, timecoded | the voice-over recording script |

Runtime is exactly **180.000s / 5400 frames**, 49 segments.

---

## What this is

An animatic, not a finished film. **It now plays as continuous picture** — there
are no text placeholders left in the cut. Roughly four fifths is real footage cut
for real, and the rest is either rendered from our own system or a slate carrying
the prompt to generate it.

Segments are colour-coded in the chrome:

| | | |
|---|---|---|
| **GREEN** | REAL | real footage, in the cut now |
| **AMBER** | RENDER | **built** — instrument panels drawn from our own telemetry |
| **RED** | GENERATE | needs an external generator. This is the shopping list |

A red card is a hole; green and amber stretches are close to final. There are
eight red cards totalling 37 seconds — barely a fifth of the film.

**The seven amber cards used to be text and are now picture:** working instrument
panels in the exhibition's own green-phosphor UI, animated, with every number on
them read out of the same telemetry that drives the score and the grade. They run
30.3 seconds, 17% of the film, and they are performances rather than titles —
treat them as shots. Two of them carry plot the dialogue never states.

## The chrome

An overlay runs across every frame: act, timecode, source label, and a live
number labelled VIBE.

That number is real crowd telemetry recorded at the exhibition, and it is not
decoration. It drives the score's arrangement and the colour grade frame by
frame — when the number falls the music thins and the picture drains, and when
it collapses the picture corrupts. Please keep it in frame in any recut. It is
the spine of the whole piece and the reason the film has an argument.

It is also, by the end, a character. See below.

## The story

Written to be followed by a ten-year-old on one viewing. If any of the below
needs explaining to a viewer, that is a bug in the film and we want to hear it.

**The moon has been filed as finished.** We went, we planted a flag, the item was
closed — and a finished world does not need power, so everyone's supply is capped
at what a finished world costs. That is the authority's case and it is not a
safety measure, it is a bill. It is stated at **0:10** by an automated notice
reading *YOU HAVE USED TOO MUCH POWER / NEW LIMIT: WHAT A FINISHED WORLD NEEDS*,
and again out loud at **0:14**: *"We already did the big thing. So nobody needs
much power."*

**So the scientists lose their power**, and that is the film's inciting incident
at **0:35**: a rack of computers powering down, nobody in frame. They cannot run a
laboratory on nothing, so they build the apparatus out of people instead — light,
sound, and a roomful of attention pointed the same way, inside a tabernacle of raw
pine and silver mylar they put up themselves. The circle is not a séance. It's a
transmitter, and the beams leave the building.

**Which makes the number evidence rather than a score.** It reads signal strength,
and it is the only proof that a free supply exists. The film hands you the
scoreboard at **0:54** — *"The number has to stay above eighty. That is the whole
plan."* — so from there you can score the film off the corner of the frame. That
is also why the authority cannot simply disagree with it, and why the central line
at **1:49** is *"You are not having fun. Your own machine says so."*

**The attack fails upward.** At **1:58** a hand in a sage-green sleeve pulls the
main breaker — and it does not work, because he has cut the electricity to an
apparatus that does not run on electricity. So the record goes instead. Then,
too late, he understands where the battle actually is: *"We will need to do
something about the moon."* Not destroy it. Dim it. A closed file that stays
visible keeps getting reopened.

Five acts: **The Flatline** (0:00), **The Ritual** (0:35), **The Signal Spreads**
(1:05), **The Softening** (1:35), **The Answer** (2:24).

## The third party

Worth knowing before you cut anything, because it is easy to mistake for UI.

There are three parties in this film, not two. The authority. The thing the crowd
is assembling, which is never named because you count it instead. And the machine
— the readout in the corner of every frame, which nobody thinks to ask anything.

It has an arc and it is entirely silent:

| | | |
|---|---|---|
| acts I–III | it reads | neutral instrumentation |
| **1:49** | **it refuses** | he calls it as his witness and it refuses in the same second. The card is called THE MACHINE DISAGREES, and it stamps READING REFUSED — THE MACHINE WILL NOT SIGN THIS over a room it can see is full |
| **2:46** | **it picks a side** | the trace doubles and the second line *leads* the first; the job field flips WATCHING → JOINING IN; the number goes off its own scale and reads TOO MUCH — the same two words the state accused them with at 0:10 |

Nothing in this film rebuts the narrator in words. A signature is not an argument,
and both of those beats are stronger for being mute. Please don't score them like
reveals.

## Audio

The score is synthesised from the same telemetry, so it is bound to picture
timing. If a section changes length the music has to be regenerated rather than
trimmed — please flag a timing change rather than cutting into it.

## The docs

- [`docs/moonshot_prompts.pdf`](docs/moonshot_prompts.pdf) — the prompt sheet that
  ships with the cut. One page per missing shot, styled like the film, carrying
  the exact string to paste into a generator. There's a
  [plain text version](docs/moonshot_prompts.txt) too, which is the one you'll
  actually copy out of.
- [`docs/vo-script.md`](docs/vo-script.md) — the voice-over: 36 lines for two
  speakers recorded separately, timecoded, with direction notes and a recording
  spec. It opens with the whole plot in one plain paragraph. The
  [PDF](docs/moonshot_vo-script.pdf) is the booth version.
- [`docs/generation-prompts.md`](docs/generation-prompts.md) — the same eight
  shots with more around them: reference plates, continuity rules, alternates,
  priority order. Start here if you're filling holes.
- [`docs/outline.md`](docs/outline.md) — the long-form outline: act structure,
  which second of the source footage is used where, how the score is built out
  of telemetry, and how the grade is driven.
- [`refs/`](refs) — reference plates. Text alone will not hold a location or a
  face across eight separately generated shots, so the venue, the ritual and the
  film's grade are pinned to images pulled from footage we own.

## What changed in this cut

- **The seven amber cards are built.** They were text describing a shot; they are
  now the shot. 30.3 seconds recovered from placeholder to picture without a
  camera or a generator, because the film already owned the thing they are shots
  *of*. Every number on them is read from the telemetry at that frame, so they
  cannot drift from the chrome, the score or the grade — and they take the colour
  grade like any other picture, so the console is nearly grey when the number is
  flat and full green when it peaks.
- **The plot now reads at a fifth-grade level.** The premise had only ever been
  implied: you could watch all three minutes and never learn why the power was
  cut. It is now said plainly at 0:14, Act I is re-ordered so the antagonist's
  authorship causes the scientist's loss, and the console stopped talking like a
  console — `SUBJECTS IN FRAME` became `PEOPLE RIGHT NOW`, `ROLE: OBSERVER` became
  `MY JOB: WATCHING`. Every spoken line was rewritten and re-timed against
  picture. Nothing about the structure, the acts or the runtime moved.
- **The film's opening accusation is now its verdict.** The 0:10 notice reads
  YOU HAVE USED TOO MUCH POWER, which lets the last card put **TOO MUCH** in red
  as the machine's own reading of the crowd.
- **Retitled MOONSHOT.** The previous title was the antagonist's phrase, which
  meant the last card of the film agreed with him. It survives where it works —
  his line at 2:47, and the operation name on a document at 1:42 — but the title
  now belongs to the other side, and the naming is the last move of the conflict.
- **The ritual has a cause.** `THEIR POWER WAS CUT` at 0:35 is new. Until it
  existed, twenty people sat in a dome because the story needed them to; now
  everything in Act II is a substitution for equipment they can no longer power.
- **The venue is a tabernacle, not a warehouse.** Raw pine framing and silver
  mylar, faceted into an octagonal passage, erected inside a larger dark hall.
  Every generated party prompt was rewritten around it and it now has a reference
  plate cut from the real footage.
- **The moon is in the middle of the film.** It bookended and never fought —
  three appearances in Act I, three in Act V, none in between. `THE MOON ANSWERS`
  now closes Act III, three seconds after *"and no one could tell me what it was
  for."*
- **The transformation is in Act III**, held at half speed over 3.2 seconds, with
  the BLOOD MOON trigger in front and the aftermath macro behind. The only speed
  change in the film.
- **Reference plates**, in `refs/` — all seven now authored, including the field
  officer and the laboratory that were outstanding last cut.
