# SFX & Audio Tag Audit: Episodes 13-22

**Show:** Vow of Smoke
**Auditor:** Automated pass
**Date:** 2026-03-06
**Scope:** All `[SFX:]`, `[AMBIENT:]`, `[Beat]`, `[Silence]`, `[DIRECTION:]` tags in scripts ep13 through ep22
**Comparison baseline:** SFX-AUDIT-01-12.md conventions

---

## Executive Summary

Episodes 13-22 were written with production conventions active. The systemic failures from eps 1-12 (no AMBIENT tags, no layering, all beats untimed, rampant hybrid SFX) are **largely resolved**. Every episode has AMBIENT tags, every SFX tag has layering instructions, beats are timed, and DIRECTION tags are used to separate narrative from producible sound. The remaining issues are:

1. **Narrative bleed in SFX tags** -- significantly reduced but not eliminated. The most common pattern is "The sound of [narrative metaphor]" appended to otherwise clean tags.
2. **"Not a sound" declarations inside SFX tags** -- 5 instances where the tag literally states it is not a sound.
3. **"Silence" embedded in SFX tags** -- 20 instances where silence/absence is described as a sound effect.
4. **Footstep layering logic errors** -- isolated footsteps that precede dialogue are tagged `[spot]` when they should be `[bridge]` or `[under]`.
5. **Expanded bond-hum vocabulary** -- eps 13-22 introduce `bond-hum-steady`, `bond-hum-alert`, and `bond-hum-dissonant` beyond the established vocabulary. These are well-used and should be added to the standard lexicon.
6. **New sonic elements need production specs** -- divine voices, ritual chanting, the summoner's distorted voice, and the Kindling's harvested power all need audio design specifications.

---

## Tag Convention Reference (Updated for Eps 13-22)

| Tag | Purpose | Status in 13-22 |
|-----|---------|----------------|
| `[SFX: ...]` | Producible sound effects only | Present in all eps; some narrative bleed |
| `[AMBIENT: ...]` | Continuous background track | Present in all eps; good coverage |
| `[DIRECTION: ...]` | Narrative/emotional context (NOT audio) | Present in 8/10 eps; absent in ep21, ep22 |
| `[Beat -- Xms]` | Timed pauses | All timed; 0 untimed beats |
| `[Silence -- Xms]` | Extended timed pauses | Used consistently; new format from ep13 |

---

## Global Issues

### 1. Beat Timing: RESOLVED

All beats across eps 13-22 use the `[Beat -- Xms]` or `[Silence -- Xms]` format with explicit durations. Zero untimed `[beat]` tags found. The timing tiers from the ep 1-12 audit are followed:
- `[Beat -- 400ms]` for breath/micro-pause
- `[Beat -- 800ms]` for thought/reaction
- `[Silence -- 1500ms]` for emotional weight
- `[Silence -- 2500ms]` for devastating moments

**One note:** The `[Silence -- Xms]` tag is new -- eps 1-12 only specified `[Beat]` and `[Long beat]`. The new format works well and should be adopted as standard. Recommend documenting the distinction: `[Beat]` for character-driven pauses, `[Silence]` for environmental/atmospheric holds.

### 2. AMBIENT Coverage: LARGELY RESOLVED

52 AMBIENT tags across 10 episodes. Every scene has an opening AMBIENT tag. Crossfades are marked at location transitions (`[bed, crossfade]`). This is a complete reversal of the ep 1-12 state.

**Remaining gap:** Mid-scene location shifts occasionally lack a new AMBIENT. Flagged per-episode below.

### 3. Layering Instructions: LARGELY RESOLVED

494 of 496 SFX tags include layering notation. Two tags are missing it:
- Ep20 line 378: `[SFX: hard cut -- the ambient drops. Complete silence. Then:]` -- This is a mixing instruction, not an SFX.
- Ep21 line 242: `[SFX: Rune sitting -- the couch...]` -- Missing layering tag; also contains narrative.

### 4. Internal Monologue: CONSISTENT

197 inner monologue lines across 10 episodes. All use `RUNE (inner monologue):` format. No variants (`RUNE (INTERNAL):`, `RUNE (inner voice):`, etc.). No other characters receive inner monologue marking, which is consistent with eps 1-12.

### 5. Bond Vocabulary: Expanded

The standardized bond-hum vocabulary from eps 1-12 has been expanded:

| Term | Established 1-12 | New in 13-22 | Usage |
|------|:-:|:-:|-------|
| bond-hum-neutral | Yes | -- | Baseline, resting state |
| bond-hum-agitated | Yes | -- | Distress, hunger, conflict |
| bond-hum-warm | Yes | -- | Connection, care, intimacy |
| bond-hum-surge | Yes | -- | Acute spikes, anchoring, the kiss |
| bond-hum-settled | Yes | -- | Post-crisis calm, resolution |
| bond-hum-steady | -- | Yes (ep21) | Post-aqueduct new normal |
| bond-hum-alert | -- | Yes (ep22) | Threat-scanning mode |
| bond-hum-dissonant | -- | Yes (ep21) | Post-summoner-call fracture |

**Recommendation:** Add `bond-hum-steady`, `bond-hum-alert`, and `bond-hum-dissonant` to the official sonic vocabulary. All three are well-deployed and fill real gaps.

---

## Recurring Issue: Narrative Metaphor in SFX Tags

This is the most prevalent remaining problem. The pattern is: a producible SFX description followed by "The sound of [metaphor]" or "The frequency of [narrative description]". Examples across the run:

| Episode | Line | Offending Phrase |
|---------|------|-----------------|
| 13 | 146 | "The sound of someone who has made a decision" |
| 13 | 238 | "The silence between two people who understand grief differently" |
| 14 | 297 | "The sound of something vast and purposeful rearranging itself" |
| 16 | 228 | "The sound of a man holding something instead of answering" |
| 16 | 294 | "The word landing in the room -- small, plain, enormous" |
| 16 | 326 | "The sound of someone genuinely falling asleep for the first time in weeks" |
| 17 | 146 | "The sound of a sister who sees everything" |
| 17 | 220 | "The silence of a sentence that has emptied the room" |
| 18 | 218 | "The sound of a circuit completing" |
| 19 | 70 | "The word landing like a hand on a chest" |
| 19 | 354 | "The sound of two people who are past the point of no return" |
| 20 | 74 | "The sound of awe and fear" |
| 20 | 108 | "The sound of separation made permanent" |
| 20 | 150 | "The sound of a river that has been flowing for four thousand years and is very tired" |
| 20 | 240 | "The sound of authority deciding to trust" |
| 20 | 336 | "The sound of a team reassembling after near-destruction" |
| 21 | 22 | "running beneath everything like a second circulatory system" |
| 21 | 216 | "The sound of a shared thing suddenly suspect" |
| 21 | 252 | "The sound of someone leaving not because they're angry" |
| 21 | 440 | "produce something that sounds like a person who might, in another life, know how to smile" |
| 22 | 12 | "Paramedic mode engaging like a switch being thrown" |
| 22 | 234 | "The sound of a foundation being replaced beneath a standing structure" |
| 22 | 310 | "carrying the weight of the new information like a river carrying snowmelt" |

**Fix pattern:** In each case, the narrative portion should be moved to a `[DIRECTION:]` tag. The producible sound (the bond-hum variant, the exhale, the footsteps) remains in `[SFX:]`.

**Example fix (ep20 line 150):**
- **Current:** `[SFX: the aqueduct god -- water given voice. Not human speech but the impression of speech. The sound of a river that has been flowing for four thousand years and is very tired. Echo, reverb, layered] [spot]`
- **Fix:**
  - `[SFX: the aqueduct god -- water given voice. Deep reverb, echo, layered harmonic. Not human speech -- a frequency, oscillating] [spot]`
  - `[DIRECTION: The impression of a river that has been flowing for four thousand years and is very tired]`

---

## Recurring Issue: "Not a Sound" Inside SFX Tags

Five SFX tags explicitly state they are not sounds:

| Episode | Line | Tag |
|---------|------|-----|
| 15 | 126 | `[SFX: Ash's eyes clearing -- not a sound, but the bond tone shifts...]` |
| 18 | 52 | `[SFX: Rune's vision -- a sudden lurch. Not a sound but the bond-hum-surge...]` |
| 19 | 286 | `[SFX: Ash's gaze -- not a sound, but the bond transmitting something...]` |
| 20 | 78 | `[SFX: the aqueduct god -- a presence. Not a sound exactly, but the water responding...]` |
| 21 | 54 | `[SFX: Mika's look -- not a sound, but the pause...]` |

**Fix pattern:** Split each into a producible SFX (the bond tone shift, the hum-surge) and a DIRECTION tag for the non-sonic event (the gaze, the vision, the look).

**Example fix (ep15 line 126):**
- **Current:** `[SFX: Ash's eyes clearing -- not a sound, but the bond tone shifts. The hunger frequency drops. What replaces it is Ash -- not the god-eater, the person] [under]`
- **Fix:**
  - `[SFX: bond tone shifting -- hunger frequency dropping, replaced by a warmer, human register] [under]`
  - `[DIRECTION: Ash's eyes clearing. What's behind them is not the god-eater. It's the person]`

---

## Recurring Issue: Silence/Absence as SFX

Approximately 20 SFX tags describe silence, absence, or non-events as sound effects. Categories:

**A. Character silence as SFX (7 instances):**
- Ep14 line 60: `[SFX: Ash's silence -- not hostile. Considering]`
- Ep21 line 234: `[SFX: Kaya's silence -- the one that means the answer is the thing he's afraid of]`
- Ep21 line 376: `[SFX: Ash -- the silence that means the argument has hit something]`
- Ep22 line 130: `[SFX: Ash's silence -- long enough to be its own statement]`
- Ep22 line 188: `[SFX: Thessa's silence -- the kind that means she is hearing something]`
- Ep22 line 290: `[SFX: the room -- the silence of five people...]`
- Ep21 line 248: `[SFX: Ash at the window -- not moving. The shadows at his feet still. The temperature normalizing. The silence of someone...]`

**Fix:** These should all be `[Silence -- Xms]` + `[DIRECTION:]` for the character context.

**B. Narrative silence embedded in SFX (3+ instances):**
- Ep13 line 238: `[SFX: window traffic. Radiator. The silence between two people who understand grief differently]`
- Ep17 line 220: `[SFX: bond -- everything stops. The hum, the ambient, the traffic, the radiator. The silence of a sentence...]`

**Fix:** The producible elements stay in SFX; the narrative description of silence moves to DIRECTION.

---

# Per-Episode Audit

---

## Episode 13: "Vital Signs"

**Tag counts:** SFX: 38 | AMBIENT: 4 | Beat: 10 (all timed) | Silence: 5 | DIRECTION: 3

### Hybrid SFX (Moderate)

| Line | Tag (abbreviated) | Issue | Fix |
|------|-------------------|-------|-----|
| 38 | `Mika's hand on his arm -- firm, clinical grip. Assessing` | "Assessing" is direction | Move "Assessing" to DIRECTION |
| 52 | `Mika exhaling -- controlled, the sound of someone choosing not to yell` | "choosing not to yell" is narrative | Move to DIRECTION |
| 114 | `Rune gesturing -- sleeve pulling back. The bruises visible` | "The bruises visible" is visual | Move to DIRECTION |
| 146 | `Mika picking up her coffee... The sound of someone who has made a decision` | Narrative | Move "The sound of..." to DIRECTION |
| 238 | `window traffic. Radiator. The silence between two people who understand grief differently` | Narrative silence | Split: `[SFX: window traffic. Radiator] [under]` + `[DIRECTION: The silence between two people...]` |
| 266 | `distorted voice -- processed, unrecognizable, calm. Not a recording -- someone speaking in real time through heavy vocal processing` | "Not a recording" is production spec, not SFX | Reword: `[SFX: distorted voice -- processed, unrecognizable, calm. Real-time vocal processing, not pre-recorded]` |
| 313 | `bond tone settling -- still agitated but resolving, the shared anger of two people pointed at the same target` | "the shared anger..." is narrative | Move to DIRECTION |
| 317 | `the two mugs by the sink. The maps on the table. The bond humming between them -- agitated, warm, alive` | "The two mugs by the sink. The maps on the table." are visual props, not sounds | Split: `[SFX: bond-hum-warm -- agitated, alive] [bed, fade-out]` + `[DIRECTION: The two mugs by the sink. The maps on the table.]` |

### AMBIENT Coverage: GOOD
All 4 scenes have opening AMBIENT. No mid-scene location shifts lack coverage.

### Layering Logic
- Line 16: `Two sets of footsteps on concrete [spot]` -- These footsteps precede dialogue and continue alongside it. Should be `[bridge]`.
- Line 30: `Mika's footsteps -- fast, precise [spot]` -- Correct as spot (punctuating, isolated event).
- Line 305: `bond-hum-surge -- brief, hot [spot]` -- Bond surges are acute events; `[spot]` is correct.

### Sonic Vocabulary: GOOD
Bond vocabulary consistent: `bond-hum-agitated`, `bond-hum-surge`. Ash vocabulary consistent: `ash-shadows-stir`, `temperature-spike`, `fire-response`. The Summoner's distorted voice introduced at line 266.

### New Sonic Element: The Summoner's Voice
Line 266-267 establishes the summoner's vocal processing. The SFX tag says "processed, unrecognizable, calm" and "heavy vocal processing" but gives no production spec. **Needs:** Specific processing chain (pitch shift? vocoder? granular? how many semitones? what distortion type?). The DIRECTION on line 267 adds "cold, deliberate" which helps direction but not production.

### Beat Timing: GOOD
10 beats, all timed (400ms-2500ms). No beats precede multi-second SFX that already fill the pause.

---

## Episode 14: "The Spring"

**Tag counts:** SFX: 46 | AMBIENT: 7 | Beat: 6 (all timed) | Silence: 3 | DIRECTION: 5

### Hybrid SFX (Moderate)

| Line | Issue |
|------|-------|
| 32 | `Rune's mouth closing. The conversation ending because Mika ended it` -- "The conversation ending because Mika ended it" is narrative. Move to DIRECTION. |
| 60 | `Ash's silence -- not hostile. Considering` -- Silence is not SFX. Replace with `[Beat -- 800ms]` + `[DIRECTION: Ash's silence. Not hostile. Considering]` |
| 64 | `maps rustling. The quiet industry of people preparing to go underground` -- "The quiet industry..." is narrative. |
| 84 | `faucet -- on, then off. Silence` -- "Silence" is not producible. End the SFX at "off." Use `[Silence -- 800ms]` after. |
| 144 | `Ash's hand rising -- slow. The sound of sleeve fabric shifting, the faintest brush of air` -- "The sound of" phrasing is fine here (describes a producible sound). PASS. |
| 265 | `the smell of damp described through sound: water on stone, rust, ventilation groaning` -- "the smell of damp described through sound" is meta-commentary. Remove the meta prefix. |
| 297 | `ash-shadows responding -- pooling, reaching forward into the dark ahead. The sound of something vast and purposeful rearranging itself` -- "vast and purposeful" is narrative. |

### AMBIENT Coverage: GOOD
7 AMBIENT tags. Crossfades at bathroom transition (line 92) and tunnel entrance (line 273). Scene 4 tunnel descent gets its own AMBIENT at line 325.

### Layering Logic: GOOD
- Line 76: `Ash's footsteps -- pacing [bridge]` -- Correct. Footsteps continue under following dialogue.
- Line 283: `three sets of footsteps entering the tunnel [bridge]` -- Correct. Continuous movement.
- Line 287: `descent -- boots on uneven stone [bridge]` -- Correct.

### New Sonic Element: Spring Chamber Acoustics
Established at the Scene 4 tunnel descent. Needs: reverb profile specification (large natural cave, 40m depth, water-reflective surfaces). Current AMBIENT tags are descriptive ("deep tunnel," "narrower, wetter") but lack RT60 or reverb character guidance for the mixer.

### New Sonic Element: Ritual Chanting
Line 314: `chanting -- distant, muffled by stone, multiple voices in an old language. The rhythm deliberate, ritual`. Needs: number of voices (8 per ep15 line 68), language reference (or "nonsense syllables in Semitic cadence"), tempo reference, recording approach (individual voices or ensemble?).

---

## Episode 15: "Undertow"

**Tag counts:** SFX: 52 | AMBIENT: 7 | Beat: 4 (all timed) | Silence: 3 | DIRECTION: 6

### Hybrid SFX (Moderate-Heavy)

This episode has the most action of the run and contains several hybrid tags driven by the battle intensity:

| Line | Issue |
|------|-------|
| 72 | `divine presence -- the spring god manifesting. Water shaped like a figure, shifting, genderless, luminous. A voice that is not a voice` -- Visual description. Split: `[SFX: divine manifestation -- water swelling, shaping, harmonic resonance. A frequency, not a voice] [spot]` + `[DIRECTION: A figure of water, shifting, genderless, luminous]` |
| 77 | `bond detonation -- massive. The hunger hitting Ash like a physical force` -- "like a physical force" is simile. Acceptable for sound design reference. BORDERLINE. |
| 94 | `ash-shadows surging -- fire-response, temperature-spike. The air in the chamber heating. Water hissing where it touches the hot stone near Ash's feet` -- "The air in the chamber heating" is not a sound. The water hissing IS. Split. |
| 115 | `the cost -- immediate. Rune's breathing stuttering. A cough. The taste of copper described through sound: a swallow, a grimace` -- "The taste of copper described through sound" is meta-commentary. Remove the meta prefix; "a swallow, a grimace" is producible. |
| 120 | `bond tone -- the war between the hunger and the anchor, two frequencies fighting for dominance` -- "The war between..." is narrative. Producible version: `[SFX: bond tone -- two frequencies oscillating, competing, one massive and low, one smaller and insistent] [under]` |
| 124 | `Ash's breathing changing -- the primal rhythm breaking. A raw sound -- half gasp, half something older than language. The shadows pulling back like a tide reversing` -- "something older than language" and "like a tide reversing" are narrative. The raw sound/gasp is producible. "The shadows pulling back" is visual. |
| 126 | **"Not a sound" tag** (see global issue). |
| 185 | `divine dissolution -- the spring god's form unraveling. Water losing its shape. Light dispersing into the stone...` -- Visual. Producible: "water splashing irregularly, harmonics collapsing, the spring source going quiet." |

### AMBIENT Coverage: GOOD
7 AMBIENT tags. Crossfades at Scene 2 (spring chamber), Scene 4 (aftermath), Scene 5 (ascending tunnel, surface). Scene 5 surface emergence gets a city-at-night AMBIENT at line 267.

### Layering Logic: GOOD
- Line 12: `three sets of footsteps [bridge]` -- Correct.
- Line 52: `Rune and Ash's footsteps continuing down. Mika's holding position [bridge]` -- Correct.
- Line 225: `three sets of footsteps ascending [bridge]` -- Correct.
- Line 237: `ascent continuing. Water dripping. Breathing [bridge]` -- Correct.

### New Sonic Element: The Spring God's Voice
Lines 169, 173, 183: The spring god speaks with `[SFX: divine voice -- water over stone, the resonance of a spring that has run for millennia. Fragile. Thinning] [spot]`. Needs: processing spec. Recommend layered water recordings with pitch-shifted vocal undertone, heavy reverb (cathedral-scale), granular synthesis for the "fragile/thinning" quality. Should be distinct from the summoner's voice (which is distorted/processed/cold vs. divine/harmonic/warm).

### New Sonic Element: Divine Dissolution
Line 185: The god dying. Described as "water losing its shape, light dispersing, spring going dark, meridian-thrum going silent." Needs: a defined audio event -- the harmonics collapsing, the reverb tail cutting, the thrum fading. This is a recurring event (spring + aqueduct) and needs a standardized sound design template.

---

## Episode 16: "Threshold"

**Tag counts:** SFX: 44 | AMBIENT: 4 | Beat: 9 (all timed) | Silence: 7 | DIRECTION: 2

### Hybrid SFX (Moderate)

| Line | Issue |
|------|-------|
| 16 | `Rune sitting on the bed -- slow, controlled. The mattress complaint. His shoes still on` -- "His shoes still on" is visual. |
| 50 | `Ash turning -- footsteps toward the kitchen. Deliberate, purposeful. A man on a mission he's inventing as he goes` -- "A man on a mission he's inventing as he goes" is narrative. Move to DIRECTION. |
| 82 | `microwave door opening. Then: Ash's palms around a ceramic bowl -- temperature-spike, a faint hiss as his hands heat. Not fire. Conducted heat. The bowl warming` -- "Not fire. Conducted heat. The bowl warming" is production direction/description. The hiss is producible. Rework. |
| 142 | `pages settling. Ash's voice continuing -- lower, steadier. The words of airway management delivered with the gravity of sacred text` -- "delivered with the gravity of sacred text" is narrative. |
| 228 | `Kaya's hands on the pendant -- closing around it. The sound of a man holding something instead of answering` -- "The sound of a man holding something instead of answering" is narrative. |
| 294 | `the word landing in the room -- small, plain, enormous. No ambient change. The silence after a choice` -- Entirely non-producible. "The word landing" is metaphorical. "No ambient change" is a non-instruction. Replace with `[Silence -- 1500ms]` + `[DIRECTION: The word "stay" landing in the room -- small, plain, enormous]` |
| 306 | `Ash -- one step. Two. The floorboard near the bed. Then the careful, rigid lowering of weight onto a mattress -- fully clothed, on top of the covers, the farthest edge from Rune. The bed accepting this new architecture` -- "The bed accepting this new architecture" is narrative. The rest is producible. |
| 318 | `two heartbeats -- not literal, but the bond-hum pulsing in a double rhythm that gradually synchronizes` -- "not literal" is meta-commentary. The bond-hum double-pulse is producible. Remove "not literal." |
| 330 | `bond-hum-settled -- holding. The two frequencies synchronized. A sound like a door that was always locked, quietly, simply, opening` -- Simile. Move to DIRECTION. |

### AMBIENT Coverage: GOOD
4 scenes, 4 AMBIENT tags. Crossfade at Scene 2 kitchen transition (line 56). Scene 4 deep-night gets its own AMBIENT at line 254.

### Layering Logic
- Line 50: `Ash turning -- footsteps toward the kitchen [bridge]` -- Correct.
- Line 264: `footsteps -- quiet, bare feet on hardwood [spot]` -- These are isolated punctuating footsteps, not continuous. `[spot]` is correct.

### Beat-SFX Overlap Check
Line 86: `[Beat -- 800ms]` followed by inner monologue at line 88. No SFX overlap. Clean.
Line 134: `[Silence -- 2500ms]` at line 134, followed by `[SFX: bond-hum]` at line 136. The silence is the pause before the bond responds. Clean.

---

## Episode 17: "Communion"

**Tag counts:** SFX: 40 | AMBIENT: 4 | Beat: 10 (all timed) | Silence: 7 | DIRECTION: 1

### Hybrid SFX (Moderate)

| Line | Issue |
|------|-------|
| 46 | `bond-hum-warm -- the purring quality. Satisfied. Neither person acknowledging it` -- "Neither person acknowledging it" is narrative. |
| 50 | `Ash drinking -- the too-strong coffee. A slight grimace, inaudible but present in the pause before the second sip` -- "inaudible but present" is contradictory in an SFX tag; "in the pause before the second sip" is timing direction. |
| 68 | `the almost-laugh that doesn't happen -- a breath, an almost, the sound of two people on the edge of something warm and pulling back out of habit` -- "the sound of two people on the edge..." is narrative. Producible: a breath, an exhale. |
| 146 | `Mika's quiet exhale -- not a laugh. Something adjacent. The sound of a sister who sees everything and is choosing which parts to name` -- "The sound of a sister..." is narrative. |
| 210 | `bond-hum-warm -- aching. The frequency of old grief reaching through a thousand years of silence to surface in a kitchen at dusk` -- Beautiful writing; not producible. |
| 220 | `bond -- everything stops. The hum, the ambient, the traffic, the radiator. The silence of a sentence that has emptied the room of everything except itself` -- This is a mixing instruction ("everything stops") wrapped in narrative. Rework: `[SFX: all ambient and bond-hum cutting to silence -- hard stop] [spot]` + `[DIRECTION: The silence of a sentence that has emptied the room]` |
| 230 | `bond-hum-warm -- resuming. Slow. The held breath releasing. Neither person having moved or spoken or breathed or known what to do with what just passed between them` -- "Neither person having moved..." is narrative. |

### AMBIENT Coverage: GOOD
4 scenes, 4 AMBIENT tags. Ambulance cab ambient at line 78 is well-specified.

### Layering Logic: GOOD
No footstep logic errors. Bond-hum tags consistently `[under]`.

### DIRECTION Tags: SPARSE
Only 1 DIRECTION tag in the entire episode (line 222). Several SFX tags contain direction that should have been split out (see hybrids above). This is the most direction-deficient episode in the run.

---

## Episode 18: "Fever"

**Tag counts:** SFX: 42 | AMBIENT: 4 | Beat: 11 (all timed) | Silence: 8 | DIRECTION: 4

### Hybrid SFX (Moderate)

| Line | Issue |
|------|-------|
| 52 | **"Not a sound" tag.** `Rune's vision -- a sudden lurch. Not a sound but the bond-hum-surge` -- Split into producible bond-hum-surge and DIRECTION for the vision event. |
| 164 | `the sentence landing -- not loud. Ash's voice drops, not rises. The volume decreasing as the gravity increases` -- "The volume decreasing as the gravity increases" is narrative. |
| 218 | `bond-hum-surge into something new... The sound of a circuit completing` -- "The sound of a circuit completing" is metaphor. |
| 222 | `the kiss -- breath caught. Fabric gripping. Rune's hands in Ash's hair. The small sounds of two bodies finding each other for the first time -- not choreographed, not graceful. Real` -- "not choreographed, not graceful. Real" is direction. The sounds (breath, fabric, hands in hair) are producible. |
| 230 | `Ash's hands at Rune's waist -- the fabric of Rune's shirt. And beneath it, the glow. Faint. The temperature of Ash's palms rising -- not burning, but luminous, the heat of someone whose body responds to what he feels` -- "the glow. Faint" and "luminous" are visual. "the heat of someone whose body responds to what he feels" is narrative. |
| 238 | `the separation -- forehead to forehead. Both breathing hard. Not pulling away. The glow at Ash's palms fading` -- "The glow... fading" is visual. "Not pulling away" is stage direction. |
| 254 | `neither of them moving -- the not-moving louder than movement` -- Not-moving is not producible. This is pure narrative. Replace with `[Silence -- 1500ms]`. |
| 310 | `from the living room -- Ash shifting on the couch. One movement. Then still again. Then, barely audible, a sound that might be Rune's name or might be a breath or might be nothing at all` -- "or might be nothing at all" is narrative uncertainty. Producible: a shift on the couch, a barely audible breath. |

### AMBIENT Coverage: GOOD
4 scenes, 4 AMBIENT tags. Crossfade at Scene 4 (line 286).

### Layering Logic
- Line 12: `Rune's footsteps -- measured, deliberate [bridge]` -- Correct. Walking + upcoming monologue.
- Line 158: `ambulance shifting into gear. Lights. Siren [spot]` -- Correct for an acute transition event.

### New Sonic Element: The Kiss
Line 222-238: The first kiss is a major sonic set piece. Current description is adequate for sound design: breath, fabric, body contact, the bond-hum-surge at a new frequency, Ash's thermal glow. **Needs:** A specific new bond-hum variant designation. The tag calls it "incandescent" and "a frequency that has no name in the vocabulary they've built." Recommend adding `bond-hum-incandescent` to the vocabulary for this specific moment, or use `bond-hum-surge` with a production note for additional harmonic layering.

---

## Episode 19: "Anchor"

**Tag counts:** SFX: 40 | AMBIENT: 5 | Beat: 19 (all timed) | Silence: 14 | DIRECTION: 2

### Hybrid SFX (Moderate)

| Line | Issue |
|------|-------|
| 30 | `the sentence -- flat, controlled. The voice of someone who has rehearsed this` -- "The voice of someone who has rehearsed this" is direction. |
| 70 | `Rune's voice -- not loud. The opposite of loud. The word landing like a hand on a chest` -- "The word landing like a hand on a chest" is simile/narrative. |
| 82 | `Rune's voice cracking -- not with anger. With the thing underneath it. The bedrock shifting` -- "The bedrock shifting" is metaphorical. |
| 178 | `the almost-thing that happens on Ash's face -- not a laugh, but the closest he's come. A breath through his nose, the corner of his mouth` -- "the almost-thing that happens on Ash's face" and "the corner of his mouth" are visual. Producible: a breath through his nose. |
| 252 | `Kaya's breathing on the phone -- the pause of a man who has just heard the word he was avoiding spoken aloud by the person it applies to` -- Narrative. Producible: Kaya's breathing pausing on the phone line. |
| 286 | **"Not a sound" tag.** See global issue. |
| 304 | `bond-hum-warm -- running. Neither of them has spoken since the call ended. The silence is not empty. It is full` -- "Neither of them has spoken..." and "The silence is not empty. It is full" are narrative. |
| 344 | `the breath -- Ash's. Not a laugh. The thing adjacent to a laugh that he hasn't learned to complete. Closer than the last one` -- "The thing adjacent to a laugh that he hasn't learned to complete" is narrative. Producible: Ash's exhale, brief, through the nose. |

### AMBIENT Coverage: GOOD
5 AMBIENT tags. Crossfade at Scene 3 (line 150).

### Layering Logic: GOOD
No errors. Bond-hum at line 136 transitions from `[under]` to `[bed]` when it becomes the scene's persistent background tone -- correct.

### Beat-SFX Overlap Check
This episode has the highest beat density (19 beats + 14 silences = 33 timed pauses). No beats precede multi-second SFX. The density reflects the emotional weight of the episode.

---

## Episode 20: "The Aqueduct"

**Tag counts:** SFX: 75 | AMBIENT: 7 | Beat: 12 (all timed) | Silence: 9 | DIRECTION: 3

### Hybrid SFX (Heavy -- action episode)

This is the longest and most SFX-dense episode. The battle sequences drive more hybrid tags:

| Line | Issue |
|------|-------|
| 26 | `Ash beside Rune -- his footsteps quieter than they should be. Shadows pooling around his feet, moving with him like something alive` -- "Shadows pooling...like something alive" is visual/narrative. Producible: quiet footsteps, ash-shadows-stir. |
| 74 | `the team emerging into the main chamber -- footsteps on stone transitioning to the wider space. Flashlight beams sweeping. The sound of awe and fear` -- "Flashlight beams sweeping" is visual. "The sound of awe and fear" is narrative. |
| 78 | **"Not a sound" tag.** See global issue. |
| 108 | `stone -- the final section falling. The passage sealed. Dust settling. The sound of separation made permanent` -- "The sound of separation made permanent" is narrative. |
| 150 | `the aqueduct god -- water given voice. Not human speech but the impression of speech. The sound of a river...very tired` -- Rich but needs production split (see global issue example). |
| 180 | `Ash standing -- the wet stone, the effort. His body shaking. The shadows around him pulling toward the god like a tide...The physical cost of refusal visible in the tremor of his voice` -- "visible in the tremor" is visual. "Like a tide" is simile. |
| 208 | `power -- streaming past Ash...flowing through the chamber like a current of light. Streaming past him unclaimed. The hunger screaming in him and the power right there and he lets it pass` -- "like a current of light" is visual. "The hunger screaming in him" is narrative. Producible: energy sound whooshing past, Ash's strained breathing. |
| 210 | `Ash -- the cost. A sound like a man who has been holding a weight too long. His knees hitting stone. The shadows around him thin, tattered, the fire guttering` -- "thin, tattered" are visual descriptors for shadows. |
| 240 | `Mika following -- her smaller frame through the gap. Kaya staying above. Thessa pausing, then following. The sound of authority deciding to trust someone she has spent weeks despising` -- "The sound of authority deciding to trust" is narrative. |
| 378 | `[SFX: hard cut -- the ambient drops. Complete silence. Then:]` -- **Missing layering tag.** This is also a mixing instruction, not an SFX. Rework as: `[All ambient cuts to hard silence]` or a dedicated mixing direction. |

### AMBIENT Coverage: GOOD
7 AMBIENT tags covering all 6 scenes plus the summoner's post-credits space at line 380. Crossfades at Scene 2 lower chamber, Scene 5 aftermath. Scene 6 apartment gets its own AMBIENT.

### Layering Logic: GOOD
- Line 12: `footsteps -- multiple sets on wet stone [bridge]` -- Correct. Continuous movement under dialogue.
- Line 66: `the descent beginning -- footsteps on carved stairs [bridge]` -- Correct.
- Lines 336: `the group reforming -- footsteps [bridge]` -- Correct.

### New Sonic Element: The Aqueduct God's Voice
Line 150, 152, 158, 164, 172, 178, 191, 204: The aqueduct god speaks. Current description: "water given voice," "the impression of speech," "the sound of a river...very tired." Distinct from the spring god (which was "water over stone, fragile, thinning"). **Needs:** Processing spec differentiating the two divine voices. The aqueduct god is described as larger, older, more patient. Recommend: deeper fundamental frequency than the spring god, more prominent water-flow undertone, longer reverb tail, slower harmonic movement.

### New Sonic Element: Tunnel Collapse
Line 92: `EXPLOSION -- not fire. Concussive. Stone fracturing. The ceiling of the passage behind them collapsing in a controlled sequence -- one section, then the next, then the next. Deliberate. Engineered.` Good production detail. **Needs:** distinction from natural cave-in (sequential detonation pattern, engineered rhythm).

### New Sonic Element: The Summoner's Broadcast Space
Line 380-394: Post-credits scene. AMBIENT: "unknown location -- empty. Hard walls. No warmth. No water. No bond-hum." The Summoner's isolated space. Needs: reverb character specification (clinical? industrial? small concrete room?).

---

## Episode 21: "Aftershock"

**Tag counts:** SFX: 65 | AMBIENT: 6 | Beat: 19 (all timed) | Silence: 10 | DIRECTION: 0

### CRITICAL: No DIRECTION Tags

This episode has **zero** `[DIRECTION:]` tags despite containing the summoner's phone call, the rooftop confrontation, and the safe house attack. All narrative/emotional content is embedded in SFX tags or inner monologue. This is a regression to pre-convention patterns, likely because the episode's emotional intensity made it harder to separate during writing.

### Hybrid SFX (Heavy)

| Line | Issue |
|------|-------|
| 20 | `radio cutting -- Rune's hand turning it off. The silence that follows carrying its own weight` -- "carrying its own weight" is narrative. |
| 22 | `bond-hum-steady...running beneath everything like a second circulatory system` -- Simile. |
| 54 | **"Not a sound" tag.** `Mika's look -- not a sound, but the pause that means she is filing information` -- Replace with `[Beat -- 400ms]` + `[DIRECTION: Mika filing what she sees]` |
| 64 | `Mika walking away -- her footsteps, her radio crackling. Rune alone with the coffee and the ambulance bay and the city outside making sounds cities shouldn't make` -- "the city outside making sounds cities shouldn't make" is narrative. |
| 116 | `Kaya's pause -- the strategic kind, but shorter than usual. He does not have time for his own habits` -- "He does not have time for his own habits" is narrative. |
| 196 | `bond-hum -- fracturing. Not breaking. Something worse. The frequencies that have been syncing for weeks suddenly dissonant, the harmony cracking as the information hits` -- Strong sound design direction that borders on narrative. The producible instruction is: bond-hum shifting from harmonic to dissonant. The rest is DIRECTION. |
| 216 | `bond-hum-dissonant...The sound of a shared thing suddenly suspect` -- Narrative tail. |
| 234 | `Kaya's silence -- the one that means the answer is the thing he's afraid of` -- Silence-as-SFX. |
| 242 | `Rune sitting -- the couch. Not on the floor this time. On the couch, because the floor is where Ash sat when things were beginning...` -- **Missing layering tag.** Also heavily narrative. Only "sitting on the couch" is producible. |
| 248 | `Ash at the window -- not moving. The shadows at his feet still. The temperature normalizing. The silence of someone...` -- Silence-as-SFX. |
| 252 | `Ash's footsteps -- to the door. Coat. The sound of someone leaving not because they're angry...` -- Narrative. |
| 256 | `door closing. Not slammed. The click of the latch. The particular quiet of a door closed carefully by someone using all their control on the door because they have none left for anything else` -- "using all their control on the door because they have none left for anything else" is narrative. The click of the latch is producible. |
| 284 | `rooftop access door -- Rune pushing through. His footsteps on the gravel surface. Finding Ash at the railing, the same spot where he stood in Episode 8 and said "beautiful" while looking at Rune` -- "the same spot where he stood in Episode 8..." is meta-narrative/continuity reference. |
| 304 | `Ash's voice -- the archaic undertow surfacing under stress. The formal syntax re-emerging when the human part takes a hit` -- Direction for the voice actor, not SFX. Move to DIRECTION. |
| 358 | `Ash's voice -- cracking. Not the measured break of vulnerability surfacing. A genuine crack...` -- More voice direction than SFX. |
| 376 | `Ash -- the silence that means the argument has hit something he can't counter with logic` -- Silence-as-SFX. |
| 412 | `Rune moving -- toward the rooftop door. Not looking back to check if Ash is following. He doesn't need to look. He can feel the footsteps through the bond before they hit the gravel` -- "Not looking back..." and "He can feel the footsteps through the bond" are narrative. |
| 440 | `Ash -- the exhale. Closer to a laugh than anything before it. The half-second where the god-eater and the human meet in the middle and produce something that sounds like a person who might, in another life, know how to smile` -- Narrative. Producible: Ash's exhale, brief, almost-amused. |
| 446 | `bond-hum -- steady. Matched...whatever the summoner planned, whatever the bond was built for, this -- the car and the crisis and the silence that isn't empty -- this is theirs` -- Narrative. |

### AMBIENT Coverage: GOOD
6 AMBIENT tags. Crossfade at Scene 2 apartment (line 72). Rooftop AMBIENT at line 282 is well-specified.

### Layering Logic
- Line 26: `ambulance bay -- morning shift change. Rune walking in [bridge]` -- Correct.
- Line 414: `Ash following -- two steps behind. The shadows at his feet sharpening, the fire response banking into readiness [bridge]` -- Correct.

### New Sonic Element: The Summoner's Bond Monitoring
Lines 181-186: The summoner claims to have been monitoring the bond frequency. This is narrative/plot but implies a new sound design element: the bond-hum as heard through monitoring equipment (surveillance quality, clinical, removed). If this recurs, it needs a production spec.

---

## Episode 22: "Schism"

**Tag counts:** SFX: 54 | AMBIENT: 4 | Beat: 21 (all timed) | Silence: 11 | DIRECTION: 0

### CRITICAL: No DIRECTION Tags

Like ep21, this episode has **zero** `[DIRECTION:]` tags. All narrative content is embedded in SFX tags. This is the second consecutive episode with this regression.

### Hybrid SFX (Heavy)

| Line | Issue |
|------|-------|
| 12 | `Rune entering -- his footsteps on debris. Glass crunching. The first-aid kit from the car already in his hand. Paramedic mode engaging like a switch being thrown` -- "Paramedic mode engaging like a switch being thrown" is simile/narrative. |
| 32 | `Ash moving through the room -- silent, shadows trailing. Examining the broken door, the shattered windows. Touching the wall where the paint is scorched in a pattern` -- "Examining the broken door, the shattered windows" is visual/stage direction. |
| 68 | `Mika beside the other two acolytes...the particular humiliation of trained protectors who got hit in their own house` -- "the particular humiliation..." is narrative. |
| 98 | `bond-hum -- a note of surprise from Rune's frequency. Thessa admitting error. A first` -- "Thessa admitting error. A first" is narrative commentary. |
| 130 | `Ash's silence -- long enough to be its own statement` -- Silence-as-SFX. |
| 152 | `Thessa's pause -- the kind she used to fill with pronouncements. Now it fills with something less certain and more honest` -- Narrative. Replace with `[Beat -- 800ms]` + DIRECTION. |
| 160 | `Ash nodding -- a small movement, the sound of fabric. The shadows at his feet easing. Not relaxing. Adjusting to a new configuration -- not watchful-hostile, but watchful-aligned` -- "Not watchful-hostile, but watchful-aligned" is direction for the shadow character. |
| 188 | `Thessa's silence -- the kind that means she is hearing something she does not want to hear and cannot argue with` -- Silence-as-SFX. |
| 204 | `the room -- whatever small sounds were happening, they stop. Thessa's acolytes cease hammering plywood. Mika, packing her kit, goes still. Ash's hand on the map freezes` -- This is a mixing/staging instruction. Rework: `[All ambient activity drops to silence] [spot]` + DIRECTION for the staging. |
| 234 | `bond-hum -- the deeper resonance building...Something tectonic. The sound of a foundation being replaced beneath a standing structure` -- "The sound of a foundation being replaced..." is metaphor. |
| 240 | `his voice -- strange. Not the hostility of the shrine. Not the vulnerability of the kitchen...Something that might be the sound a being makes when it learns it was not built for the thing it fears most about itself` -- Narrative. Voice direction belongs in DIRECTION. |
| 248 | `bond-hum -- the deep resonance meeting Rune's frequency. The dissonance from the summoner's call finally breaking apart. Not because the argument is resolved. Because the ground beneath the argument has shifted...` -- "Not because the argument is resolved. Because the ground beneath the argument has shifted" is narrative. |
| 276 | `Thessa -- who has been silent since her two-word admission. Her voice, when it comes, is different. Not the cold pronouncement. The voice of a woman rebuilding her convictions in real time` -- Voice direction, not SFX. |
| 290 | `the room -- the silence of five people and a handful of battered god-keepers processing a revelation that rewrites a thousand years of doctrine` -- Silence-as-SFX with narrative. |
| 300 | `the almost-laugh -- not from Ash this time. From the room. The collective exhale of people who are exhausted and overwhelmed...` -- Producible: a collective exhale/breath. The rest is narrative. |
| 370 | `the city -- the late sounds. The dog again. A distant siren resolving into silence. The Meridian thrum...The world continuing its slow negotiation between what holds and what gives` -- "The world continuing its slow negotiation..." is narrative. |
| 378 | `bond-hum-warm -- the new frequency. Steady. Deep...The bond as fact. The bond as architecture. The thing they are building now...` -- Narrative. |

### AMBIENT Coverage: ADEQUATE
4 AMBIENT tags for 4 scenes. Crossfade at Scene 3 (line 168). The final street scene (Scene 4) gets its own AMBIENT at line 306.

### Layering Logic: GOOD
No errors found.

### New Sonic Element: The Kindling's Harvested Power
Line 38: `This mark. Not god-keeper fire. Not divine. Harvested. Someone is carrying residual power from the dead sacred sites. Diluted. Weak.` Lines 204: scorch patterns, diluted god-power. **Needs:** Audio design spec for "harvested divine power" -- weaker, thinner, less resonant than true divine sound. Perhaps the divine harmonic with artifacts/distortion/decay, like a degraded recording of divinity.

### New Sonic Element: God-Keeper Safe House
Lines 10-11: AMBIENT establishes "broken glass, displaced furniture, flashlights." **Needs:** Distinguish from other interior spaces -- this is a domestic space converted to operational use, now destroyed. The acoustic should feel domestic (smaller reverb than the tunnels/chambers) but violated.

---

# Summary Table

| EP | SFX | AMB | Beat | Silence | DIR | Hybrid Issues | Missing Layering | Beat Timing | AMBIENT Gaps | IM Consistent | New Sounds Specified |
|---:|----:|----:|-----:|--------:|----:|:-------------|:----------------|:-----------|:------------|:-------------|:--------------------|
| 13 | 38 | 4 | 10 | 5 | 3 | 8 tags | 0 | All timed | None | Yes | Summoner voice: needs spec |
| 14 | 46 | 7 | 6 | 3 | 5 | 7 tags | 0 | All timed | None | Yes | Ritual chanting: needs spec |
| 15 | 52 | 7 | 4 | 3 | 6 | 8 tags | 0 | All timed | None | Yes | Divine voices, dissolution: need spec |
| 16 | 44 | 4 | 9 | 7 | 2 | 9 tags | 0 | All timed | None | Yes | Bond heartbeat sync: needs spec |
| 17 | 40 | 4 | 10 | 7 | 1 | 7 tags | 0 | All timed | None | Yes | -- |
| 18 | 42 | 4 | 11 | 8 | 4 | 8 tags | 0 | All timed | None | Yes | Kiss bond frequency: needs designation |
| 19 | 40 | 5 | 19 | 14 | 2 | 8 tags | 0 | All timed | None | Yes | -- |
| 20 | 75 | 7 | 12 | 9 | 3 | 10 tags | 1 | All timed | None | Yes | Aqueduct god voice, collapse, summoner space: need spec |
| 21 | 65 | 6 | 19 | 10 | **0** | **18 tags** | 1 | All timed | None | Yes | Bond monitoring: needs spec |
| 22 | 54 | 4 | 21 | 11 | **0** | **17 tags** | 0 | All timed | None | Yes | Harvested power, safe house: need spec |
| **TOTAL** | **496** | **52** | **121** | **77** | **26** | **~100 tags** | **2** | **All timed** | **None** | **Yes** | |

---

# Priority Fix List

## P0 -- Must fix before production

1. **Eps 21-22: Add DIRECTION tags.** These two episodes have zero DIRECTION tags. ~35 hybrid SFX tags between them need narrative content extracted to DIRECTION. This is the single highest-priority fix.

2. **Remove "not a sound" from 5 SFX tags** (ep15:126, ep18:52, ep19:286, ep20:78, ep21:54). Each needs a split into producible SFX + DIRECTION.

3. **Remove silence-as-SFX from ~12 tags** across eps 14, 17, 19, 21, 22. Replace with `[Silence -- Xms]` + `[DIRECTION:]`.

4. **Add layering to 2 missing tags** (ep20:378, ep21:242).

## P1 -- Should fix before production

5. **Extract "The sound of [metaphor]" tails** from ~25 SFX tags across all episodes. These are the most common hybrid pattern in the run.

6. **Write production specs for new sonic elements:**
   - The Summoner's distorted voice (processing chain)
   - Ritual chanting (voice count, tempo, language approach)
   - Spring god's voice vs. aqueduct god's voice (distinct processing)
   - Divine dissolution (standardized audio event)
   - Tunnel collapse (engineered demolition sequence)
   - Harvested divine power (degraded divinity)
   - Bond-hum-incandescent (kiss frequency -- or fold into surge with production note)

7. **Update sonic vocabulary document** to add: `bond-hum-steady`, `bond-hum-alert`, `bond-hum-dissonant`, and optionally `bond-hum-incandescent`.

## P2 -- Nice to have

8. **Footstep layering pass** -- A few isolated footsteps tagged `[spot]` should be `[bridge]` when they lead into dialogue (ep13:16, ep16:12). Low impact but worth a consistency pass.

9. **Reverb character specs** for new environments: spring chamber, aqueduct cathedral, tunnel system, summoner's broadcast space, god-keeper safe house.

---

# Comparison: Eps 1-12 vs. 13-22

| Metric | Eps 1-12 | Eps 13-22 | Improvement |
|--------|----------|-----------|-------------|
| AMBIENT tags | 0 | 52 | Complete fix |
| Untimed beats | 100% | 0% | Complete fix |
| SFX with layering | 0% | 99.6% (494/496) | Complete fix |
| Hybrid SFX tags | ~80% of all tags | ~20% of all tags | Major improvement |
| DIRECTION tags used | 0 | 26 (but 0 in eps 21-22) | Partial fix; regression in final eps |
| Inner monologue consistency | 100% `RUNE (inner monologue):` | 100% `RUNE (inner monologue):` | Maintained |
| Sonic vocabulary | Inconsistent | Consistent + expanded | Major improvement |

**Bottom line:** The production convention pass succeeded. The remaining work is surgical -- extracting narrative tails from SFX tags, adding DIRECTION tags to the final two episodes, and writing production specs for the new sonic elements introduced in this act.

---
