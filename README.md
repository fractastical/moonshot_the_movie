# MOONSHOT — 3:00 animatic

An animatic for a three-minute film assembled out of a real exhibition. The
footage, the score and the colour grade are all driven by crowd telemetry
recorded off a live installation.

**Download the cut from [Releases](../../releases/latest).** Two files, same edit,
and nothing burned into the picture in either:

| file | | |
|---|---|---|
| `moonshot_1080p.mp4` | 1920×1080, 30fps | the master |
| `moonshot_720p.mp4` | 1280×720, 30fps | review, comments, anything with a size limit |
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

The release above is clean — no overlay, no tags, no timecode. There is a working
version of the same cut with an overlay across every frame: act, timecode, source
label, and a live number labelled VIBE. That one is for cutting, not for watching,
and everything below about the number describes it.

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
  spec, plus a third voice that is a recording rather than a part. It opens with
  the whole plot in one plain paragraph. The
  [PDF](docs/moonshot_vo-script.pdf) is the booth version, and carries the 36
  lines that are actually going to be performed.
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

Two things arrived from outside the edit and both are the same kind of material:
not written, not generated, and not re-creatable. They went in on the same rule —
replace like with like, and do not make the film longer. Every act still runs to
the frame it ran to before, and the cut is still 51 segments and 180.000s.

- **The real structure is in the film.** Two seconds of the tabernacle
  half-built, on the site's own camera, now open Act II at **0:39**. Every
  generated shot in that act asks for *"raw pine framing and silver mylar
  sheeting"* — and that phrase was not invented for the prompts, it describes a
  real structure a real camera was pointed at a month before any of them were
  run. So the act shows the thing itself before it cuts inside the generator's
  version of it, which is the right way round. It cost half a second off the
  interior it introduces, and the whole of a stock microscopy shot at 1:02.
- **The cameras go blind at the bottom of Act IV.** At **2:12.9**, two seconds
  after the wall of 1969 goes out, the site's outdoor camera reads NO SIGNAL with
  its list of prohibitions still scrolling across the top of it. It replaces a
  stock glitch loop, and that is the whole trade: a picture of a feed corrupting,
  swapped for a feed that stopped. The film's own erasure is at full strength on
  that frame, so the shot is torn by the same process that put the card up.
- **A third voice, twice, for five seconds.** Not a part. It is a real recording
  of one of the people who built this, taken off a video call, saying what it is
  for in his own words — *"It turns us into spectators"* at **2:06**, and
  *"Really enliven the moon as a symbol of the future"* at **2:27.6**. He is
  never synthesised, and he cannot hear either of the other two speakers, which
  is what makes him admissible in a script that has always refused to let one
  voice rebut another. He is the same class of object as the number in the
  corner: something that came off the world and cannot be edited to suit the
  argument.
- **Two lines is what the film had room for, and that is the finding.** He said a
  great deal more and most of it is good. The widest hole left in a cut that is
  56% speech is 4.7 seconds, and his best sentence — *"The moon is one of many
  examples of a future that's being lost"* — runs 7.4. The only gaps big enough
  are the two deliberate silences, and spending either costs more than it buys.

Earlier releases carry their own notes: the moonshot exterior and the plug going
back in ([v1.2](../../releases/tag/v1.2-animatic)), the instrument panels and the
fifth-grade rewrite ([v1.1](../../releases/tag/v1.1-animatic)).
