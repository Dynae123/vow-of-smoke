# SFX & Audio Tag Audit: Episodes 1-12

**Show:** Vow of Smoke
**Auditor:** Automated pass
**Date:** 2026-03-06
**Scope:** All `[SFX:]`, `[AMBIENT:]`, `[beat]`, `[DIRECTION:]` tags in scripts ep01 through ep12

---

## Tag Convention Reference

| Tag | Purpose |
|-----|---------|
| `[SFX: ...]` | Producible sound effects only |
| `[AMBIENT: ...]` | Continuous background track |
| `[DIRECTION: ...]` | Narrative/emotional context (NOT audio) |
| `[Beat — Xms]` / `[Long beat — Xms]` | Timed pauses |
| `[beat]` | Untimed pause (current usage in scripts) |

---

## Global Issue: Beat/Silence Tags Lack Timing

**Every `[beat]` tag across all 12 episodes is untimed.** The convention specifies `[Beat -- Xms]` and `[Long beat -- Xms]` with millisecond durations. None of the scripts use this format. All beats are written as lowercase `[beat]` with no duration. This is a systemic issue affecting every episode and will be called out per-episode but the fix is the same everywhere: assign durations based on dramatic weight.

**Recommended timing tiers:**
- Short beat (breath, micro-pause): `[Beat -- 400ms]`
- Standard beat (thought, reaction): `[Beat -- 800ms]`
- Long beat (emotional weight, revelation): `[Long beat -- 1500ms]`
- Heavy beat (devastating moment): `[Long beat -- 2500ms]`

---

## Global Issue: No `[AMBIENT:]` Tags Exist

**Not a single `[AMBIENT:]` tag appears in any of the 12 scripts.** Environmental/background sound is instead embedded inside `[SFX:]` tags (e.g., `[SFX: the apartment at night. The fridge cycling. Rune shifting in bed]`). This creates two problems:

1. The assembler cannot distinguish one-shot effects from continuous background layers.
2. Scene-establishing atmosphere is tangled with discrete sound events.

Every scene needs its ambient separated from its spot SFX. This is flagged per-episode below.

---

## Global Issue: No Layering Instructions Anywhere

**No SFX tag in any episode includes layering notation** (`[spot]`, `[under]`, `[bed]`, `[bridge]`, `[fade-in]`, `[fade-out]`). Every single SFX tag is missing placement context. Rather than repeat this for every tag, layering recommendations are provided for representative/critical tags per episode, with the understanding that ALL tags need this pass.

---

## Global Issue: Internal Monologue Marking

Per the INTERNAL-MONOLOGUE-GUIDE, Rune's internal lines require bandpass + micro-echo processing. The scripts use the format:

```
RUNE (inner monologue):
```

This is **consistent across all 12 episodes** -- always `RUNE (inner monologue):`, never varying. This is good. However, two issues:

1. **No other character gets internal monologue.** Ash has one quasi-internal moment in Ep6 Scene 1 (`ASH (not speaking to anyone -- surfacing, like a diver breaking water):`), which is direction embedded in the character tag rather than proper internal monologue marking. If this should get the bandpass filter, it needs to be marked `ASH (inner monologue):` or `ASH (INTERNAL):`.

2. **The guide says `RUNE (INTERNAL):`** in its example, but the scripts use `RUNE (inner monologue):`. Pick one and standardize. Recommend keeping `RUNE (inner monologue):` since it's already consistent across all 12 scripts, and updating the guide to match.

---

# Per-Episode Audit

---

## Episode 1: "First Response"

**Tag counts:**
- SFX tags: 18
- AMBIENT tags: 0
- Beat tags: 6 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: roaring fire -- consuming, enormous. Stone cracking under heat. Ancient chanting, low and rhythmic, bleeding upward into a scream]`

- "consuming, enormous" is direction, not a producible sound quality.
- "bleeding upward into a scream" is narrative.
- **Fix:**
  - `[SFX: roaring fire, large-scale. Stone cracking under heat. Ancient chanting, low and rhythmic, rising into a scream]`
  - `[DIRECTION: The fire is consuming, enormous -- a ritual blaze, not a house fire]`

**Line 18:**
> `[SFX: a hand gripping another -- skin on skin, desperate -- then slipping free]`

- "desperate" is emotional direction, not a sound quality.
- **Fix:**
  - `[SFX: a hand gripping another -- skin on skin -- then slipping free]`
  - `[DIRECTION: The grip is desperate -- someone trying not to lose someone]`

**Line 26:**
> `[SFX: sharp gasp -- Rune jolting awake. Ambulance siren, mid-wail. The hum of an engine on asphalt]`

- Multiple distinct sounds crammed into one tag. The gasp is a vocal SFX, the siren is environmental, the engine is ambient.
- **Fix:**
  - `[SFX: sharp gasp -- Rune jolting awake] [spot]`
  - `[AMBIENT: Ambulance interior -- siren mid-wail, engine hum on asphalt]`

**Line 88:**
> `[SFX: keys in a lock. Door opening and closing. The deep silence of a small apartment at 3 AM. A fridge hum]`

- "The deep silence of a small apartment at 3 AM" is direction/narrative -- silence is not a producible SFX.
- **Fix:**
  - `[SFX: keys in a lock. Door opening and closing] [spot]`
  - `[AMBIENT: Small apartment at 3 AM -- fridge hum, deep quiet]`
  - `[DIRECTION: The silence is heavy. A space that says: someone lives here, but not very much]`

**Line 100:**
> `[SFX: silence. Then -- the crackle of a dispatch radio on a bedside table]`

- "silence" is not producible SFX.
- **Fix:**
  - `[Beat -- 1500ms]`
  - `[SFX: dispatch radio crackling to life on a bedside table] [spot]`

**Line 142:**
> `[SFX: Rune's hand pressing against the man's chest. Then -- a sharp, high-frequency sound. Every scar on the man's body igniting at once -- a brief, blinding flare of heat and light]`

- "Every scar on the man's body igniting at once -- a brief, blinding flare of heat and light" is visual/narrative description.
- **Fix:**
  - `[SFX: skin pressing against skin. Then -- a sharp, high-frequency tone spiking] [spot]`
  - `[DIRECTION: Every scar on Ash's body ignites -- a brief, blinding flare of heat and light]`

**Line 146:**
> `[SFX: the hum in the shrine spikes -- vibrating through stone, through bone. Then it locks. A deep, resonant click, felt more than heard. Like a key turning in a lock inside Rune's chest]`

- "vibrating through stone, through bone" is physical direction. "felt more than heard" is direction. "Like a key turning in a lock inside Rune's chest" is pure narrative/metaphor.
- **Fix:**
  - `[SFX: subsonic hum spikes sharply, then resolves into a deep resonant click] [spot]`
  - `[DIRECTION: The hum vibrates through stone, through bone. The click is felt more than heard -- like a key turning in a lock inside Rune's chest]`

**Line 150:**
> `[SFX: the flare dies. Silence. Then -- the man's breathing. Slow. Deep]`

- "Silence" is not producible. "Slow. Deep" is direction for the breathing.
- **Fix:**
  - `[Beat -- 800ms]`
  - `[SFX: slow, deep breathing] [bridge]`

**Line 152:**
> `[SFX: eyes opening -- not a sound, but the shift in the man's breathing. A sharp inhale]`

- "eyes opening -- not a sound" literally declares it is not a sound. This is direction.
- **Fix:**
  - `[SFX: sharp inhale] [spot]`
  - `[DIRECTION: Ash's eyes open]`

**Line 170:**
> `[SFX: the subsonic hum beneath the shrine -- steady now. Constant. A new frequency in the world that wasn't there before]`

- "A new frequency in the world that wasn't there before" is narrative.
- **Fix:**
  - `[AMBIENT: subsonic hum beneath the shrine -- steady, constant] [bed]`

**Line 178:**
> `[SFX: the hum. Low. Steady. The sound of a bond that will not break]`

- "The sound of a bond that will not break" is narrative.
- **Fix:**
  - `[AMBIENT: low, steady hum] [bed, fade-out over episode end]`

### Issue 2: Vague/Unproducible SFX

**Line 124:**
> `[SFX: footsteps shifting from gravel to stone. The ambient sound drops -- the highway noise muffles, replaced by a faint, subsonic hum]`

- The transition instruction ("the ambient sound drops") is a mixing direction, not a sound effect.
- **Fix:**
  - `[SFX: footsteps shifting from gravel to stone] [bridge]`
  - `[AMBIENT: highway noise fades to muffled; replaced by faint subsonic hum] [crossfade]`

### Issue 3: Missing Layering (representative examples)

| Line | Tag | Recommended Layering |
|------|-----|---------------------|
| 10 | Roaring fire, stone cracking, chanting | `[bed]` -- continuous dream soundscape, fade-in at scene start |
| 14 | Chanting distorts | `[under]` -- plays under following inner monologue |
| 26 | Gasp + siren + engine | Gasp: `[spot]`. Siren/engine: `[bed]` for Scene 2 |
| 34 | Siren winds down, road noise, radio | Siren: `[spot, fade-out]`. Road noise + radio: `[bed]` |
| 58 | Medical bag, BP cuff, monitor | `[spot]` sequence between lines |
| 70 | Cuff inflating, monitor beeping | Cuff: `[spot]`. Monitor: `[bed]` |
| 82 | Gurney wheels | `[spot]` |
| 88 | Keys, door, fridge | Keys/door: `[spot]`. Fridge: `[bed]` |
| 93 | Boots dropping, body on mattress | `[spot]` |
| 116 | Car engine, door, traffic, gravel | Engine cut + door: `[spot]`. Traffic: `[bed]`. Gravel footsteps: `[bridge]` |
| 128 | Footsteps through ash, bag clinking | `[bridge]` -- starts between lines, continues under next monologue |
| 136 | Footsteps quickening, knees on stone | `[spot]` |

### Issue 4: AMBIENT Coverage

Every scene shift needs an AMBIENT tag. Current state:
- **Scene 1 (Nightmare):** No AMBIENT. Needs: `[AMBIENT: dream soundscape -- roaring fire, distant chanting] [bed]`
- **Scene 2 (Ambulance):** No AMBIENT. The SFX on line 34 partially covers this but should be split: `[AMBIENT: ambulance interior -- road noise, low radio chatter] [bed]`
- **Scene 3 (Apartment hallway):** No AMBIENT. Needs: `[AMBIENT: apartment building hallway -- muffled building sounds] [bed]`
- **Scene 4 (Rune's apartment):** No AMBIENT. Line 88 partially covers. Needs: `[AMBIENT: small apartment, 3 AM -- fridge hum, deep quiet] [bed]`
- **Scene 5 (Abandoned shrine):** No AMBIENT. Line 116 partially covers. Needs: `[AMBIENT: highway overpass -- distant drone overhead, gravel and weeds] [bed]`, then crossfade to `[AMBIENT: inside the shrine -- muffled highway, subsonic hum, warm dead air] [bed, crossfade]`

### Issue 5: Beat Consistency

6 beats, all untimed. Recommended durations:
- Line 22 `[beat]` after "Rune.": `[Beat -- 800ms]` (dream-pause)
- Line 97 `[beat]` after name comment: `[Beat -- 400ms]`
- Line 104 `[beat]` after dispatch: `[Beat -- 800ms]` (decision moment)
- Line 132 `[beat]` after "Is anyone here?": `[Long beat -- 1500ms]` (empty shrine, tension)
- Line 157 `[beat]` after void eyes: `[Long beat -- 1500ms]`
- Line 161 `[beat]` before "Fury": `[Beat -- 800ms]`

### Issue 6: Internal Monologue

All inner monologue lines use `RUNE (inner monologue):` consistently. Count: 14 inner monologue lines. No marking issues in this episode.

---

## Episode 2: "Ash"

**Tag counts:**
- SFX tags: 20
- AMBIENT tags: 0
- Beat tags: 8 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 12:**
> `[SFX: the subsonic hum, low and steady. Ash's breathing -- too slow, too controlled for someone who just woke up on a stone floor]`

- "too slow, too controlled for someone who just woke up on a stone floor" is narrative direction.
- **Fix:**
  - `[AMBIENT: subsonic hum, low and steady] [bed]`
  - `[SFX: Ash's breathing -- slow, unnaturally controlled] [under]`
  - `[DIRECTION: His breathing is too controlled for someone who just woke up on a stone floor]`

**Line 22:**
> `[SFX: a shift in the air -- the temperature in the shrine rising by several degrees. The ash on the ground stirring, disturbed by heat that has no source]`

- Temperature rising is not producible sound. "disturbed by heat that has no source" is narrative.
- **Fix:**
  - `[SFX: a low pressure shift. Fine ash stirring on the ground] [under]`
  - `[DIRECTION: The temperature in the shrine rises by several degrees. The heat has no visible source]`

**Line 46:**
> `[SFX: Ash turning his head -- the faint scrape of skin against stone. Looking at the shrine walls. Looking at Rune's flashlight, his medical bag, his phone clipped to his belt]`

- "Looking at the shrine walls..." is visual direction.
- **Fix:**
  - `[SFX: faint scrape of skin against stone] [spot]`
  - `[DIRECTION: Ash turns his head, scanning -- the shrine walls, Rune's flashlight, his medical bag, his phone]`

**Line 82:**
> `[SFX: the gentle tap of Rune finding a vein on Ash's arm. Then the IV needle touching skin -- and a sharp, metallic hiss. Metal softening, deforming]`

- "Metal softening, deforming" is a visual description. The producible sound is the hiss.
- **Fix:**
  - `[SFX: gentle tap on arm. IV needle touches skin -- sharp metallic hiss] [spot]`
  - `[DIRECTION: The needle doesn't bend -- it melts. The tip softens and runs like his skin is a burner]`

**Line 108:**
> `[SFX: apartment door opening. The familiar hum of the fridge. Rune's keys dropping onto a counter. Then -- unfamiliar footsteps. Heavier. Slower. Someone taking in a space they've never been in]`

- "Someone taking in a space they've never been in" is narrative.
- **Fix:**
  - `[SFX: apartment door opening. Keys dropping on counter] [spot]`
  - `[AMBIENT: apartment -- fridge hum] [bed]`
  - `[SFX: unfamiliar footsteps -- heavier, slower than Rune's] [bridge]`
  - `[DIRECTION: Someone taking in a space they've never seen]`

**Line 128:**
> `[SFX: Ash looking at his hands -- the faint rasp of scarred skin rubbing against itself]`

- "Ash looking at his hands" is visual direction.
- **Fix:**
  - `[SFX: faint rasp of scarred skin rubbing together] [spot]`

**Line 148:**
> `[SFX: the apartment settling. The fridge cycling. Distant traffic. Ash hasn't moved from the couch. Rune is sitting across from him on the floor, back against the wall]`

- "Ash hasn't moved..." and "Rune is sitting..." are stage direction/narrative.
- **Fix:**
  - `[AMBIENT: apartment settling -- fridge cycling, distant traffic] [bed]`
  - `[DIRECTION: Ash hasn't moved from the couch. Rune sits across from him on the floor, back against the wall]`

**Line 184:**
> `[SFX: a sharp flare -- not physical, not audible to anyone but them. A surge through the bond like grabbing a live wire]`

- "not physical, not audible to anyone but them" -- the tag literally says it isn't a sound. "like grabbing a live wire" is metaphor.
- **Fix:**
  - `[SFX: a sharp electrical surge tone -- brief, high-frequency] [spot]`
  - `[DIRECTION: Not physical. Not audible to anyone but them. A surge through the bond like grabbing a live wire]`

**Line 240:**
> `[SFX: the low, steady hum of the bond -- just beneath hearing. Like a transformer on the other side of a wall]`

- "just beneath hearing" is direction about perception. "Like a transformer on the other side of a wall" is simile/direction.
- **Fix:**
  - `[AMBIENT: low, steady hum -- subsonic, transformer-like] [bed]`

**Line 248:**
> `[SFX: the hum. Steady. Patient. The sound of something that has no intention of stopping]`

- "Patient" and "The sound of something that has no intention of stopping" are narrative.
- **Fix:**
  - `[AMBIENT: the hum, steady] [bed, fade-out over scene end]`

### Issue 2: Vague/Unproducible SFX

**Line 128:** `[SFX: Ash looking at his hands]` -- Looking is not a sound. (Fixed above.)

**Line 52:** `[SFX: the quiet frustration of a search going nowhere]` (Ep3 line 52) -- Not in this episode but noting the pattern. Frustration is not a sound.

### Issue 4: AMBIENT Coverage

- **Scene 1 (Shrine, continuous):** No AMBIENT. Needs: `[AMBIENT: inside the shrine -- subsonic hum, still warm air, muffled highway above] [bed]`
- **Scene 2 (Outside shrine / Rune's car):** No AMBIENT. Needs: `[AMBIENT: outside shrine -- highway traffic overhead, night air] [bed]`
- **Scene 3 (Rune's apartment):** No AMBIENT. Line 108 partially covers. Split needed.
- **Scene 4 (Rune's apartment, later):** No AMBIENT. Line 148 partially covers. Split needed.
- **Scene 5 (Rune's apartment, deep night):** No AMBIENT. Line 228 partially covers. Needs: `[AMBIENT: apartment, 4 AM -- minimal, fridge, breathing] [bed]`

### Issue 6: Internal Monologue

All consistent: `RUNE (inner monologue):`. Count: 12 inner monologue lines. No issues.

---

## Episode 3: "Binding Marks"

**Tag counts:**
- SFX tags: 22
- AMBIENT tags: 0
- Beat tags: 10 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: the city at dawn -- birds, distant traffic, the first buses. But underneath it, barely audible: the subsonic thrum. Something old vibrating beneath concrete. Then it cuts]`

- "Something old vibrating beneath concrete" is narrative. "Then it cuts" is a mixing instruction.
- **Fix:**
  - `[AMBIENT: city at dawn -- birds, distant traffic, first buses. Subsonic thrum underneath, barely audible] [bed]`
  - `[SFX: the subsonic thrum cuts abruptly] [spot]`
  - `[DIRECTION: Something old vibrating beneath concrete -- then gone]`

**Line 28:**
> `[SFX: the click of a lighter. Then -- the sound of flame behaving wrong. Flickering, bending, leaning toward something instead of rising]`

- "behaving wrong" and "leaning toward something instead of rising" are visual/narrative.
- **Fix:**
  - `[SFX: lighter click. Flame flickering -- wavering, unsteady, pulled sideways] [under]`
  - `[DIRECTION: The flame bends toward Ash's fingers like it's alive. Like it knows him]`

**Line 52:**
> `[SFX: laptop keys clicking. Scrolling. The quiet frustration of a search going nowhere]`

- "The quiet frustration of a search going nowhere" is emotional direction.
- **Fix:**
  - `[SFX: laptop keys clicking. Mouse scrolling] [under]`

**Line 72:**
> `[SFX: forty minutes of ambient silence compressed into a few seconds. Then -- the phone ringing. Sharp, immediate]`

- "forty minutes of ambient silence compressed into a few seconds" is a narrative/editing instruction, not a producible sound.
- **Fix:**
  - `[Beat -- 1500ms]`
  - `[SFX: phone ringing -- sharp, sudden] [spot]`
  - `[DIRECTION: Forty minutes have passed]`

**Line 98:**
> `[SFX: car engine. City traffic -- honking, the rumble of a bus, crosswalk signals beeping. Ash in the passenger seat, rigid]`

- "Ash in the passenger seat, rigid" is visual/stage direction.
- **Fix:**
  - `[AMBIENT: car interior -- engine, city traffic, honking, bus rumble, crosswalk beeping] [bed]`
  - `[DIRECTION: Ash in the passenger seat, rigid]`

**Line 128:**
> `[SFX: a tense silence. The bond humming between them -- Rune can feel Ash's anger like heat through a wall]`

- "a tense silence" is not producible. "Rune can feel Ash's anger like heat through a wall" is narrative.
- **Fix:**
  - `[Long beat -- 1500ms]`
  - `[SFX: low bond hum, agitated] [under]`
  - `[DIRECTION: Rune can feel Ash's anger through the bond -- like heat through a wall]`

**Line 144:**
> `[SFX: a door opening into a cluttered academic office. Books everywhere -- shelves bowing under weight. Papers. The hum of an old desktop computer. A window open to the campus quad -- distant student voices, pigeons]`

- "Books everywhere -- shelves bowing under weight. Papers." is visual description.
- **Fix:**
  - `[SFX: heavy door opening into a room] [spot]`
  - `[AMBIENT: academic office -- old desktop humming, open window to campus quad, distant student voices, pigeons] [bed]`

**Line 154:**
> `[SFX: Kaya standing. Moving closer. His breathing changes -- controlled, deliberate. The intake of someone looking at something they've only ever read about]`

- "The intake of someone looking at something they've only ever read about" is narrative.
- **Fix:**
  - `[SFX: chair pushing back. Footsteps approaching. Controlled, deliberate intake of breath] [spot]`

**Line 192:**
> `[SFX: silence. The office clock ticking. A pigeon cooing outside the window. The hum of the bond between Rune and Ash -- both of them aware of it now, both of them unable to ignore it]`

- "silence" is not producible. "both of them aware of it now, both of them unable to ignore it" is narrative.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[AMBIENT: office -- clock ticking, pigeon cooing outside] [bed]`
  - `[SFX: bond hum, low] [under]`

**Line 232:**
> `[SFX: the shadows in the office shifting -- bending toward Ash. The light from the window dimming. Kaya's desk lamp buzzing, straining]`

- "shadows shifting -- bending toward Ash" and "light from the window dimming" are visual.
- **Fix:**
  - `[SFX: desk lamp buzzing, straining -- electrical flicker] [under]`
  - `[DIRECTION: The shadows bend toward Ash. The window light dims]`

**Line 254:**
> `[SFX: the heavy door of the humanities building swinging shut. Campus noise -- students, bicycles, the normalcy of a world that has no idea. Rune and Ash walking. Ash's footsteps heavier, angrier]`

- "the normalcy of a world that has no idea" is narrative. "angrier" is emotional direction applied to footsteps.
- **Fix:**
  - `[SFX: heavy door swinging shut] [spot]`
  - `[AMBIENT: campus -- students, bicycles, outdoor activity] [bed]`
  - `[SFX: footsteps on pavement -- Ash's heavier, harder than Rune's] [bridge]`

**Line 288:**
> `[SFX: a beat. Kaya's breathing. The sirens growing louder]`

- "a beat" is a pause instruction written as SFX.
- **Fix:**
  - `[Beat -- 800ms]`
  - `[SFX: Kaya's ragged breathing. Sirens growing louder in the distance] [under]`

**Line 296:**
> `[SFX: the sirens. The subsonic thrum -- louder than before. The city, shaking at a frequency no one else can hear]`

- "The city, shaking at a frequency no one else can hear" is narrative.
- **Fix:**
  - `[SFX: sirens. Subsonic thrum rising, louder than before] [bed, fade-out over scene end]`

**Line 304:**
> `[SFX: the hum between them. The bond. Louder now. Resonating with something deep beneath the city]`

- "Resonating with something deep beneath the city" is narrative.
- **Fix:**
  - `[SFX: bond hum, louder, with a deeper sub-frequency] [under, fade-out]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (Rune's kitchen, dawn):** No AMBIENT. Line 10 partially covers. Split needed.
- **Scene 2 (Rune's apartment, laptop):** No AMBIENT. Needs: `[AMBIENT: apartment daytime -- fridge, muted traffic] [bed]`
- **Scene 3 (City streets, driving):** No AMBIENT. Line 98 partially covers. Split needed.
- **Scene 4 (Kaya's office):** No AMBIENT. Line 144 partially covers. Split needed.
- **Scene 5 (City street, leaving university):** No AMBIENT. Line 254 partially covers. Split needed.

---

## Episode 4: "Fault Lines"

**Tag counts:**
- SFX tags: 20
- AMBIENT tags: 0
- Beat tags: 8 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: overlapping radio reports -- tinny, urgent, layered on top of each other. Different stations, different anchors, the same disaster]`

- "Different stations, different anchors, the same disaster" is narrative/production direction.
- **Fix:**
  - `[SFX: overlapping radio reports -- tinny, urgent, multiple stations layered] [bed]`

**Line 18:**
> `[SFX: the radio reports blur together, then cut. Silence. Then the subsonic thrum -- louder than before. A sound like stone exhaling]`

- "Silence" is not producible. "A sound like stone exhaling" is a simile, though useful as creative direction for design.
- **Fix:**
  - `[SFX: radio reports blur and cut abruptly] [spot]`
  - `[Beat -- 1500ms]`
  - `[SFX: subsonic thrum rises, louder -- deep, geological, like stone exhaling] [bridge]`

**Line 30:**
> `[SFX: ambulance doors slamming. Boots on rubble. Sirens -- multiple, overlapping. The crunch and groan of unstable debris. Voices shouting. Dust. The roar of a rescue crew working against time]`

- "Dust" is not a sound. "The roar of a rescue crew working against time" is narrative.
- **Fix:**
  - `[SFX: ambulance doors slamming] [spot]`
  - `[AMBIENT: collapse site -- boots on rubble, multiple overlapping sirens, unstable debris groaning, voices shouting, rescue crew activity] [bed]`

**Line 40:**
> `[SFX: a woman crying, somewhere close. Rune kneeling. Debris being shifted by hand]`

- "Rune kneeling" is not a producible sound.
- **Fix:**
  - `[SFX: a woman crying, close. Debris being shifted by hand] [under]`

**Line 64:**
> `[SFX: the rescue noise fading to background. Rune walking away from the rubble, peeling off gloves. Heavy breathing. Then -- he feels it. The bond. A tug behind his sternum]`

- "he feels it. The bond. A tug behind his sternum" is internal/narrative.
- **Fix:**
  - `[AMBIENT: rescue noise, faded to background] [bed, crossfade from previous]`
  - `[SFX: footsteps off rubble. Gloves peeling off. Heavy breathing] [bridge]`
  - `[DIRECTION: Rune feels the bond -- a tug behind his sternum. Ash is here]`

**Line 108:**
> `[SFX: the collapse site, quieter now. Most of the rescue crews have moved on. Generators humming. Ash's footsteps -- deliberate, drawn -- moving into the rubble field. Rune following]`

- "Most of the rescue crews have moved on" is narrative. "drawn" is emotional direction on footsteps.
- **Fix:**
  - `[AMBIENT: collapse site, quieter -- generators humming, distant activity] [bed, crossfade]`
  - `[SFX: Ash's footsteps -- deliberate, slow -- moving into the rubble field. Rune's following] [bridge]`

**Line 112:**
> `[SFX: Ash doesn't stop. His footsteps descending -- the ground slopes where the foundation cracked open. Loose stone shifting]`

- "Ash doesn't stop" is direction.
- **Fix:**
  - `[SFX: footsteps descending a slope. Loose stone shifting] [bridge]`

**Line 122:**
> `[SFX: they reach the bottom -- the exposed foundation. The ambient sound changes: deeper, enclosed. The subsonic hum is louder here, resonating through the stone]`

- "the ambient sound changes: deeper, enclosed" is a mixing instruction.
- **Fix:**
  - `[AMBIENT: exposed foundation -- deeper, enclosed acoustic space. Subsonic hum louder, resonating through stone] [bed, crossfade]`

**Line 222:**
> `[SFX: the apartment at night. Rune in bed. Sheets shifting. The steady hum of the bond -- low, constant, like a transformer on the other side of a wall]`

- "Rune in bed" is stage direction. "like a transformer on the other side of a wall" is a simile.
- **Fix:**
  - `[AMBIENT: apartment at night -- quiet, minimal] [bed]`
  - `[SFX: sheets shifting] [spot]`
  - `[SFX: steady bond hum -- low, transformer-like, constant] [bed]`

**Line 254:**
> `[SFX: the hum. Low. Steady. The sound of a bond that is learning new tricks neither of them asked for]`

- "The sound of a bond that is learning new tricks neither of them asked for" is narrative.
- **Fix:**
  - `[AMBIENT: bond hum -- low, steady, subtly shifting frequency] [bed, fade-out]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (Darkness, news audio):** No AMBIENT. The radio reports serve as the soundscape but need `[bed]` layering.
- **Scene 2 (Collapse site):** No AMBIENT. Line 30 partially covers. Split needed.
- **Scene 3 (Collapse perimeter):** No AMBIENT. Needs crossfade from collapse scene.
- **Scene 4 (Ruins/foundation):** No AMBIENT. Line 122 partially covers. Split needed.
- **Scene 5 (Rune's apartment, evening):** No AMBIENT. Needs: `[AMBIENT: apartment evening -- fridge, faint traffic] [bed]`
- **Scene 6 (Rune's apartment, night):** No AMBIENT. Line 222 partially covers. Split needed.

---

## Episode 5: "Smoke and Mirrors"

**Tag counts:**
- SFX tags: 22
- AMBIENT tags: 0
- Beat tags: 12 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: the apartment in morning light. Traffic outside. The fridge humming. In the background -- pages turning. Fast. Faster than anyone reads]`

- "the apartment in morning light" is visual. "Faster than anyone reads" is narrative.
- **Fix:**
  - `[AMBIENT: apartment morning -- traffic outside, fridge humming] [bed]`
  - `[SFX: pages turning rapidly in the background] [under]`

**Line 52:**
> `[SFX: the quiet frustration of a search going nowhere]` (referenced from Ep3 pattern, noting here for Ep5)

Not present in Ep5, disregard.

**Line 150:**
> `[SFX: the beat hangs. Then -- the fridge cycling on. The world resuming. Ash looking at his bandaged hand like it's a map of somewhere he's never been]`

- "the beat hangs" is a timing instruction. "The world resuming" is narrative. "Ash looking at his bandaged hand like it's a map of somewhere he's never been" is visual/narrative.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[SFX: fridge cycling on] [spot]`
  - `[DIRECTION: Ash looks at his bandaged hand like it's a map of somewhere he's never been]`

**Line 202:**
> `[SFX: evening settling. Rune on his laptop at the kitchen table. Ash on the couch, reading -- pages turning at normal speed for once. Slower. Like he's choosing to take his time]`

- "evening settling" is narrative. "Rune on his laptop at the kitchen table. Ash on the couch, reading" is stage direction. "Like he's choosing to take his time" is narrative.
- **Fix:**
  - `[AMBIENT: apartment evening -- muted traffic, settling sounds] [bed]`
  - `[SFX: laptop keys, soft. Pages turning slowly in the other room] [under]`
  - `[DIRECTION: Ash is reading at normal speed for once -- slower, deliberate]`

**Line 244:**
> `[SFX: Ash turning the page. The apartment, quiet. The bond between them, steady]`

- "The apartment, quiet. The bond between them, steady" is narrative.
- **Fix:**
  - `[SFX: page turning] [spot]`

**Line 258:**
> `[SFX: the bond spikes -- sudden, sharp. Behind him, the temperature in the apartment jumps. Ash is on his feet before Rune reaches the handle]`

- "the temperature in the apartment jumps" is not a sound. "Ash is on his feet before Rune reaches the handle" is stage direction.
- **Fix:**
  - `[SFX: bond hum spikes -- sudden, sharp] [spot]`
  - `[DIRECTION: The temperature in the apartment jumps. Ash is on his feet before Rune reaches the door handle]`

**Line 262:**
> `[SFX: door opening. The hallway beyond -- fluorescent buzzing. Three sets of breathing]`

- "Three sets of breathing" is a producible sound but needs clarity on which is which.
- **Fix:**
  - `[SFX: door opening] [spot]`
  - `[AMBIENT: hallway -- fluorescent buzzing] [bed]`
  - `[SFX: multiple people breathing in the hallway -- controlled, deliberate] [under]`

**Line 268:**
> `[SFX: behind Rune -- the shadows in the apartment shift. The lamp flickers. The air thickens with heat]`

- "the shadows in the apartment shift" and "The air thickens with heat" are visual/non-sonic.
- **Fix:**
  - `[SFX: lamp flickering -- buzzing, straining] [under]`
  - `[DIRECTION: The shadows shift toward Ash. The air thickens with heat]`

**Line 280:**
> `[SFX: the bond. The shadows. The woman in white. The sound of something about to break]`

- "The shadows. The woman in white" are visual. "The sound of something about to break" is vague/narrative.
- **Fix:**
  - `[SFX: bond hum -- agitated, rising tension. Lamp buzzing harder] [under, fade-out over scene end]`
  - `[DIRECTION: The shadows. The woman in white. Something is about to break]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (Apartment, morning):** No AMBIENT. Line 10 partially covers. Split needed.
- **Scene 2 (Kitchen):** No AMBIENT. Needs: `[AMBIENT: apartment kitchen -- stove clicking, water sounds, domestic] [bed]`
- **Scene 3 (Apartment, afternoon):** No AMBIENT. Needs: `[AMBIENT: apartment afternoon -- traffic, fridge] [bed]`
- **Scene 4 (Apartment, evening):** No AMBIENT. Line 202 partially covers.
- **Scene 5 (Apartment, night):** No AMBIENT. Needs: `[AMBIENT: apartment night -- dishes, water, quiet] [bed]`

---

## Episode 6: "The God-Keepers"

**Tag counts:**
- SFX tags: 18
- AMBIENT tags: 0
- Beat tags: 14 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: silence. Then -- the faintest crackle of fire. Not modern fire. Something older, ritualistic. Cedar burning]`

- "silence" is not producible. "Not modern fire. Something older, ritualistic" is direction.
- **Fix:**
  - `[Beat -- 1500ms]`
  - `[SFX: faint crackle of cedar fire -- old, ritualistic quality] [bed, fade-in]`

**Line 16:**
> `[SFX: the memory collapses. The sound cuts -- abrupt, like a recording snapped in half. Silence]`

- "the memory collapses" is narrative. "like a recording snapped in half" is simile. "Silence" is not producible.
- **Fix:**
  - `[SFX: abrupt hard cut -- all sound stops] [spot]`
  - `[Beat -- 800ms]`

**Line 52:**
> `[SFX: the shadows in the apartment bending hard toward Ash. The light from the window dimming. Kaya's desk lamp buzzing, straining]`

- "shadows bending" and "light dimming" are visual.
- **Fix:**
  - `[SFX: desk lamp buzzing, straining -- electrical flicker] [under]`
  - `[DIRECTION: Shadows bend hard toward Ash. The window light dims]`

Note: This tag is nearly identical to Ep3 line 232, Ep5 line 268. The shadow/light effect recurs throughout the series and needs a consistent SFX treatment. Recommend designing a single "Ash's power manifesting" SFX element (electrical buzz + low hum shift) and reusing it.

**Line 80:**
> `[SFX: silence. The bond between Rune and Ash -- still, for the first time. Held breath]`

- "silence" not producible. "still, for the first time. Held breath" is narrative.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[DIRECTION: The bond goes still. Held breath. The first time it has stopped humming]`

**Line 94:**
> `[SFX: Thessa stepping into the doorway. Not inside. Just across the threshold. Her voice drops -- quieter, more precise. This is not a threat. This is a diagnosis]`

- "Not inside. Just across the threshold" is stage direction. "Her voice drops -- quieter, more precise. This is not a threat. This is a diagnosis" is direction for the voice actor.
- **Fix:**
  - `[SFX: single footstep -- crossing a threshold] [spot]`
  - `[DIRECTION: Thessa steps just into the doorway. Not inside. Her voice drops. This is not a threat -- it's a diagnosis]`

**Line 106:**
> `[SFX: behind Rune -- stillness. Ash has gone completely silent. The shadows have stopped moving. The temperature has dropped]`

- "stillness" and "Ash has gone completely silent" are the absence of sound. "The shadows have stopped moving. The temperature has dropped" are visual/physical.
- **Fix:**
  - `[SFX: bond hum drops to near-silence] [spot]`
  - `[DIRECTION: Ash goes completely still. Shadows stop moving. The temperature drops]`

**Line 154:**
> `[SFX: nothing. The fridge. The clock. The silence where an answer should be]`

- "nothing" and "the silence where an answer should be" are narrative/conceptual.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[AMBIENT: apartment -- fridge, clock ticking] [bed]`

**Line 292:**
> `[SFX: Rune sitting down. Not on the couch. On the floor, against the opposite wall. The same height. The same dark]`

- "Not on the couch. On the floor, against the opposite wall. The same height. The same dark" is stage direction.
- **Fix:**
  - `[SFX: body settling onto floor, back against wall] [spot]`
  - `[DIRECTION: Rune sits on the floor against the opposite wall. Same height. Same dark]`

**Line 302:**
> `[SFX: the hum fades to near-silence. Then -- under it, barely audible -- the subsonic thrum. The city. The Meridian. Something old and vast and cracking, far below]`

- "The city. The Meridian. Something old and vast and cracking, far below" is narrative.
- **Fix:**
  - `[SFX: bond hum fades to near-silence] [fade-out]`
  - `[AMBIENT: subsonic thrum -- barely audible, deep beneath the city] [bed, fade-in]`

**Line 312:**
> `[SFX: the hum. The dark. The sound of something that will not break tonight]`

- "The dark" is not sound. "The sound of something that will not break tonight" is narrative.
- **Fix:**
  - `[AMBIENT: bond hum -- low, steady, resolving] [bed, fade-out over scene end]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (Memory fragment):** No AMBIENT. Minimal -- the cedar fire SFX serves. `[bed, brief]`
- **Scene 2 (Apartment doorway):** No AMBIENT. Needs: `[AMBIENT: apartment hallway -- fluorescent buzz] [bed]`
- **Scene 3 (Apartment, the cost):** No AMBIENT. Shares space with Scene 2.
- **Scene 4 (Apartment, after):** No AMBIENT. Needs: `[AMBIENT: apartment -- fridge, clock, the quiet after a confrontation] [bed]`
- **Scene 5 (Apartment, Kaya on phone):** No AMBIENT. Same apartment ambient continues.
- **Scene 6 (Apartment, deep night):** No AMBIENT. Needs: `[AMBIENT: apartment, 3 AM -- near-total silence, faint city, breathing] [bed]`

### Issue 6: Internal Monologue -- Special Case

**Line 12:**
> `ASH (not speaking to anyone -- surfacing, like a diver breaking water): There was a temple. There was a fire. There was --`

This is Ash's internal voice. If it should receive the bandpass + micro-echo treatment, it needs to be marked `ASH (inner monologue):`. If it's meant to be heard as spoken aloud (surfacing, half-conscious), it should be `ASH:` with a direction tag. Currently ambiguous. **Needs creative decision.**

---

## Episode 7: "The Meridian"

**Tag counts:**
- SFX tags: 18
- AMBIENT tags: 0
- Beat tags: 10 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: city traffic -- normal, steady. Then underneath it, a low resonance. Subsonic. Not a sound you hear so much as feel in your back teeth. Water pipes groaning somewhere distant. Then -- dogs barking. Multiple, from different directions, all at once. A chorus of alarm with no visible cause. Then they stop. All of them. At the same time]`

- "Not a sound you hear so much as feel in your back teeth" is narrative/direction. "A chorus of alarm with no visible cause" is narrative.
- **Fix:**
  - `[AMBIENT: city traffic -- normal, steady. Low subsonic resonance underneath. Distant water pipes groaning] [bed]`
  - `[SFX: dogs barking -- multiple, different directions, simultaneous. Then all stop at once] [spot]`

**Line 36:**
> `[SFX: car doors closing. Footsteps on pavement, then on grass -- except the grass sounds wrong. Dry. Brittle. Crunching underfoot like old paper]`

- "except the grass sounds wrong" is narrative/direction.
- **Fix:**
  - `[SFX: car doors closing] [spot]`
  - `[SFX: footsteps on pavement transitioning to dry, brittle grass -- crunching like old paper] [bridge]`

**Line 40:**
> `[SFX: they stop walking. Silence -- no birdsong, no wind through leaves. Dead air]`

- "Silence -- no birdsong, no wind through leaves. Dead air" describes an absence. It IS actually producible though -- the removal of expected ambient.
- **Fix:**
  - `[AMBIENT: dead grove -- total absence of natural sound. No birdsong, no wind. Dead air] [bed, hard-cut from previous]`

**Line 64:**
> `[SFX: a low hum -- not the subsonic thrum from before but something closer, more intimate. The sound of divine residue dissipating. The air shimmering]`

- "The sound of divine residue dissipating" is narrative concept. "The air shimmering" is visual.
- **Fix:**
  - `[SFX: a low hum -- close, intimate, different from the subsonic thrum. Wavering, dissipating quality] [under]`
  - `[DIRECTION: The god's power is still here. Leaking out of the ground. The air shimmers]`

**Line 258:**
> `[SFX: a heavy door opening -- metal, stiff hinges. The wind. The city at night from above -- distant traffic, a siren somewhere far, the white noise of a million lives happening at once. Vast. Open. The opposite of the apartment]`

- "the white noise of a million lives happening at once. Vast. Open. The opposite of the apartment" is narrative.
- **Fix:**
  - `[SFX: heavy metal door opening -- stiff hinges] [spot]`
  - `[AMBIENT: rooftop at night -- wind, vast open air, distant traffic, far siren, city white noise] [bed]`

**Line 266:**
> `[SFX: the wind. The city. The distance between the roof and the ground -- vertiginous, alive]`

- "The distance between the roof and the ground -- vertiginous, alive" is narrative/sensory direction.
- **Fix:**
  - `[AMBIENT: wind and city below -- open, high-elevation acoustic] [bed]` (continues from above)

**Line 316:**
> `[SFX: the wind fading. The rooftop quiet. Two sets of breathing. The bond humming between them -- not the wire anymore. Something warmer. Something with a pulse]`

- "not the wire anymore. Something warmer. Something with a pulse" is narrative.
- **Fix:**
  - `[SFX: wind fading. Two sets of breathing, close] [fade-out]`
  - `[SFX: bond hum -- warmer tone, with a subtle rhythmic pulse] [bed, fade-out over scene end]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (City, morning):** No AMBIENT. Line 10 partially covers.
- **Scene 2 (Dead grove):** No AMBIENT. Needs the dead-air ambient noted above.
- **Scene 3 (Apartment, afternoon):** No AMBIENT. Line 106 partially covers. Needs: `[AMBIENT: apartment afternoon -- fridge, muted traffic through glass] [bed]`
- **Scene 4 (Apartment, evening):** No AMBIENT. Same apartment.
- **Scene 5 (Apartment, night):** No AMBIENT. Line 214 partially covers.
- **Scene 6 (Rooftop):** No AMBIENT. Line 258 partially covers. Split needed.

---

## Episode 8: "Pulse"

**Tag counts:**
- SFX tags: 16
- AMBIENT tags: 0
- Beat tags: 10 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: the apartment. Morning. Coffee brewing -- the gurgle of a cheap drip machine. Pages turning in the other room. Not fast. Normal speed]`

- "the apartment. Morning" is setting/narrative.
- **Fix:**
  - `[AMBIENT: apartment morning -- coffee machine gurgling] [bed]`
  - `[SFX: pages turning in the other room -- normal speed] [under]`

**Line 184:**
> `[SFX: the bond -- a ripple. Not agitated. Searching. Like a hand reaching across a table in the dark]`

- "Not agitated. Searching. Like a hand reaching across a table in the dark" is narrative/metaphor.
- **Fix:**
  - `[SFX: bond hum -- a subtle ripple, searching quality] [under]`

**Line 212:**
> `[SFX: the shadows along the building wall bend. Not toward Rune. Toward something behind him]`

- Visual description.
- **Fix:**
  - `[DIRECTION: The shadows along the building wall bend -- not toward Rune. Toward something behind him]`
  - (No SFX needed -- this is purely visual)

**Line 216:**
> `[SFX: the shadows tightening. A sound like fabric pulled taut. Then -- footsteps behind Rune. Fast. Retreating]`

- "The shadows tightening" is visual. The fabric sound and footsteps are producible.
- **Fix:**
  - `[SFX: a low taut sound -- like fabric stretched tight. Footsteps behind Rune -- fast, retreating] [spot]`
  - `[DIRECTION: The shadows tighten around the stalker]`

**Line 240:**
> `[SFX: Ash pacing -- his footsteps tracing the circuit. Window, kitchen, bookshelf, window. The same path but faster. Tighter. The air warmer than it should be]`

- "Window, kitchen, bookshelf, window" and "The air warmer than it should be" are direction/narrative.
- **Fix:**
  - `[SFX: Ash pacing -- footsteps in a repeated circuit, getting faster] [bed]`
  - `[DIRECTION: The same path -- window, kitchen, bookshelf, window. Tighter. The air is warmer than it should be]`

**Line 300:**
> `[SFX: the wind. The city. The space between two people standing at the edge of something]`

- "The space between two people standing at the edge of something" is narrative.
- **Fix:**
  - `[AMBIENT: rooftop wind, city below] [bed]` (continuation)

### Issue 2: Vague/Unproducible SFX

**Line 212:** Shadows bending is not a sound. (Fixed above.)

### Issue 4: AMBIENT Coverage

- **Scene 1 (Apartment, morning):** No AMBIENT. Line 10 partially covers.
- **Scene 2 (Kitchen, lunch with Mika):** No AMBIENT. Needs: `[AMBIENT: apartment kitchen -- dishes, conversation atmosphere] [bed]`
- **Scene 3 (Apartment, afternoon):** No AMBIENT. Continues apartment bed.
- **Scene 4 (City street, evening):** No AMBIENT. Needs: `[AMBIENT: city street -- evening traffic, pedestrians, streetlights] [bed]`
- **Scene 5 (Apartment, night):** No AMBIENT. Line 240 partially covers.
- **Scene 6 (Rooftop):** No AMBIENT. Needs rooftop wind/city bed.

---

## Episode 9: "Fault"

**Tag counts:**
- SFX tags: 14
- AMBIENT tags: 0
- Beat tags: 16 (all untimed) -- highest beat count of any episode

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: the hiss of a recording. Ambient echo -- a lecture hall, empty. Then Kaya's voice, slightly tinny, the cadence of an academic performing knowledge]`

- "the cadence of an academic performing knowledge" is narrative/direction.
- **Fix:**
  - `[SFX: recording hiss. Ambient echo of an empty lecture hall] [bed]`
  - `[DIRECTION: Kaya's voice is slightly tinny -- the cadence of an academic performing knowledge]`

**Line 34:**
> `[SFX: Rune's alarm. The buzz of a phone on wood. His hand slapping it off. Then -- a cough. Dry, persistent, the kind that lives in your chest]`

- "the kind that lives in your chest" is narrative.
- **Fix:**
  - `[SFX: phone alarm buzzing on wood. Hand slapping it off. Dry, persistent cough] [spot]`

**Line 76:**
> `[SFX: a heavy wooden door opening. Kaya's office -- old, cluttered. The sound of books stacked too high, papers shifting. A window with city noise beyond it. Three people settling into chairs -- Rune, Ash, Kaya]`

- "old, cluttered" and "books stacked too high" are visual. "Three people settling into chairs -- Rune, Ash, Kaya" has unnecessary character attribution.
- **Fix:**
  - `[SFX: heavy wooden door opening] [spot]`
  - `[AMBIENT: Kaya's office -- papers shifting, city noise through window] [bed]`
  - `[SFX: three chairs being pulled out and sat in] [spot]`

**Line 110:**
> `[SFX: the office. Books. Dust. The weight of what's been said settling into the room]`

- "Books. Dust. The weight of what's been said settling into the room" -- none of this is producible sound.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[DIRECTION: The weight of the revelation settles into the room]`

**Line 132:**
> `[SFX: the shadows in the office sharpening. Books on the nearest shelf shifting -- not falling, tilting. The window glass humming]`

- "the shadows in the office sharpening" is visual. "not falling, tilting" is visual clarification.
- **Fix:**
  - `[SFX: books on shelf shifting, tilting. Window glass humming] [under]`
  - `[DIRECTION: The shadows in the office sharpen]`

**Line 174:**
> `[SFX: Rune standing. Jacket. The sound of someone who doesn't want to hear this but won't flinch from it]`

- "Jacket" is vague. "The sound of someone who doesn't want to hear this but won't flinch from it" is narrative.
- **Fix:**
  - `[SFX: chair pushing back. Jacket being pulled on] [spot]`

**Line 182:**
> `[SFX: the city. Late afternoon. Rune and Ash walking. Footsteps on pavement -- Rune's steady, Ash's harder, still carrying the fury from Kaya's office. Traffic. A bus passing. The normal sounds of a city that doesn't know its foundations are cracking]`

- "still carrying the fury from Kaya's office" is emotional direction. "The normal sounds of a city that doesn't know its foundations are cracking" is narrative.
- **Fix:**
  - `[AMBIENT: city street, late afternoon -- traffic, bus passing] [bed]`
  - `[SFX: two sets of footsteps on pavement -- one steady, one harder] [bridge]`

**Line 224:**
> `[SFX: the sidewalk. The city. Two people standing in the middle of a Thursday afternoon saying things that belong in the dark]`

- Entirely narrative. No producible sound described.
- **Fix:**
  - `[AMBIENT: city street continues] [bed]` (no change needed -- ambient continues from scene start)
  - `[DIRECTION: Two people standing still on a Thursday afternoon sidewalk, saying things that belong in the dark]`

**Line 276:**
> `[SFX: the doorway. The bedroom. The space between them -- ten feet and everything that hasn't been said in nine days]`

- Entirely narrative/spatial. No sound.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[DIRECTION: The doorway. The bedroom. Ten feet and everything unsaid between them]`

**Line 282:**
> `[SFX: silence. The apartment. The bond between them -- humming, raw, the frequency of two people standing on either side of a question that will determine if one of them lives or dies]`

- "silence" not producible. The narrative description is direction.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[SFX: bond hum -- raw, exposed] [under]`

**Line 296:**
> `[SFX: the bed. Two people. The maximum possible distance on a queen mattress. The bond between them -- not humming now. Settled. The note it's been searching for found]`

- Entirely narrative. "The bed" is not a sound. "The maximum possible distance on a queen mattress" is stage direction. "The note it's been searching for found" is narrative.
- **Fix:**
  - `[SFX: mattress springs shifting under new weight -- far side of the bed] [spot]`
  - `[SFX: bond hum settling into a resolved, steady tone] [bed]`
  - `[DIRECTION: He sits on the far edge. Maximum distance. The bond settles into the note it's been searching for]`

**Line 304:**
> `[SFX: the bond. Steady. Warm. The sound of a choice made without a single word]`

- "The sound of a choice made without a single word" is narrative.
- **Fix:**
  - `[SFX: bond hum -- steady, warm] [bed]`

**Line 318:**
> `[SFX: the clock. The breathing. The bond between them -- the note it makes not a hum anymore but a pulse. Two rhythms learning to sync]`

- "the note it makes not a hum anymore but a pulse. Two rhythms learning to sync" is narrative/direction for the sound designer.
- **Fix:**
  - `[AMBIENT: clock ticking. Two sets of breathing. Bond tone -- rhythmic, pulse-like, two rhythms approaching sync] [bed, fade-out over scene end]`

### Issue 2: Vague/Unproducible SFX

**Line 110:** "Books. Dust. The weight of what's been said" -- none are sounds. (Fixed above.)
**Line 224:** "The sidewalk. The city." -- not specific SFX. (Fixed above.)
**Line 276:** "The doorway. The bedroom. The space between them." -- not sounds. (Fixed above.)

### Issue 5: Beat Consistency

This episode has 16 beats -- the most of any episode. Several clusters occur where 2-3 beats appear within a few lines (lines 118-148 has 5 beats in 30 lines). This density risks making the pacing draggy. Recommend:
- Lines 119-120: Combine into one `[Long beat -- 1500ms]`
- Lines 143-148: Keep both but differentiate timing: `[Beat -- 800ms]` then `[Long beat -- 1500ms]`
- Lines 283-285: `[Long beat -- 2500ms]` (single heavy beat, not two separate ones)

---

## Episode 10: "The First God"

**Tag counts:**
- SFX tags: 22
- AMBIENT tags: 0
- Beat tags: 10 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: the subsonic thrum -- louder than it's ever been. Not felt in the teeth anymore. Felt in the floor, the walls, the bones. Then cracking. Deep, structural. The sound of bedrock splitting far below the surface. A groan that comes from the earth itself]`

- "Not felt in the teeth anymore. Felt in the floor, the walls, the bones" is direction. "A groan that comes from the earth itself" has "comes from the earth itself" as narrative.
- **Fix:**
  - `[SFX: subsonic thrum -- massive, louder than ever. Deep structural cracking. Bedrock splitting far below. Geological groan] [bed, fade-in]`
  - `[DIRECTION: Not felt in the teeth anymore -- in the floor, the walls, the bones]`

**Line 14:**
> `[SFX: the apartment. Predawn stillness. Then -- a voice. Ancient, vast, fading. Like a recording played through stone: "We were here first..."]`

- "the apartment. Predawn stillness" should be AMBIENT. "Like a recording played through stone" is direction for the voice processing.
- **Fix:**
  - `[AMBIENT: apartment, predawn -- stillness] [bed]`
  - `[SFX: ancient voice, vast and fading, reverberating through stone: "We were here first..."] [spot]`
  - `[DIRECTION: Process the voice like a recording played through stone -- filtered, old, geological]`

**Line 18:**
> `[SFX: silence. Total. The fridge stops. The traffic stops. The city holds its breath]`

- "silence. Total" and "The city holds its breath" are narrative. The stopping of ambient IS a producible instruction though.
- **Fix:**
  - `[SFX: all ambient sound stops -- fridge, traffic, everything. Hard cut to total silence] [spot]`
  - `[Beat -- 1500ms]`

**Line 54:**
> `[SFX: the scene -- sirens layered, distant and close. People shouting. The hiss of a ruptured water main. Concrete grinding. A sinkhole has opened in the park, and the buildings along the east side are listing, their foundations compromised. Glass breaking somewhere. A child crying. The organized chaos of first responders]`

- "A sinkhole has opened in the park, and the buildings along the east side are listing, their foundations compromised" is visual/narrative. "The organized chaos of first responders" is narrative.
- **Fix:**
  - `[AMBIENT: disaster site -- layered sirens (near and far), people shouting, ruptured water main hiss, concrete grinding, glass breaking, child crying, first responder activity] [bed]`

**Line 100:**
> `[SFX: the woman crying out -- distant but clear. The child whimpering. Metal groaning as the building shifts another degree]`

- "another degree" is measurement/narrative.
- **Fix:**
  - `[SFX: woman crying out (distant). Child whimpering. Metal groaning -- building shifting] [under]`

**Line 104:**
> `[SFX: a sound like heavy fabric unfurling. Shadows moving with physical weight. Then -- the creak of metal. The fire escape, the rusted section that pulled away from the wall, bending. Not falling. Bending back. The bolts finding their holes. The metal groaning into place and holding]`

- "Shadows moving with physical weight" is visual. "Not falling. Bending back. The bolts finding their holes" is visual/narrative. "and holding" is narrative.
- **Fix:**
  - `[SFX: heavy fabric-unfurling sound. Metal creaking -- fire escape bending, bolts grinding back into place, metal groaning and settling] [spot]`
  - `[DIRECTION: The shadows move with physical weight. The fire escape bends back into place -- not falling, returning. Ash is holding it]`

**Line 142:**
> `[SFX: the bond -- a surge. Not slow. A wall of sensation. Hunger, vast and mindless, the pull of divine power draining from the earth below the park]`

- "Not slow. A wall of sensation. Hunger, vast and mindless, the pull of divine power draining from the earth below the park" is narrative/internal.
- **Fix:**
  - `[SFX: bond surge -- massive, sudden, overwhelming] [spot]`
  - `[DIRECTION: Hunger, vast and mindless. The pull of divine power draining from the earth below]`

**Line 154:**
> `[SFX: the bond roaring between them. The hunger a physical force, a sound like standing next to a furnace with the door open]`

- "The hunger a physical force" is narrative. "like standing next to a furnace with the door open" is simile/creative direction.
- **Fix:**
  - `[SFX: bond roaring -- furnace-like intensity, open-flame quality] [under]`

**Line 298:**
> `[SFX: the contact. Fabric shifting. The bond responding -- a flare, but soft this time. A warmth that spreads instead of spikes]`

- "A warmth that spreads instead of spikes" is narrative/direction.
- **Fix:**
  - `[SFX: fabric shifting. Bond tone -- soft flare, warm, spreading] [under]`

**Line 304:**
> `[SFX: the smallest shift. Ash leaning. Not collapsing. Not falling. An inch. Maybe less. His weight tipping toward the contact like someone remembering how gravity works after a long time in the air]`

- Entirely narrative/visual. The producible sound is minimal.
- **Fix:**
  - `[SFX: the faintest shift of weight -- fabric, a breath] [spot]`
  - `[DIRECTION: Ash leans in. An inch. Maybe less. Like someone remembering how gravity works]`

**Line 320:**
> `[SFX: the nightmare sound -- brief. A flash. The burning temple. A hand reaching. Then gone. Cut to silence]`

- "A flash. A hand reaching" are visual. "Cut to silence" is a mixing instruction.
- **Fix:**
  - `[SFX: brief flash of nightmare sound -- fire roar, chanting, abruptly cut] [spot]`
  - `[Beat -- 800ms]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (City, predawn):** No AMBIENT. Needs: `[AMBIENT: apartment predawn] [bed]` then hard-cut to silence.
- **Scene 2 (Central Park disaster):** No AMBIENT. Line 54 partially covers. Split needed.
- **Scene 3 (Disaster site, mid-morning):** No AMBIENT. Continues disaster bed, lower intensity.
- **Scene 4 (Near sinkhole):** No AMBIENT. Needs: `[AMBIENT: sinkhole proximity -- dissipating divine energy hum, dust, distant activity] [bed, crossfade]`
- **Scene 5 (Disaster site, afternoon):** No AMBIENT. Continues site, winding down.
- **Scene 6 (Apartment, night):** No AMBIENT. Needs: `[AMBIENT: apartment night -- wounded city outside, quieter than usual] [bed]`

---

## Episode 11: "Smoke Signals"

**Tag counts:**
- SFX tags: 12
- AMBIENT tags: 0
- Beat tags: 10 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: the apartment. Morning. Coffee brewing. But the soundscape is different now -- fuller. A knock at the door. Kaya's voice in the hallway. Papers being spread on the kitchen table. Mika arriving ten minutes later with takeout bags and the blunt efficiency of someone who has decided to be helpful and will not be stopped]`

- "the apartment. Morning" is setting. "But the soundscape is different now -- fuller" is meta-narrative about the sound design. "the blunt efficiency of someone who has decided to be helpful and will not be stopped" is narrative.
- **Fix:**
  - `[AMBIENT: apartment morning -- coffee brewing, fuller than before, multiple people] [bed]`
  - `[SFX: knock at door. Hallway voices. Papers spreading on table. Another arrival -- takeout bags rustling] [spot sequence]`

**Line 86:**
> `[SFX: a beat. Then Ash -- a sound that might be a breath leaving through his nose. Not a laugh. The predecessor of one]`

- "a beat" is a timing tag misplaced inside SFX. "Not a laugh. The predecessor of one" is narrative.
- **Fix:**
  - `[Beat -- 800ms]`
  - `[SFX: Ash -- a sharp exhale through the nose. Almost a laugh] [spot]`

**Line 98:**
> `[SFX: Ash's finger stopping on the map. The stillness of someone who has arrived at the answer they didn't want]`

- "The stillness of someone who has arrived at the answer they didn't want" is narrative.
- **Fix:**
  - `[SFX: finger tapping map, then stopping] [spot]`
  - `[DIRECTION: The stillness of someone who has arrived at the answer they didn't want]`

**Line 154:**
> `[SFX: skin on skin. Brief. Accidental. The sound of two hands occupying the same space over a map of the end of the world]`

- "The sound of two hands occupying the same space over a map of the end of the world" is narrative.
- **Fix:**
  - `[SFX: brief skin-on-skin contact -- hands brushing] [spot]`

**Line 158:**
> `[SFX: the bond -- a spark. Not a surge. A warmth that blooms from the point of contact and spreads through the wrist, the forearm, the chest. The bond registering something it's been waiting for]`

- Entirely narrative/internal. The spark can be a producible tone, but the rest is direction.
- **Fix:**
  - `[SFX: bond tone -- a soft spark, warm, blooming] [under]`
  - `[DIRECTION: The warmth spreads from the point of contact through the wrist, the forearm, the chest. The bond registering something it's been waiting for]`

**Line 170:**
> `[SFX: Ash's hand still. Not pulling away. The bond humming between them -- warm, searching, the frequency of two people pretending a coincidence isn't a confession]`

- "Not pulling away" is stage direction. "the frequency of two people pretending a coincidence isn't a confession" is narrative.
- **Fix:**
  - `[SFX: bond hum -- warm, searching] [under]`
  - `[DIRECTION: His hand is still. Not pulling away. Two people pretending a coincidence isn't a confession]`

**Line 258:**
> `[SFX: the faucet turning off. The kitchen going silent. The bond humming through the wall -- warm, steady, the pulse of someone reading in the next room who has no idea what's happening in the kitchen. Or who knows exactly what's happening and is giving Rune the space to arrive at it on his own]`

- "The kitchen going silent" is narrative. Everything after the first sentence is narrative.
- **Fix:**
  - `[SFX: faucet turning off] [spot]`
  - `[SFX: bond hum through the wall -- warm, steady, rhythmic] [bed]`
  - `[DIRECTION: Someone reading in the next room who has no idea -- or who knows exactly and is giving Rune space]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (Apartment, morning, full house):** No AMBIENT. Line 10 partially covers. Split needed.
- **Scene 2 (Kitchen, map work):** No AMBIENT. Continues apartment bed.
- **Scene 3 (Kitchen, later, just Rune and Ash):** No AMBIENT. Needs: `[AMBIENT: apartment, late afternoon -- quieter now, just two people, muted traffic] [bed, crossfade]`
- **Scene 4 (Apartment, evening):** No AMBIENT. Same apartment, evening shift.
- **Scene 5 (Apartment, night):** No AMBIENT. Needs: `[AMBIENT: apartment, midnight -- faucet drip, clock, deep quiet] [bed]`

---

## Episode 12: "Sacred Ground"

**Tag counts:**
- SFX tags: 16
- AMBIENT tags: 0
- Beat tags: 8 (all untimed)

### Issue 1: Hybrid Tags (CRITICAL)

**Line 10:**
> `[SFX: footsteps on cobblestone. The old quarter at night -- narrow streets, old stone, the echo of walls close together. A church bell somewhere, muffled. The city sounds farther away here, older]`

- "narrow streets, old stone, the echo of walls close together" and "The city sounds farther away here, older" are direction/narrative mixed with producible elements.
- **Fix:**
  - `[SFX: footsteps on cobblestone] [bridge]`
  - `[AMBIENT: old quarter at night -- close-walled echo, muffled church bell, distant city sounds] [bed]`

**Line 30:**
> `[SFX: the chamber. A vast, echoing space -- their footsteps suddenly distant, the ceiling high enough to swallow sound. The drip amplified. A low hum in the stone -- the Meridian, felt more than heard]`

- "the ceiling high enough to swallow sound" is narrative. "the Meridian, felt more than heard" is direction.
- **Fix:**
  - `[AMBIENT: underground chamber -- vast natural reverb, amplified water drip, low hum in stone] [bed]`
  - `[DIRECTION: The ceiling is high enough to swallow sound. The Meridian hum is felt more than heard]`

**Line 44:**
> `[SFX: Ash moving through the chamber. His footsteps different here -- slower, pulled, the way he walked toward the dead grove. The shadows around him moving with purpose, reaching into corners Rune's phone light can't find]`

- "the way he walked toward the dead grove" is narrative reference. "reaching into corners Rune's phone light can't find" is visual.
- **Fix:**
  - `[SFX: Ash's footsteps through the chamber -- slow, drawn, deliberate] [bridge]`
  - `[DIRECTION: The same pull as the dead grove. Shadows move with purpose around him, reaching into corners beyond the phone light]`

**Line 100:**
> `[SFX: the moment his foot crosses the circle's edge, the bond detonates. Not hostile. Not painful. But massive -- a wave of sensation that knocks Rune back a step. The hum in the chamber rising to a vibration you feel in your teeth]`

- "Not hostile. Not painful. But massive -- a wave of sensation that knocks Rune back a step" is narrative/direction.
- **Fix:**
  - `[SFX: bond detonation -- massive surge. Chamber hum rises to teeth-vibrating intensity. Footstep stumbling back] [spot]`
  - `[DIRECTION: Not hostile. Not painful. But massive. Rune staggers back a step from the wave]`

**Line 104:**
> `[SFX: the memory -- fire. Roaring. A temple that's real, not a dream. Chanting in a language that's older than the one Kaya reads. Figures in white -- not god-keepers, not yet, the predecessors. And in the center, on a stone altar --]`

- "A temple that's real, not a dream" and "not god-keepers, not yet, the predecessors. And in the center, on a stone altar --" are narrative.
- **Fix:**
  - `[SFX: memory flash -- roaring fire, real stone temple acoustics, ancient chanting (older language than previous dream sequences)] [bed]`
  - `[DIRECTION: This is real, not a dream. Figures in white -- the predecessors of the god-keepers. A stone altar in the center]`

**Line 108:**
> `[SFX: the memory snapping. Violent. A sound like glass breaking]`

- "Violent" is direction. The glass-breaking sound is producible.
- **Fix:**
  - `[SFX: memory snap -- violent, like glass shattering. All sound cuts] [spot]`

**Line 228:**
> `[SFX: his hand finding Rune's. The contact. Deliberate. Not a brush. Not an accident. Fingers closing around fingers. Skin to skin. The bond flaring -- warm, certain, a note that resolves]`

- "Deliberate. Not a brush. Not an accident" is direction. "a note that resolves" is musical metaphor.
- **Fix:**
  - `[SFX: fingers closing around fingers -- skin to skin. Bond tone flares warm, resolving] [under]`
  - `[DIRECTION: Deliberate. Not a brush. Not an accident. A choice]`

**Line 284:**
> `[SFX: the apartment. The words. The way they land -- quiet, precise, heavy as the stone floor of a chamber carved a millennium ago]`

- Entirely narrative. No producible sound.
- **Fix:**
  - `[Long beat -- 2500ms]`
  - `[DIRECTION: The words land -- quiet, precise, heavy as the stone floor of the chamber]`

**Line 294:**
> `[SFX: a beat. Then Ash turning toward the couch. The familiar path. And Rune toward the bedroom. The familiar path. The same apartment, the same rooms, the same distance between the couch and the bed. But the bond between them is different tonight. Not a chain. Not a wire. Not even a current. Something that has found its frequency and is ringing with it. Clear and sustained and new]`

- "a beat" is a timing instruction. Most of this is narrative.
- **Fix:**
  - `[Beat -- 1500ms]`
  - `[SFX: footsteps separating -- one toward the couch, one toward the bedroom] [spot]`
  - `[SFX: bond tone -- clear, sustained, new frequency. Resolved] [bed, fade-out slowly]`
  - `[DIRECTION: The same apartment, same rooms, same distance. But the bond is different tonight. Not a chain, not a wire. Something that has found its frequency]`

**Line 310:**
> `[SFX: the bond. Two rhythms. Closer now. Not synced. But close. Getting closer]`

- "Not synced. But close. Getting closer" is narrative/direction.
- **Fix:**
  - `[SFX: bond tone -- two rhythmic pulses, approaching sync but not yet matching] [bed]`

**Line 316:**
> `[SFX: the dawn through the curtains. The apartment. The bond humming. Two people awake in the same space, choosing to be there. The quiet of a new beginning disguised as an ordinary morning]`

- Entirely narrative. "The dawn through the curtains" is visual.
- **Fix:**
  - `[AMBIENT: apartment at dawn -- early light atmosphere, city waking, bond hum] [bed, fade-out over episode end]`
  - `[DIRECTION: Two people awake in the same space, choosing to be there. The quiet of a new beginning disguised as an ordinary morning]`

### Issue 4: AMBIENT Coverage

- **Scene 1 (Old quarter, descent):** No AMBIENT. Line 10 partially covers. Split needed. Needs crossfade from street to underground.
- **Scene 2 (Chamber):** No AMBIENT. Line 30 partially covers. Split needed.
- **Scene 3 (Tunnels, ascending):** No AMBIENT. Needs: `[AMBIENT: tunnel stairs -- echoing footsteps, dripping, enclosed] [bed, crossfade from chamber]`
- **Scene 4 (Walk home, dawn):** No AMBIENT. Needs: `[AMBIENT: city at dawn -- grey-gold quiet, distant delivery truck, bird testing, minimal traffic] [bed]`
- **Scene 5 (Apartment, dawn):** No AMBIENT. Line 316 partially covers.

---

# Summary Table

## Tag Counts Per Episode

| Episode | SFX | AMBIENT | Beats | Inner Monologue Lines |
|---------|-----|---------|-------|----------------------|
| Ep01 | 18 | 0 | 6 | 14 |
| Ep02 | 20 | 0 | 8 | 12 |
| Ep03 | 22 | 0 | 10 | 9 |
| Ep04 | 20 | 0 | 8 | 14 |
| Ep05 | 22 | 0 | 12 | 10 |
| Ep06 | 18 | 0 | 14 | 6 |
| Ep07 | 18 | 0 | 10 | 15 |
| Ep08 | 16 | 0 | 10 | 13 |
| Ep09 | 14 | 0 | 16 | 10 |
| Ep10 | 22 | 0 | 10 | 14 |
| Ep11 | 12 | 0 | 10 | 12 |
| Ep12 | 16 | 0 | 8 | 8 |
| **TOTAL** | **218** | **0** | **122** | **137** |

## Issue Counts Per Episode

| Episode | Hybrid Tags | Vague/Unproducible | Missing AMBIENT | Missing Layering | Untimed Beats | IM Issues |
|---------|------------|-------------------|-----------------|------------------|---------------|-----------|
| Ep01 | 11 | 1 | 5 scenes | ALL (18 tags) | 6 | 0 |
| Ep02 | 10 | 1 | 5 scenes | ALL (20 tags) | 8 | 0 |
| Ep03 | 13 | 0 | 5 scenes | ALL (22 tags) | 10 | 0 |
| Ep04 | 10 | 0 | 6 scenes | ALL (20 tags) | 8 | 0 |
| Ep05 | 9 | 0 | 5 scenes | ALL (22 tags) | 12 | 0 |
| Ep06 | 10 | 0 | 6 scenes | ALL (18 tags) | 14 | 1 (Ash ambiguous) |
| Ep07 | 7 | 0 | 6 scenes | ALL (18 tags) | 10 | 0 |
| Ep08 | 6 | 1 | 6 scenes | ALL (16 tags) | 10 | 0 |
| Ep09 | 11 | 3 | 4 scenes | ALL (14 tags) | 16 | 0 |
| Ep10 | 10 | 0 | 6 scenes | ALL (22 tags) | 10 | 0 |
| Ep11 | 7 | 0 | 5 scenes | ALL (12 tags) | 10 | 0 |
| Ep12 | 10 | 0 | 5 scenes | ALL (16 tags) | 8 | 0 |
| **TOTAL** | **114** | **6** | **64 scenes** | **ALL 218 tags** | **122** | **1** |

## Overall Patterns to Fix

### 1. Systemic: Narrative embedded in SFX tags (114 instances)
The single largest issue. The scripts are written in a literary style where SFX tags function as prose -- describing visuals, emotions, metaphors, and narrative context alongside producible sounds. **Every SFX tag needs a separation pass** to split producible audio from direction/narrative.

### 2. Systemic: Zero AMBIENT tags (64 scenes untagged)
No scene in any episode has a proper `[AMBIENT:]` tag. Environmental soundscapes are currently inside `[SFX:]` tags, making it impossible for the assembler to distinguish one-shot effects from continuous background layers. Every scene needs an ambient bed established at its head.

### 3. Systemic: Zero layering instructions (218 tags)
No SFX tag includes `[spot]`, `[under]`, `[bed]`, `[bridge]`, `[fade-in]`, or `[fade-out]` notation. The assembler has no guidance on placement relative to dialogue.

### 4. Systemic: All 122 beats are untimed
Every beat is written as lowercase `[beat]` with no millisecond duration. The convention specifies `[Beat -- Xms]` and `[Long beat -- Xms]`.

### 5. Recurring: The bond hum has no consistent SFX design language
The bond hum appears in virtually every scene across all 12 episodes with wildly varying descriptions: "steady," "agitated," "raw," "warm," "searching," "pulsing," "roaring," "settled." This needs a **sound design palette** -- a set of bond hum variants (neutral, agitated, warm, surge, settled) that can be referenced by name rather than re-described each time.

### 6. Recurring: Ash's shadow/power manifestation has no consistent SFX
Shadows bending, lamps flickering, temperature changes -- these appear in Ep2, Ep3, Ep5, Ep6, Ep8, Ep9, Ep10, Ep12. The visual elements (shadows, light changes) need to be moved to `[DIRECTION:]` tags, and the producible elements (lamp buzz, electrical strain) need a consistent treatment.

### 7. Recurring: "Silence" used as SFX
The word "silence" appears inside SFX tags at least 10 times across the series. Silence is not a producible sound effect -- it is either a beat (timed pause) or an ambient instruction (removal of background sound).

### 8. Minor: Internal monologue marking is clean
`RUNE (inner monologue):` is used consistently across all 137 inner monologue lines in 12 episodes. The only issue is the Ep6 Ash line that needs a creative decision on whether it receives bandpass processing. The guide's example format (`RUNE (INTERNAL):`) differs from the script format (`RUNE (inner monologue):`); recommend updating the guide to match the scripts.

### 9. Recommendation: Crossfade map
Multiple episodes have scene transitions that shift location (apartment to car, street to building interior, surface to underground). None specify whether the ambient should hard-cut or crossfade. Recommend a crossfade map for each episode specifying transition type at every scene boundary.

---

*End of audit. 218 SFX tags reviewed across 12 episodes. 114 hybrid tags flagged for splitting. 64 scenes missing AMBIENT coverage. All 218 tags missing layering instructions. All 122 beats missing timing values.*
