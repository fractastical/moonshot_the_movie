# MOONSHOT — 3:00 animatic

An animatic for a three-minute film assembled out of a real exhibition. The
footage, the score and the colour grade are all driven by crowd telemetry
recorded off a live installation.

**Download the cut from [Releases](../../releases/latest).** Two files, same edit:

| file | | |
|---|---|---|
| `moonshot_animatic_MASTER_1080p.mp4` | 1920×1080, 30fps | the master |
| `moonshot_animatic_REVIEW_720p.mp4` | 1280×720, 30fps | review and comments |
| `moonshot_prompts.pdf` / `.txt` | one page per generated shot | the prompt sheet |
| `moonshot_vo-script.pdf` / `.txt` | 36 lines, two speakers, timecoded | the voice-over recording script |

Runtime is exactly **180.000s / 5400 frames**, 51 segments.

---

## What this is

An animatic, not a finished film. **Every frame of it is picture.** There are no
placeholders and no holes left anywhere in the cut — the last two, the moonshot
itself and the plug going back in, were generated for this version.

Segments are colour-coded in the chrome:

| | | |
|---|---|---|
| **GREEN** | REAL | real footage, in the cut now |
| **AMBER** | RENDER | instrument panels drawn from our own telemetry |
| **RED** | GENERATE | came out of a generator rather than a camera |

The tags stay on screen now that nothing is missing, because an editor still
needs to know at a glance which frames came off a camera, which came out of the
rig and which came out of a generator.

| | shots | | |
|---|---|---|---|
| **REAL** | 34 | 107.2s | 60% |
| **RENDER** | 7 | 30.3s | 17% |
| **GENERATE** | 10 | 42.5s | 24% |

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
transmitter, and at **0:49** you see the beams leave the roof and converge on the
moon, under the line they answer: *"Together they make a signal. And we know where
to point it."* Until this version that shot did not exist and the aim was a claim
rather than a fact.

**Which makes the number evidence rather than a score.** It reads signal strength,
and it is the only proof that a free supply exists. The film hands you the
scoreboard at **0:54** — *"The number has to stay above eighty. That is the whole
plan."* — so from there you can score the film off the corner of the frame. That
is also why the authority cannot simply disagree with it, and why the central line
at **1:49** is *"You are not having fun. Your own machine says so."*

**The attack fails upward.** At **1:58** a hand in a black glove and a greatcoat
cuff pulls the dome's single plug out of the wall, and the structure dies in the
same frame — and it does not work, because he has cut the electricity to an
apparatus that does not run on electricity. So the record goes instead. At
**2:24** a clawed hand covered in dark fur pushes the same plug back into the
same socket and the lights come up behind him while he is still saying *"There
was nothing left. I checked."* Then, too late, he understands where the battle
actually is: *"We will need to do something about the moon."* Not destroy it.
Dim it. A closed file that stays visible keeps getting reopened.

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
  ships with the cut. One page per generated shot, styled like the film, carrying
  the exact string that made it. It reads as provenance now rather than as a
  shopping list: this is what to iterate on to re-roll one shot without disturbing
  the others. There's a [plain text version](docs/moonshot_prompts.txt) too, which
  is the one you'll actually copy out of.
- [`docs/vo-script.md`](docs/vo-script.md) — the voice-over: 36 lines for two
  speakers recorded separately, timecoded, with direction notes and a recording
  spec. It opens with the whole plot in one plain paragraph. The
  [PDF](docs/moonshot_vo-script.pdf) is the booth version.
- [`docs/generation-prompts.md`](docs/generation-prompts.md) — the same shots with
  more around them: reference plates, continuity rules, alternates, priority
  order. Start here if you're re-rolling one.
- [`docs/outline.md`](docs/outline.md) — the long-form outline: act structure,
  which second of the source footage is used where, how the score is built out
  of telemetry, and how the grade is driven.
- [`refs/`](refs) — reference plates. Text alone will not hold a location or a
  face across ten separately generated shots, so the venue, the ritual, the
  antagonist's coat, the protagonist and the film's grade are each pinned to an
  image pulled from footage we own.

## What changed in this cut

The last version ended with a room recovering, and a room recovering reads as
"the party got going again" — a pleasant ending, not the one this film claims.
Everything below is aimed at the same thing: something did this, on purpose, and
it is still doing it.

- **The two missing shots exist.** `THE MOONSHOT — THE BEAMS REACH THE MOON` at
  0:49 and `THEY PLUG IT BACK IN` at 2:24 were the last red cards in the film and
  they were the two the title and the ending depended on. The cut now has no
  holes at all.
- **The ending said the opposite of the story.** The scientist's line over the
  moon was *"It did not die. It just does not need us now"*, which tells an
  audience they have been abandoned by the thing they built. It is now *"It did
  not die. It is holding us up now."* Act IV's tail was re-timed around it and the
  silence at 2:37 is the collective thing whole again rather than an empty room.
- **The machine says what is keeping the lights on.** On the final card:
  `THE GRID`, struck through, `OFF SINCE 1:58`; then `THE MOON`, typed on rather
  than cut in, `FEEDING THE ROOM`. Without it the moon is scenery — the recovery
  is only an act if something is named as its source.
- **The score turns to the relative major.** Four acts rest on the Am every fourth
  bar; Act V plays the same four chords as vi-IV-V-I, anchored so the last bar
  under the title card is the tonic. Same voicings, same hook — the film resolving,
  not a key change nobody set up.
- **The antagonist is one antagonist.** The field staff wore sage-green
  softshells and read as a different film's problem. They now wear the author's
  heavy dark greatcoat, wide collar and black leather gloves, so the man in the
  corridor at 1:35, the people in the doorway at 1:38 and the hand on the plug at
  1:58 are visibly one side.
- **The collective thing survives on screen.** It ran through the build, the peak
  and the erasure and then vanished from the recovery, so the picture showed it
  die and never showed it come back. It returns at 2:37, framed long so it
  resolves as one contained body, cut between the moon with an eye and the moon
  dance — the thing they built and the thing they aimed at, shot like the same
  object.
- **The protagonist has a face in the film.** She carries 22 of the 36 spoken
  lines and had been on screen twice. Her introduction at 0:12 also used to open
  on a third of a second of the wrong shot, which is fixed, and she now appears
  in the generated Act IV arrival as the person the citation is handed to.
- **The dorje is gone.** 2.5 seconds of a ritual implement rotating on black — no
  room, no people, no telemetry — cutting Act II's only build in half, and the
  strongest single push toward reading the circle as a séance. Its seconds paid
  for the moonshot exterior.
