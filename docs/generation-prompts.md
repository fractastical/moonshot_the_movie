# Generation prompts — MOONSHOT

Seven shots in the 3:00 animatic are red cards: they don't exist yet and can't be
rendered from our own system. This is the shopping list, with a prompt for each
one written to be pasted into a video generator more or less as-is.

Together they are **33.5 seconds of 180** — under a fifth of the film. Everything
else is either real footage already cut, or renderable from VibeMap.

Each shot's prompt also appears on its slate in the animatic, abbreviated. This
file is the long version: negatives, alternates, and the reason the shot is there.

---

## Before you generate anything

**Deliver 16:9, 1920×1080, 30fps.** Generate 2 seconds longer than the slot asks
for at both ends — every one of these gets cut to the frame against a score that
can't be trimmed, so handles are not optional. Veo makes this easy by having no
choice in the matter: at 1080p it only produces 8-second clips, which is longer
than every slot here.

**Audio is discarded.** Veo generates sound whether you want it or not. We never
do — the score is synthesised from telemetry and anything underneath it fights
it. The tooling strips it; if you generate by hand, strip it.

**The house look, which applies to all seven.** These have to cut against 1970s
broadcast stock, a contest video shot on phones, and our own surveillance UI. The
thing that makes that survive is commitment to a degraded, observed image:

- Near-monochrome. Colour only where the prompt names a specific source (an amber
  display, a red LED, blue laser beams). Everything else drained.
- Heavy grain, soft blacks, halation on any bright source.
- Available light only. No film lighting, no key, no rim, no practicals that
  aren't in the room already.
- Camera is either locked off or handheld by someone standing still. Never a
  crane, a gimbal move, a dolly, or a drone.
- Nothing looks new. Concrete, steel, worn paint, cheap fabric.

**The negative prompt, for generators that take one.** Runway and Kling do.
**Veo 3.x does not** — it has no negative field at all, so for Veo this list has
to be phrased into the prompt itself, as properties the image has rather than
things to leave out. `tools/video/generate.py` does that automatically; if
you're prompting Veo by hand, copy the `STYLE` block out of that file.

For everything else, append:

```
cinematic lighting, lens flare, colour grading, teal and orange, shallow cinematic
bokeh, slow motion, drone shot, crane shot, gimbal move, camera push, 4k clean,
hyperdetailed, sharp, glossy, CGI, 3d render, illustration, anime, text overlay,
watermark, subtitles, logos, brand names, uniforms, police, military, weapons,
riot gear, crowds cheering at camera, smiling at camera, model faces
```

**Continuity that binds several shots.** The Softening's field staff wear soft
sage-green softshell jackets, ID lanyards, no insignia of any kind. They are
calm, polite and unhurried in every appearance. They are never angry and never
in a hurry, because the point of them is that they believe they are helping.
Nothing they wear or carry should read as police or military — if a generation
gives you anything that looks like a uniform, throw it out and run it again.

---

## Reference plates — do this before generating anything

Text alone will not hold a character across three shots. The Softening's field
staff appear in **THE METER IN THE DOORWAY**, **WELLNESS INSPECTORS ARRIVE** and
**THEY CUT THE POWER**, and prompted from words each time they will come back as
three different people in three different jackets. Veo 3.1 takes up to three
reference images per generation, and that is the fix.

`tools/video/refs.py` manages them. There are two kinds.

**Extracted — already done.** Pulled out of live-action footage we own, sitting
in `refs/`:

| plate | what it fixes |
|---|---|
| `world_corridor.png` | the institutional corridor, and with it the film's live-action grade — monochrome, fluorescent, grainy, worn. The strongest style plate we have |
| `tabernacle.png` | **the venue.** Raw pine framing and silver mylar, faceted into an octagonal passage, erected inside a larger dark hall. Every party shot happens in here |
| `circle.png` | the ritual — cushions in a ring, candles at the centre, crossed blue beams overhead. All 1.9 seconds of it that exist |
| `world_crt.png` | the CRT wall: screen texture and the light coming off it |
| `author.png` | the Softening's author. He is only ever real footage, so this is for continuity checking rather than generation |

The last two of those come out of the contest video, which is animation — so they
are desaturated and grained on extraction before anything sees them. We want that
building and those materials, not that medium; a clean animated frame handed to a
video generator as a reference drags the whole shot back toward animation, which
is the one thing these must not be.

**Authored — still to do.** Two plates the film needs that no footage contains.
Make each once as a still, look at it properly, then reuse it everywhere:

| plate | needed by | why |
|---|---|---|
| `staff.png` | meter, inspectors, power | the field officer. The one that actually matters — three shots, same organisation, currently nothing tying them together |
| `lab.png` | lab | the laboratory they lose. One shot, but it is the inciting incident and everything after it is a substitution for that room |

Run `tools/video/refs.py` to print the image prompt for each. Generate it with a
*still* generator, drop the PNG in `refs/`, and the video harness picks it up
automatically — `--list` shows which are present and which are missing.

Iterate on the still, not on the video. A still is cheap to regenerate and a
video is not, so a character is worth getting right on a plate before a single
second of motion is generated against it.

One API detail the harness handles for you: passing reference images forces
`person_generation` to `allow_adult`, where text-to-video requires `allow_all`.
Sending the wrong one is a hard error.

---

## Generating them automatically

`tools/video/generate.py` submits these to Veo straight off the edit. The EDL is
the source of truth — every red card's prompt lives on the card in
`tools/video/animatic.py`, so this file and the tool can't drift apart, and a new
red card appears in the tool the moment it's added to the film.

```sh
export GEMINI_API_KEY=...                            # Veo needs a paid tier
python tools/video/generate.py --list                # the seven, one line each
python tools/video/generate.py --dry-run             # exact prompts, no calls
python tools/video/generate.py --only power          # just the breaker shot
python tools/video/generate.py                       # all seven
```

It asks for 8 seconds at 1080p, folds the house look into each prompt, strips the
generated audio, trims to the slot length off a 0.4s offset, and writes to
`build/gen/<slug>.mp4`. Seeds are fixed per shot, so a regeneration is a
variation rather than a fresh roll of the dice. `--list` and `--dry-run` need no
key.

Wiring a finished shot into the film is a one-line change: swap that card's
`S(...)` in the EDL for a `C(...)` pointing at the generated file, and re-render.

---

## P0 — do these first

### 1. YOU HAVE USED TOO MUCH POWER

| | |
|---|---|
| slot | 0:10.0, Act I |
| length | 4.5s |
| vibe | 5 → 6 (flatline) |

This is the film's conflict, stated in the first twenty seconds, before there is
a hero or a party to lose — and stated in words a ten-year-old reads off the wall
at a glance, which is the only reason the rest of the film is followable. It is
paid off at 1:58 when the same authority puts a hand on a breaker, and again at
2:46 when the machine's own readout says TOO MUCH about them.

The second line of the readout is the one that matters and it is easy to lose. The
cap is not a safety measure, it is a bill — the great thing was achieved, the
account was closed, and what is left gets charged at what a finished world costs.
That is the whole antagonist in one line of amber text.

```
Static macro shot of a wall-mounted domestic utility panel in a dark, empty
hallway at night. A small amber LCD screen on the panel reads "YOU HAVE USED TOO
MUCH POWER / NEW LIMIT: WHAT A FINISHED WORLD NEEDS". A relay clicks
inside the panel and the hallway lights behind it step down one level, dimmer. No
people in shot. Locked-off camera, no movement. Available light only, heavy film
grain, near-monochrome with the amber display as the only colour in frame. 1990s
security-camera character, slightly soft, slightly underexposed.
```

Notes. The text has to be legible — if the generator garbles it, generate the
panel clean and we'll comp the readout ourselves; it's a flat rectangle on a
locked-off shot and that is an easy composite. The light stepping down inside the
shot is the important beat, not the text.

Alternate if the panel reads as too domestic: the same notice on a printed letter
under a door, or on a wall-mounted meter in a stairwell.

---

### 1b. THEIR POWER WAS CUT

| | |
|---|---|
| slot | 0:35.6, opening Act II |
| length | 3.5s |
| vibe | 6 → 11 (waking) |

The film's inciting incident, and until this card existed the ritual had no cause
— twenty people sat in a dome because the story needed them to. They are there
because this room stopped working.

That makes everything in Act II a substitution for equipment they can no longer
power. The circle is not a séance, it is the same experiment run on the only
supply nobody is metering, and the beams leaving the dome are the output stage.
Get this shot right and the rest of the act stops looking like mysticism.

```
Interior of a small cluttered laboratory at night. A rack of computers powers
down row by row, cooling fans winding down to silence, status LEDs going out one
bank at a time until only emergency lighting remains. Papers, notebooks and
coffee cups abandoned mid-work on the bench. Cable runs, a whiteboard covered in
working. No people in frame. Locked-off static wide, no camera movement.
Available light only, heavy film grain, near-monochrome, the last equipment LEDs
the only colour in frame.
```

Notes. The fans winding down are the sound of this shot and probably its best
asset — ask for them explicitly. Nobody in frame is deliberate: the people are
already gone, and where they went is the next card.

Alternate if the rack reads as too corporate: a bench of lab instruments — a
centrifuge spinning down, an oscilloscope going dark — which is smaller and more
personal.

---

### 2. THEY CUT THE POWER

| | |
|---|---|
| slot | 1:58.3, Act IV |
| length | 3.5s |
| vibe | 63 → 26 — the steepest fall in the film |

The payoff. Everything about the Softening up to this point is soft: leaflets,
water bottles, decibel readings, a smug man with a book. This is the one moment
the argument becomes a physical act, and it lands exactly on the collapse in the
telemetry — the vibe number falls off a cliff under this shot because the room
really did go quiet at this point in the recording.

Cutting the power and deleting the record are the same action here. With the room
dark the meter has nothing to read, so the evidence ends with the light.

```
An electrical intake cupboard on the wall of a dark hall, beside a temporary
structure of raw pine framing and silver mylar, its grey steel door open on
a bank of old breakers. A gloved hand in a soft sage-green sleeve reaches in,
takes hold of the main breaker and pulls it down firmly. In the same frame, the
corridor and the lit room visible beyond it drop to black — the music and the
light die together. Single locked-off wide shot, no cut, no camera movement.
Available fluorescent light before the pull, near-total darkness after, with only
a faint spill from a distant EXIT sign. Heavy grain, near-monochrome.
```

Notes. It must be one continuous frame with the pull and the blackout in it — if
the generator cuts, or fades, the shot is worthless and the beat dies. No face,
no body, just the sleeve and the hand: the point is that it is procedural.

Hold roughly a second of darkness at the end. That darkness is the cut point into
the particle field retracting.

Alternate framing if the cupboard doesn't work: a hand on a wall-mounted isolator
switch outside a fire door, same action, same blackout.

---

### 3. ZVEN RITUAL — find the source before you generate it

| | |
|---|---|
| slot | 0:44.9, Act II |
| length | 7.0s |
| vibe | 12 → 21 (waking) |

**Look for the original first.** The meditation circle with the crossed blue beams
is the single most credible image in the film, and the contest cut contains 1.9
seconds of it (16.0–17.9). Act II wants thirty. If the rushes exist anywhere,
they are worth more than anything on this list.

Only if they are genuinely gone:

```
Twenty people seated cross-legged in a wide meditation circle on the floor of a
dark geodesic dome. Two blue laser beams cross overhead in the haze. Candles burn
around the perimeter. EEG biosensor headbands are being fitted, people helping
each other with the straps. Everyone is still and quiet. Very slow push-in from
the edge of the circle. Available candlelight only, heavy grain, near-monochrome
except for the blue of the beams. Documentary, observed, nobody aware of camera.
```

Notes. Generate this as three or four separate 3-second angles rather than one
7-second take — a wide, a two-shot of headbands going on, and an insert of a face
with eyes closed. Cut together they will hold seven seconds far better than a
single generated shot will.

---

## P1

### 4. DANCING IN THE DARK

| | |
|---|---|
| slot | 1:52.3, Act IV |
| length | 6.0s |
| vibe | 25 → 63 (the reversal) |

The hope beat, and the longest generated shot in the film. The caps have bitten,
the room is dark, and they keep going anyway — the number climbs right through
this shot and the score comes back up with it. Then the power gets cut.

```
A dense crowd dancing hard in near-total darkness, lit only by one or two phone
torches sweeping across faces and raised arms. Bodies read mostly as silhouettes
with brief flashes of a face or a hand as the light passes. Handheld camera at
chest height inside the crowd, jostled. Extreme grain, almost pure monochrome,
deep crushed blacks. Energy building through the shot. Real people, unglamorous,
sweating, absorbed, nobody looking at camera.
```

Notes. Wants to feel *harder* than the lit party footage in Act III, not softer.
Underexposed is correct. If it comes back looking like a nightclub advert, push
the darkness further and cut the crowd size.

---

### 5. WELLNESS INSPECTORS ARRIVE

| | |
|---|---|
| slot | 1:38.1, Act IV |
| length | 4.5s |
| vibe | 71 → 46 (the party is already dying) |

The field staff, not the author. This cuts against Act III's half-second cutting
at two to three seconds per beat, so the calm itself is the intrusion.

```
Three or four people in soft sage-green softshell jackets with ID lanyards walk
through a low timber doorway and calmly into a hazy candlelit tabernacle of raw
pine framing and silver mylar sheeting at night. They carry clipboards and a handheld
sound-level meter. One of them smiles and offers a bottle of water to a dancer,
who takes it, confused. No uniforms, no insignia, no weapons, no urgency at all.
Handheld observational camera, following at a distance. Available light, haze,
heavy grain, near-monochrome. Slow walk-in.
```

Notes. The water bottle is the shot. If you only get one usable beat out of the
generation, get that one.

---

## P2

### 6. THE METER IN THE DOORWAY

| | |
|---|---|
| slot | 1:21.1, Act III |
| length | 3.0s |
| vibe | 76 → 77 (the peak) |

Measurement arriving before enforcement, planted at the top of the film's biggest
high. Nobody in the party reacts to it — they don't know they are being assessed,
which is what makes three seconds enough.

```
A calibrated handheld sound-level meter held at arm's length in a doorway, its red
LED display reading 96.4 dB. The doorway is raw timber. Behind it and far out of
focus, a candlelit tabernacle of pine framing and silver mylar
strobing and full of people. The hand holding the meter is steady and unhurried,
an ID lanyard hanging from the wrist. Very shallow depth of field — the meter
sharp, the celebration soft. Night, available light, heavy grain, near-monochrome
apart from the red of the display.
```

Notes. This is the one place shallow depth is right, because the whole idea is an
instrument in focus and people out of it.

---

### 7. THE AFTERMATH

| | |
|---|---|
| slot | 2:19.4, Act IV |
| length | 5.0s |
| vibe | 0.0, absolute zero, and the score is silent under all of it |

The Nothing. Five seconds of a room that had something in it. This is the longest
the film holds anything, and it should be uncomfortable.

```
Static wide shot of an emptied tabernacle at dawn — an octagonal chamber of raw
pine framing hung with silver mylar, erected inside a larger dark hall. Candles burned out
and still smoking, floor cushions stacked against a wall, house fluorescent lights
up hard and flat, nobody there at all. No movement anywhere in frame except one
thin thread of candle smoke rising. Locked-off camera, absolutely no movement, no
cut. Cold flat overhead light, heavy grain, near-monochrome.
```

Notes. Must be genuinely static — any drift, any push, any life in the frame
undoes it. The thread of smoke is the only permitted movement and it is what stops
the shot reading as a freeze frame.

---

## Not on this list: the amber cards

Seven cards in the animatic are amber, meaning we render them ourselves out of
VibeMap and real telemetry. No generator, no shoot, no cost:

| slot | length | card |
|---|---|---|
| 0:19.5 | 5.0s | NOTHING LEFT TO DO — party level 0.03%, vibe at 6, read as a success |
| 1:01.9 | 3.7s | SIGNAL STRENGTH — the meter climbing 28 → 43 |
| 1:45.3 | 4.0s | THE NUMBER FALLS — 39 / 25 / 16 as the caps bite |
| 1:49.3 | 3.0s | THE MACHINE DISAGREES — a full room reading 16, and the third party's first refusal |
| 2:24.4 | 5.0s | THE TURN — 0 → 1 → 2, the map relighting |
| 2:46.4 | 4.0s | THE MACHINE PICKS A SIDE — a second trace that leads the first, WATCHING → JOINING IN |
| 2:54.4 | 5.6s | MOONSHOT — title and the HYPERSTITION lockup |

Two of those are load-bearing rather than decorative. **THE MACHINE DISAGREES**
is where the readout refuses to back him up, and **THE MACHINE PICKS A SIDE** is
where it goes over to the other one — the film's third party, which has no voice
and does all of its arguing in the chrome. Treat them as performances, not titles.

Every word on these cards is checked by `tools/video/reading_level.py`, which
reads the strings out of `panels.py` and fails the build if the console starts
talking like a console. Same for the spoken lines in `docs/vo-script.md`.

---

## Where the antagonist already is

Worth knowing before generating, so the new shots don't duplicate what's covered.
The Softening's author is real footage we already hold, and he now appears three
times:

| slot | what |
|---|---|
| 0:24.5 | glimpsed in Act I, unexplained, before anyone has met him |
| 1:35.6 | returns at the party's peak — a recognition, not an introduction |
| 1:42.6 | holds up DEFANGED NOUMENA, the case for the caps |
| 2:06.8 | salutes the room he has just killed, and leaves |

He is smug, not jackbooted. Every generated shot on this list should match that
register: the authority in this film is polite, certain it is doing good, and
never raises its voice.
