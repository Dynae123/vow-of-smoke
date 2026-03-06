# Full-Series Continuity & Script QA: Episodes 1-32

**Scope:** Cross-batch sweep across all 32 scripted episodes. Per-batch and per-episode checks already completed. This report flags ONLY patterns, drift, and issues visible at full-series scale.

**Reference docs consulted:** OUTLINE.md, STORY-BIBLE.md, CHARACTERS.md, SPEECH-PATTERNS.md, CONTINUITY-FULL-1-22.md, all 32 episode scripts.

**Previous sweep:** CONTINUITY-FULL-1-22.md flagged 5 warnings and 9 notes. Verification of those fixes is included below (Section 10).

---

## 1. Cross-Batch Construction Patterns (QUANTITATIVE)

### Phrase Frequency Audit

| Phrase | Total (32 eps) | Target | Eps 1-22 | Eps 23-32 | Verdict |
|--------|:-:|:-:|:-:|:-:|---------|
| "two people" | **20** | ~10-12 max | 5 | **15** | OVER TARGET |
| "the way" + pronoun/name | **57** | ~40-45 | 38 | 19 | BORDERLINE |
| "I can feel" (all voices) | **34** | ~20-24 | 18 | 16 | OVER TARGET |
| "behind my sternum" | **8** | ~3 | 8 | 0 | All in eps 1-10; was 9, reduced to 8. ACCEPTABLE |
| "the thing" | **70** | flag at 50+ | 40 | 30 | HIGH |
| "the particular" / "the specific" | **44** | flag at 20+ | 2 | **42** | CRITICAL SPIKE |
| "through the bond" | **88** | flag at 50+ | 52 | 36 | HIGH |
| "the sound of" (SFX/direction) | **98** | flag at 50+ | 4 | **94** | CRITICAL SPIKE |
| "the frequency of" (SFX) | **24** | flag at 15+ | 2 | **22** | SPIKE |

### Critical: "the particular" / "the specific"

> **Critical** -- 44 total uses, with **42 concentrated in eps 23-32**. This phrase barely exists in eps 1-22 (2 total) and then appears at a rate of 4+ per episode in the final batch. It has become an unconscious verbal tic in SFX descriptions: "the particular quiet of...", "the specific weight of...", "the particular heat of...". The late-batch scripts are saturated.

**Fix:** Cut to ~15 total across 32 eps. Remove from SFX/direction cues where they add no information. Reserve for moments where specificity genuinely earns the adjective. Ep31 alone has 13 instances -- reduce to 3-4.

### Critical: "the sound of" in SFX cues

> **Critical** -- 98 total uses, with **94 in eps 23-32** (the early eps describe sounds directly without this frame). The phrase "The sound of [noun]" has become a scaffolding pattern in SFX descriptions that inflates word count without adding sonic information. A sound engineer does not need "the sound of two people breathing" -- they need "two rhythms, breathing, sync."

**Fix:** Audit all SFX cues in eps 23-32. Replace "The sound of X" with direct description of X wherever possible. Target: reduce to ~30 total.

### Warning: "two people"

> **Warning** -- 20 total, but 15 are in eps 28-32. The phrase clusters heavily in the denouement episodes (ep31 has **8** instances alone). This creates a rhythmic monotony in the closing episodes where the phrase should land hardest. When "two people" is used 8 times in one episode, the 8th has zero impact.

**Fix:** In ep31, reduce from 8 to 3 (opening, Thessa visit, final scene). In ep30, reduce from 3 to 1 (the final beat). In ep32, reduce from 3 to 2.

### Warning: "through the bond"

> **Warning** -- 88 total across 32 episodes. This is structurally inevitable given the bond is the central mechanic, but it reads as repetitive. Ep10 alone has 7 instances. Eps 27 and 32 have 7-8 each.

**Fix:** Vary phrasing. "Through the circuit," "the bond carried it," "the harmonic transmitted," "Rune felt it arrive" are all available alternatives. Target: reduce to ~50 total by varying 30+ instances.

### Note: "the thing"

> **Note** -- 70 total. High but distributed evenly (2-3 per episode average). No clustering. Many are in Rune's internal voice where "the thing" is a characteristic construction ("the thing behind my sternum," "the thing that terrifies me"). Acceptable as voice signature but monitor.

### Note: "I can feel"

> **Note** -- 34 total, distributed across 20 episodes. This is high but inherent to the bond mechanic. Check that it appears in Rune's voice more than Ash's (it should -- Rune is the narrator). Some instances are in Ash's dialogue, which is correct for his register.

---

## 2. Ash's Register Evolution (Contractions)

### Contraction Tracking by Episode Range

| Range | SPEECH-PATTERNS Target | Actual Contractions in Ash Dialogue |
|-------|----------------------|-----------------------------------|
| **Eps 1-10** | ZERO | **Zero.** Ep5 "bond's" is possessive, not contraction. Compliant. |
| **Eps 11-15** | LOW | Zero. Still fully formal. |
| **Eps 16-18** | LOW (seeded) | **Ep17: "don't" (1). Ep18: "isn't" (1).** Seeded per 1-22 fix. |
| **Eps 19-20** | LOW | Zero explicit contractions found in Ash lines. |
| **Eps 21-22** | MEDIUM | **Ep21: "can't" (2), "what's" (1). Ep22: "don't" (1), "hasn't" (1).** |
| **Eps 23-25** | MEDIUM | Frequent: "don't," "it's," "I'm," "didn't," "can't," "won't." |
| **Eps 26-27** | MEDIUM | Moderate: "don't," "isn't." |
| **Eps 28-32** | MEDIUM | Frequent and natural: "That's," "I'm," "don't," "it's," "can't," "doesn't." |

### Verdict

> **Note** -- The contraction seeding in ep17-18 (the fix from the 1-22 sweep) works. The progression is:
> - Eps 1-10: Zero (archaic/formal)
> - Ep17-18: First appearance (2 total, emotional peaks)
> - Ep21-22: Expanding (5 total)
> - Ep23+: Natural frequency
>
> The jump from ep20 (zero) to ep21 (multiple) is still somewhat abrupt. Seeding one more contraction in ep19 or ep20 would smooth it further. But the current version is functional -- the ep17-18 seeds establish precedent.

### Ep03/Ep09 Near-Duplicate Line

> **Note** -- Ep03 line 261: "You are telling me someone chose this human to be my chain. That someone selected the specific person I would slowly kill." Ep09 line 119: "You are telling me someone chose him to be my leash. That someone picked the specific human I would slowly kill." These are intentional variants (chain/leash, this human/him, selected/picked) but the structural echo is very close. In a weekly release format this works as callback; in a binge format it may read as repetition.

---

## 3. The Gap: Rune's Spoken vs. Internal Voice

### Samples Across Full Run

**Ep01 -- Spoken:** "Bad sleep. That's all." / "Yeah. I'm up." / "Scale of one to ten?"
**Ep01 -- Internal:** "The voice in the dream knows my name. Not the way strangers say it -- the way someone says it when they're losing you."
**Gap:** Maximum. Paramedic efficiency vs. lyrical vulnerability. Correct.

**Ep10 -- Spoken:** "Stay with me." (3 words, imperative)
**Ep10 -- Internal:** "His shoulder under my hand. The warmth of him. The way the bond settled when I touched him."
**Gap:** Large. Correct.

**Ep18 -- Spoken:** "We shouldn't--" (2 words, trails off)
**Ep18 -- Internal:** "He kissed me. The god-eater kissed me in the kitchen and said my name against my mouth and his hands were glowing and the bond sang."
**Gap:** Maximum. Correct, and the gap IS the drama at the emotional peak.

**Ep22 -- Spoken:** "I'm saying the summoner built a weapon. We built something else."
**Ep22 -- Internal:** "They don't know this one. The one that formed when a god-eater learned he was built to save things and a paramedic was standing close enough to feel it happen."
**Gap:** Narrowing slightly -- spoken Rune allows himself a metaphor. Correct for late Act II.

**Ep27 -- Spoken:** "You'll be bound to me forever." / "Tell me." / "You were always you."
**Ep27 -- Internal:** "Seven lines. Fourteen seconds to speak. And the meaning underneath the meaning -- I give back godhood. I accept mortality."
**Gap:** Still present but the spoken lines carry more weight per word. The sentences are short but devastating. Correct narrowing.

**Ep31 -- Spoken:** "Define 'attempted.'" / "How wet." / "Come to bed."
**Ep31 -- Internal:** "He sleeps the way humans sleep -- deep, unaware, his body generating heat that makes the sheets almost too warm. He drools slightly. I'm not telling him that."
**Gap:** The gap has become *comedic* rather than tragic. Spoken Rune is still clipped; internal Rune is still lyrical but the content has shifted from anguish to tenderness. Exactly right for the denouement.

> **Note** -- The Gap holds across the full 32-episode run. It narrows appropriately at emotional peaks (ep18, ep27) and evolves from tragic to tender by ep31-32. No drift detected. This is the strongest voice-craft element in the series.

---

## 4. Bond Mechanics Full Timeline

### Complete SFX Terminology Evolution

| Episode Range | Primary Term | Notes |
|---|---|---|
| Eps 1-26 | **bond-hum** + variants | -neutral, -agitated, -surge, -warm, -settled, -incandescent, -dissonant, -alert |
| Ep27 | **Transition episode** | "bond-hum" used 19 times. Final line introduces "bond-harmonic" as the post-vow term. |
| Eps 28-32 | **bond-harmonic** | 103 total uses across 6 eps. "bond-hum" does NOT appear. |

> **Note** -- The SFX terminology transition is clean. Ep27 serves as the bridge: "bond-hum" throughout the pre-vow scenes, then the final SFX cue explicitly retires it: "Not the hum. The hum is gone. What replaces it is a harmonic." Post-ep27, "bond-hum" never recurs. No reversion detected.

### Warning: bond-harmonic Density

> **Warning** -- 103 uses of "bond-harmonic" in 6 episodes (eps 27-32) averages 17 per episode. Ep28 has 20, ep29 has 21, ep32 has 21. This is extremely dense. By contrast, "bond-hum" across 26 episodes averaged ~4 per episode. The post-vow episodes have 4x the bond SFX density of the pre-vow episodes.

**Fix:** Reduce bond-harmonic cues in eps 28-32 by ~40%. Many SFX cues in these episodes describe the bond's emotional state at length (30-50 word descriptions). A sound engineer needs the sonic instruction, not the narrative interpretation. Separate the direction from the SFX.

---

## 5. God-Death Timeline (Full Series)

### Complete God Status Tracker

| # | God | Sacred Site | Death/Change Episode | Status by Ep32 |
|---|-----|-----------|---------------------|----------------|
| 1 | Shrine god | Eastern district shrine | Pre-series | Dead (faded; site where Ash sealed) |
| 2 | River's Memory | Meridian Temple | Ep3-4 | Dead (summoner's ritual) |
| 3 | Grove god | South side grove | Ep7 | Dead (summoner's ritual) |
| 4 | Great Temple god | Central park | Ep10 | Dead (summoner's ritual) |
| 5 | Spring god | Underground spring | Ep15 | Dead (summoner's ritual) |
| 6 | Aqueduct god | River district | Ep20 | Dormant (ritual interrupted) |
| 7 | North quarter god | North quarter | -- | **Alive** (referenced ep22+) |
| 8 | Kaya's river god | Harbor district | Pre-series (~40 yrs ago) | Dead (natural fading) |
| 9 | Sable (god of dust/memory) | South quarter / demolished library | Ep23 (fading), ep32 (stabilized) | **Alive** (stabilized by Meridian change) |
| 10 | Cathedral god (the last god) | Central cathedral undercrypt | Ep29-30 (threatened, survived) | **Alive** (protected by Ash/vow) |
| 11 | New node | North quarter vacant lot | Ep32 (emerging) | **Emerging** (new growth, not a traditional god) |

### God-Count References Verified

- Ep10: Kaya says "three gods in ten days" = Meridian Temple + Grove + Central Park. **Correct.**
- Ep21: "Four gods dead or dying" = + Spring. Aqueduct is dormant, not dead. **Correct.**
- Ep25: Summoner's message "THE LAST GOD DIES AT SOLSTICE" = the cathedral god. **Correct.**
- Ep29: Selin says she has "four consumed gods" worth of power = the four killed by her ritual. **Correct.**
- Ep30: Resolution -- cathedral god survives. Ash absorbs Selin's stolen power (4 gods' worth). **Correct.**
- Ep32: Sable says "the dying gods felt the shift" -- plural, referring to remaining fading gods. **Correct.**

> **Note** -- God-death arithmetic is consistent across all 32 episodes. All references verified. The count is: 5 dead by summoner action, 1 dormant, 1 dead pre-series (natural), 1 dead pre-series (Kaya's), 2 alive, 1 emerging. No contradictions.

---

## 6. Character Knowledge States at Ep32

| Knowledge Item | Rune | Ash | Mika | Kaya | Thessa |
|---|:-:|:-:|:-:|:-:|:-:|
| Bond exists | Ep1 | Ep1 | Ep8 | Ep3 | Ep6 |
| Bond is parasitic | Ep6 | Ep6 | Ep13 | Ep5-6 | Ep6 |
| Ash is god-eater | Ep3 | Always | Ep8 | Ep3 | Ep6 |
| God-kill pattern | Ep7 | Ep7 | Ep13 | Ep4 | Ep10 |
| Summoner exists | Ep9 | Ep10 | Ep14 | Ep9 | Ep10 |
| Vow of Smoke (concept) | Ep6 | Ep19 | **Ep25** | Ep6 | Ep22 |
| Vow of Smoke (mechanics) | Ep19 | Ep19 | **Ep25** | Ep19 | Ep22 |
| Summoner = Selin | Ep24 | Ep24 | Ep24 | **Ep21** (suspected) | Ep29 |
| Summoner designed the bond | Ep21 | Ep21 | Ep25 (implied) | Ep21 | Ep29 |
| The Kindling | Ep22 | Ep22 | Ep28 | Ep22 | Ep22 |
| First Root | Ep23 | Ep23 | Unknown | Ep24 | Ep29 |
| God-eater = vessel (original) | Ep22 | Ep22 | Unknown | Ep22 | Ep22 |
| Selin's designed bond | Ep21 | Ep21 | Ep25 | Ep21 | Ep29 |
| Vow spoken | Ep27 | Ep27 | Ep28 (told) | Ep27 (present) | Ep31 |
| Ash's pre-transformation humanity | Ep12 | Ep12 | Unknown | Ep3 (texts) | Doctrine |

### Key Gaps

> **Warning** -- **Mika's knowledge of the First Root is never established.** She is present for the cathedral undercrypt confrontation (ep28-30) but the First Root is discussed primarily in Ash/Rune/Kaya scenes (ep23-24). If Mika references the First Root in any future content, a gap exists. Currently not dramatized.

> **Note** -- **Thessa learns Selin's identity only in ep29** (the undercrypt confrontation). Prior to this, her intelligence about the summoner comes through the ceasefire alliance. The reveal lands correctly -- she has no prior knowledge of Selin.

---

## 7. Motif Threads Across Full Run

### Parenthesis Scar

| Episode | Occurrence |
|---------|-----------|
| Ep11 | Introduced -- Rune notices the scar, "curves like a parenthesis" (3 mentions) |
| Ep12 | Physical touch -- Rune's thumb traces it (2 mentions) |
| Ep18 | Kiss scene -- "My thumb finds the scar on his wrist -- the parenthesis mark" |
| Ep27 | Vow scene -- "My thumb finds the parenthesis scar on his wrist. Warm. It's always warm." |
| Ep31 | Morning scene -- "The one on his wrist that curves like a parenthesis" |

> **Note** -- The 1-22 sweep flagged this motif as dropped after ep12. It has been carried forward: ep18 (kiss), ep27 (vow), ep31 (domestic). Five-beat arc across the full series. Clean and well-paced.

### Sweatshirt

| Episode | Occurrence |
|---------|-----------|
| Ep17 | Introduced -- Ash wearing Rune's sweatshirt (4 mentions) |
| Ep19 | Rune's internal references it (4 mentions) |
| Ep21 | Brief reference (1 mention) |
| Ep25 | Ash's dialogue: "wearing a sweatshirt that didn't fit" |
| Ep31 | "He's wearing my shirt. The grey one." |

> **Note** -- Consistent. The motif transitions from the specific grey sweatshirt to Ash wearing Rune's clothes generally by ep31.

### Tea/Mug (Two Mugs by the Sink)

| Episode | Occurrence |
|---------|-----------|
| Ep7 | Tea introduced -- mug, "too strong," "both hands" |
| Ep11 | "Two mugs of tea on the table"; "two mugs. His and mine. Side by side." |
| Ep13 | "Two mugs by the sink -- his and mine." |
| Ep16 | "Tea on the table -- two mugs, one too strong" |
| Ep17 | "Two mugs -- one placed, one lifted. The ceramic sounds of established routine" |
| Ep24 | "Two mugs by the sink" in ambient (3 references in episode) |
| Ep32 | "Two mugs in the sink. Two coats by the door." / "The second mug -- the one Ash uses" |

> **Note** -- The 1-22 sweep flagged this as underused (only ep13). It has been woven into the full run. Seven episodes across 32. The motif builds from ep11 (introduction) to ep32 (closing image). Clean arc.

### Nightmare/Dream --> Resolution

| Episode | Occurrence |
|---------|-----------|
| Ep1 | Nightmare introduced: fire, temple, hand slipping |
| Ep4, 5, 7, 8, 9, 10, 12 | Recurring with variations |
| Ep10 | Key shift: "Tonight the hand doesn't slip. Tonight the hand holds." |
| Ep16 | Last full nightmare reference |
| Ep27 | Brief reference to the dream during vow prep |
| Ep31 | Resolution: "I don't see the burning temple. I don't hear the voice." |

> **Note** -- Clean arc. The nightmare intensifies through Act I, pivots in ep10, fades through Act II, and is explicitly closed in ep31.

### Ash's Almost-Laugh --> Laugh

| Episode | Stage |
|---------|-------|
| Ep12 | "A sharp exhale through the nose. Almost a laugh." |
| Ep21 | "The muscle memory of amusement trying to reach his mouth" |
| Ep23 | "Almost a laugh. The corner of something that lives next to amusement" |
| Ep28 | "Close to a laugh. The same not-quite that has been building for weeks" |
| Ep31 | "The almost-laugh" (still not full, but closer) |
| Ep32 | **"Ash laughs for the first time."** Full, real laugh in the wildflowers. |

> **Note** -- This is a 32-episode payoff. Perfectly tracked. The slow build from ep12's nasal exhale to ep32's full laugh is one of the series' best long-game motifs.

### "The Hand That Holds" / Hand Motif

| Episode | Form |
|---------|------|
| Ep1 | Nightmare: "a hand gripping another -- then slipping free" |
| Ep7 | Nightmare variant: "the hand -- reaching, fingers slipping" |
| Ep10 | Pivot: "Tonight the hand doesn't slip. Tonight the hand holds." |
| Ep12 | Physical: hand-holding through the city |
| Ep15 | "He takes my hand... holds on like the earth is still trying to pull him down" |
| Ep27 | Vow: hands clasped during the speaking |
| Ep30 | "His hand finding Rune's. The specific sound of fingers interlocking." |
| Ep31 | Closing: "I don't feel the hand slipping" (negative echo of ep1) |

> **Note** -- Full-series arc from the opening image (hand slipping) to ep31 (hand no longer slips). Clean inversion. Eight beats across 32 episodes.

### Dropped Thread Check

All motifs tracked from the 1-22 sweep continue through ep32. No dropped threads detected.

---

## 8. Cold Opens and End Hooks (Full 32-Episode Catalog)

### Cold Open Types

| Type | Episodes | Count |
|------|----------|:-----:|
| **Apartment morning** | 3, 5, 8, 11, 14, 17, 19, 26, 27, 28, 31, 32 | 12 |
| **Nightmare/dream** | 1 | 1 |
| **Rune inner monologue** | 2 | 1 |
| **Ash fragment/memory** | 6 | 1 |
| **News/external audio** | 4 | 1 |
| **City/ambient (wrong)** | 7, 10, 21 | 3 |
| **Kaya lecture** | 9 | 1 |
| **Location arrival** | 12, 15, 20, 23, 25, 29 | 6 |
| **Aftermath/safe house** | 13, 16, 22 | 3 |
| **Continuous from previous** | 18, 24, 30 | 3 |

> **Warning** -- **Apartment morning opens cluster in eps 26-32.** Five of the final seven episodes open in the apartment. This is thematically coherent (the domestic reclamation arc) but creates sonic monotony in the final stretch. Eps 26, 27, 28, 31, and 32 all begin with the radiator, street noise, and the sound of the apartment.

**Fix:** Consider varying the opening ambience in ep27 or ep28 even if the location is the apartment. Ep27 could open with the rooftop ambience (where the vow is spoken) rather than the apartment. Ep28 could open with the meridian-thrum escalating beneath the city before pulling into the apartment.

### End Hook Types

| Type | Episodes | Count |
|------|----------|:-----:|
| **Bond-hum/harmonic fade-out** | 1, 2, 4, 6, 7, 9, 10, 11, 12, 14, 15, 16, 22, 23, 25, 26, 27, 28, 29, 30, 31, 32 | 22 |
| **Silence/hard cut** | 3, 18, 20, 21 | 4 |
| **Cliffhanger (action)** | 5, 8, 13, 24, 29 | 5 |
| **Rune internal closing line** | Nearly all | 30+ |

> **Warning** -- **22 of 32 episodes end with a bond-hum or bond-harmonic fade-out.** This is the default end texture. While it provides sonic continuity, it risks becoming wallpaper. Particularly in the final stretch (eps 26-32), every single episode ends with a bond-harmonic fade-out.

**Fix:** Not all of these need to change -- the bond-hum is the series' sonic signature. But consider breaking the pattern 2-3 times:
- Ep28 could end on the meridian-thrum (they're entering the cathedral, not a domestic moment)
- Ep30 could end on silence (the climax resolution deserves a hard stop before the denouement)
- One of ep31/32 could end on city ambient without the bond (the bond has become background; let the city be the final sound)

---

## 9. Pacing / Emotional Intensity Map

### Full 32-Episode Intensity Ratings

| Ep | Title | Intensity (1-5) | Type |
|:-:|-------|:-:|------|
| 1 | First Response | 3 | Setup/mystery |
| 2 | Ash | 3 | Character/tension |
| 3 | Binding Marks | 3 | Exposition/revelation |
| 4 | Fault Lines | 4 | Action/god-death |
| 5 | Smoke and Mirrors | 3 | Character/domestic |
| 6 | The God-Keepers | 4 | Confrontation |
| 7 | The Meridian | 4 | God-death/emotional |
| 8 | Pulse | 3 | Character/rooftop |
| 9 | Fault | 3 | Character/vulnerability |
| 10 | The First God | 5 | Crisis/god-death/action |
| 11 | Smoke Signals | 2 | Domestic/setup |
| 12 | Sacred Ground | 4 | Action/revelation |
| 13 | Vital Signs | 4 | Crisis/Mika told |
| 14 | The Spring | 4 | Battle prep/bathroom |
| 15 | Undertow | 5 | Combat/god-death |
| 16 | Threshold | 2 | Recovery/quiet |
| 17 | Communion | 2 | Domestic/emotional |
| 18 | Fever | 5 | Emotional peak/kiss |
| 19 | Anchor | 3 | Aftermath/vow introduced |
| 20 | The Aqueduct | 4 | Operation/action |
| 21 | Aftershock | 5 | Revelation/trust crisis |
| 22 | Schism | 4 | Reframe/alliance |
| 23 | The God of Dust | 3 | Sable/lore |
| 24 | Revelation | 5 | Selin reveal/Kaya taken |
| 25 | Smoke | 4 | Rescue/shrine return |
| 26 | Threshold | 4 | Pre-vow emotional |
| 27 | Vow | 5 | THE VOW |
| 28 | Kindling | 5 | Solstice battle begins |
| 29 | Heart of the City | 5 | Confrontation/climax |
| 30 | Solstice | 5 | Resolution of crisis |
| 31 | Daybreak | 2 | Denouement/domestic |
| 32 | Meridian | 2 | Epilogue/new beginning |

### Pacing Flags

> **Warning** -- **Eps 27-30 is four consecutive intensity-5 episodes.** This is the longest sustained peak in the series. Ep27 (vow) -> Ep28 (kindling) -> Ep29 (confrontation) -> Ep30 (climax) with no valley. The previous longest run was ep14-15 (two consecutive 4-5s) followed by ep16's valley.

This is defensible structurally (it's the climax) but listeners may experience fatigue. The vow (ep27) is emotionally exhausting; launching immediately into battle (ep28) with no breathing room risks flattening the vow's resonance.

**Fix (optional):** Consider whether ep28 Scene 1 (the apartment morning, solstice day) could be extended to provide a 5-minute breathing space before the Kindling attacks begin. The current script has the quiet morning -> Mika arrives -> Kindling attacks. If the quiet morning had one more beat of domestic normalcy, it would provide micro-contrast.

> **Note** -- Eps 31-32 as a 2-2 closing pair after four 5s is correct. The series earns its quiet ending. No pacing issue in the denouement.

### Duplicate Episode Title

> **Note** -- Ep16 and Ep26 are both titled "Threshold." This is clearly intentional (ep16 is the physical/domestic threshold; ep26 is the pre-vow emotional threshold). Confirm this is a deliberate echo for production credits.

---

## 10. Verification of 1-22 Sweep Flags

### Flag 1: Ash contraction smoothing (seed in eps 16-18)

**Status: FIXED.** Ep17 has "don't" and ep18 has "isn't" in Ash's dialogue. The jump from zero to medium is now seeded.

### Flag 2: Meridian-thrum reintroduction after ep4

**Status: FIXED.** Meridian-thrum appears in eps 4, 6, 7, 10, 12, 14, 15, 20, 21, 22, 23, 24, 25, 27, 28, 29, 30, 31, 32 (52 total uses). It was reintroduced extensively from ep23 onward.

### Flag 3: Parenthesis scar callback after ep12

**Status: FIXED.** Callbacks in ep18 (kiss), ep27 (vow), ep31 (morning). See Section 7.

### Flag 4: Mika knowledge gap about the Vow

**Status: FIXED.** Ep25 contains an explicit scene where Mika says "I think I need to be told about the vow now" and Rune explains the full mechanics. Rune's internal monologue even acknowledges the gap: "she doesn't know about the vow. I never told her." The fix is clean, dramatically motivated, and in-character for Mika.

### Flag 5: Ep22 "two weeks ago" timeline fix

**Status: FIXED.** The "two weeks ago" line from Thessa in ep22 has been removed. The only "two weeks ago" remaining in the full series is ep16 line 32 (Rune's internal, referring correctly to the ep2 doorway scene ~14 days earlier). Timeline-consistent.

---

## 11. Additional Cross-Batch Findings (New for This Sweep)

### SFX Description Bloat in Eps 28-32

> **Warning** -- SFX cues in the final batch have expanded dramatically in length. Early episodes average 10-15 words per SFX cue. Eps 28-32 average 30-50 words, with some exceeding 80 words. These cues have become narrative passages disguised as sound direction. Example:

> Ep31: `[SFX: bond-harmonic -- the final note of the episode. The final note of the act. The frequency that has evolved across thirty-one episodes -- from a transformer buzz to a parasitic drain to a singing circuit to a battle roar to this. This quiet. This hum. The sound of two people breathing together in a bed in a city that almost ended, the bond between them carrying nothing but warmth and the slow pulse of two hearts, offset, complementary, the rhythm of a system that runs on two]`

This is beautiful writing but it is not SFX direction. A sound engineer cannot mix "the rhythm of a system that runs on two." This belongs in a DIRECTION or PRODUCTION NOTE tag.

**Fix:** Split long SFX cues into: (1) the sonic instruction (what the audience hears) and (2) the narrative/emotional direction (what the moment means). Use [DIRECTION:] for the latter.

### "The frequency of" Construction in SFX

> **Note** -- 24 uses of "the frequency of [emotional state]" in SFX cues, 22 of them in eps 23-32. This is a useful shorthand for communicating to the sound engineer what the bond-harmonic should convey, but it has become formulaic. "The frequency of a man who..." appears 8+ times. Vary the construction.

### Bond-Harmonic as Meta-Commentary

> **Note** -- Several SFX cues in eps 27-32 break the fourth wall by referencing episode numbers: "Not a spike. An opening. Something that has no precedent in twenty-seven episodes." / "The first time in twenty-seven episodes it has sounded like this." / "The sound the audience has been hearing for thirty-one episodes." These are production notes, not SFX cues. They should be tagged as [DIRECTION:] or [PRODUCTION NOTE:].

### Ep05 Bond-Possessive vs. Contraction

> **Note** -- Ep05 line 58, ASH: "I feel the bond's response to your dreams." The "'s" here is possessive, not a contraction. No violation of the zero-contraction rule for eps 1-10. Confirmed clean.

---

## Summary of Flags

| Severity | Count | Key Items |
|----------|:-----:|-----------|
| **Critical** | 2 | "the particular/the specific" spike in eps 23-32 (44 total, 42 in final batch); "the sound of" SFX inflation (98 total, 94 in final batch) |
| **Warning** | 6 | "two people" clustering in ep31 (8x); "through the bond" at 88 total; bond-harmonic density 4x pre-vow rate; apartment morning cold opens cluster in final stretch (5 of 7); bond-hum/harmonic fade-out in 22/32 end hooks; SFX description bloat in eps 28-32 |
| **Note** | 11 | "the thing" at 70 (distributed, acceptable); "I can feel" at 34 (inherent to premise); contraction seeding functional but ep19-20 gap remains; ep03/ep09 near-duplicate line; The Gap holds perfectly; god-death count verified; all motifs tracked and resolved; ep16/26 duplicate title (intentional); eps 27-30 four consecutive 5s (defensible); SFX meta-commentary breaks fourth wall; "the frequency of" formulaic |

---

## Priority Action Items

### Must-Fix Before Production (Critical)

1. **"The particular" / "the specific" -- reduce from 44 to ~15.** Audit eps 23-32. Remove from SFX cues where the adjective adds nothing. Heaviest offenders: ep31 (13), ep32 (10), ep28 (5).

2. **"The sound of" SFX construction -- reduce from 98 to ~30.** Replace "The sound of X" with direct description of X in all SFX cues. This is a production-readiness issue: inflated SFX cues slow engineering workflow.

### Should-Fix (Warning)

3. **"Two people" -- reduce ep31 from 8 to 3.** Keep opening, Thessa scene, final bed scene. Cut from mid-episode SFX cues.

4. **Bond-harmonic SFX density -- reduce by ~40% in eps 28-32.** Split long cues into [SFX:] (sonic) and [DIRECTION:] (narrative).

5. **End hook variety -- break bond-harmonic fade-out pattern 2-3 times.** Suggested: ep28 (meridian-thrum), ep30 (silence), one of ep31/32 (city ambient).

6. **Cold open variety -- vary 1-2 apartment mornings in final stretch.** Ep27 or ep28 could open with rooftop or meridian ambience.

7. **"Through the bond" -- vary phrasing in ~30 instances.** Use "through the circuit," "the harmonic carried it," etc.

### Optional (Note)

8. Seed one Ash contraction in ep19 or ep20 to further smooth the register transition.
9. Move fourth-wall-breaking episode-number references from [SFX:] to [DIRECTION:] tags.
10. Review ep03/ep09 near-duplicate Ash line for binge-format listeners.

---

## What's Working

- **The Gap** between Rune's spoken and internal voice is the series' strongest craft element. Perfectly maintained across 32 episodes with appropriate evolution.
- **Ash's laugh arc** (ep12 to ep32) is a masterclass in long-game payoff. 32 episodes from almost-exhale to full laugh.
- **God-death arithmetic** is flawless. Every count, every reference, every timeline marker -- verified.
- **Motif tracking** is complete. Parenthesis scar, sweatshirt, two mugs, nightmare, hand motif -- all seeded, developed, and resolved.
- **Bond SFX terminology transition** (hum to harmonic at ep27) is clean with zero reversion.
- **Mika's Vow knowledge gap** was fixed organically in ep25 with one of the series' best Mika scenes.
- **Thematic coherence** holds across all 32 episodes. The "choosing to be human" arc is unbroken.
- **All five flags from the 1-22 sweep have been addressed.**
