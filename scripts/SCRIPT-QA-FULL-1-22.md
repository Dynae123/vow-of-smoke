# Full-Series Script QA: Episodes 1-22

**Scope:** Cross-batch patterns only. Issues already flagged in `SCRIPT-QA-01-12.md` and `SCRIPT-QA-13-22.md` are not repeated here unless they reveal a larger pattern at scale.

**Severity:** Critical = must fix before recording. Warning = fix if possible. Note = worth tracking.

---

## 1. REPEATED CONSTRUCTIONS AT SCALE

### 1A. "Two people" — Critical

**Count:** 19 instances across 11 of 22 episodes. Accelerates sharply in the back half.

| Episode | Count |
|---------|-------|
| 6, 8, 9, 11, 17, 21 | 1 each |
| 13, 18 | 2 each (ep13 both in DIRECTION tags) |
| 12 | 3 (inc. the closing AMBIENT) |
| 19 | 4 |
| 22 | 1 |

The phrase appears in inner monologue, DIRECTION lines, and AMBIENT descriptions. Examples of the pattern:

- "two people in a kitchen, planning for something they might not survive" (ep13)
- "two people who aren't sleeping" (ep18)
- "two people choosing to be in the same space" (ep12)
- "two people who understand grief differently" (ep13)
- "two people in two rooms staring at two ceilings" (ep18)
- "two people pointed at the same target" (ep13)
- "two people stood in a broken room" (ep22)

**Problem:** This is an AI construction tell. The phrasing is too symmetrical and self-consciously poetic each time. It becomes a tic — a way of summarizing emotional states that flattens them into postcard captions. At 19 instances the listener will hear the formula.

**Fix:** Cut to 6-8 total across the full series. Preserve the strongest (ep12 closing AMBIENT, ep18 "two people who aren't sleeping"). Replace the rest with specifics: names, actions, body parts. "Two people in a kitchen" should be "Rune and Ash, maps between them." The formula works when rare; at this density it reads as a macro.

---

### 1B. "The way [she/he/you/someone] [verbs]" comparative — Warning

**Count:** 58 instances across 21 of 22 episodes. Nearly every episode uses this construction at least twice.

Pattern: "the way she says it on calls," "the way he looks at a disease," "the way a surgeon asks where it hurts," "the way you feel a radiator through a blanket."

**Problem:** This is Rune's signature comparison mode — translating the supernatural through the familiar. That's a good instinct. But at 58 uses it becomes the *only* mode. The construction is:

> [noun] [verbed] the way [reference person] [verbs] [reference situation]

When every emotion, every glance, every temperature is routed through a "the way" simile, the technique stops revealing character and starts sounding like fill-in-the-blank.

**Fix:** Audit in two passes. (1) Cut any "the way" construction where the comparison is generic or interchangeable — e.g., "the way you feel heat from a distance" does no character work. (2) For the remaining instances, vary the syntax. Some can be restructured: "Mika said it clinically — her dispatch voice" instead of "She said it the way she says it on calls." Target: ~30-35 across the full series.

---

### 1C. "The sound of someone [gerund]" in DIRECTION tags — Warning

**Count:** 14 instances across 10 episodes (eps 6, 7, 9, 10, 12, 14, 16, 18, 20).

Examples:
- "The sound of someone holding on with both hands" (ep14)
- "The sound of someone choosing a doorway" (ep7)
- "The sound of someone undone" (ep18)
- "The sound of a circuit completing" (ep18)

**Problem:** DIRECTION lines are instructions for actors and engineers, not poetry. "The sound of someone undone" gives the actor nothing to play. These are emotional stage directions disguised as audio notes. At 14 instances across 22 episodes, it's a visible formula.

**Fix:** Replace with actable directions. "The sound of someone undone" becomes "Ash's exhale breaks halfway through — involuntary, raw." The actor needs an action, not a concept.

---

### 1D. "And [quantifier] of [pronoun] [verb]" closing flourish — Warning

**Count:** 15 instances across 7 episodes, clustering in the back half (eps 17, 19, 21 account for 10 of 15).

Pattern: "and none of it is resolved," "and all of it is happening," "and neither of us picks it up," "and both of them are true and none of them are the right one," "and every signal is pointed at me."

**Problem:** This construction anchors the big closing monologues. When Rune sums up an emotional state, he almost always reaches for "and [all/none/both/neither/every] of [it/them/us]." At scale, the rhythm becomes predictable — the listener learns that when Rune starts listing things and then reaches "and none of it," the episode is ending.

**Fix:** Vary the closing constructions. Let some monologues end on a short declarative. Let others end on a question. The "and none of it matters because" construction is strongest in ep21 (the crisis run) — keep it there, thin it elsewhere.

---

### 1E. "I would follow him" — Critical

**Count:** 2 instances in consecutive episodes (ep13, ep14).

- ep13 closing: "I would follow him into the ground."
- ep14 closing: "I think I would follow him anywhere."

**Problem:** Near-identical sentiment in back-to-back episode closings. Both are Rune's final inner monologue line. This reads as copy-paste bleed, not intentional echo.

**Fix:** Cut one. The ep14 version is stronger (it earns the "anywhere" after the bathroom scene). Rewrite ep13's closing to focus on the threat — the summoner, the spring, the blood — without the declaration of devotion.

---

### 1F. "I can feel him/it/the/his" — Warning

**Count:** 36 instances across 19 of 22 episodes.

**Problem:** This is the default bond-awareness verb. Rune "feels" Ash through the bond in almost every scene. The word "feel" carries almost no sensory weight anymore because it's doing everything — temperature, emotion, location, hunger, heartbeat. It has become the generic API call for bond-awareness.

**Fix:** Diversify the bond vocabulary. Some instances should be "the bond tells me." Some should be tactile: "the bond presses," "the bond tightens." Some should use the specific sense — "I taste his anger," "the bond goes cold at the base of my spine." The word "feel" should appear no more than ~15-18 times for bond-awareness across 22 episodes.

---

### 1G. Bond-hum closing formula — Warning

**Count:** 14 of 22 episodes end with a bond-hum SFX tagged `[bed, fade-out]` or `[bed, fade-out over episode end]`. This includes eps 1, 2, 4, 6, 10, 11, 12, 15, 16, 18, 19, 20. Ep13 ends with apartment ambient instead. Eps 3, 5 end on plot hooks (Kaya's warning, Thessa's arrival). Ep8 ends on wind/breathing. Ep14 ends on tunnel ambient. Ep17 ends on radiator/apartment. Ep20 ends on Summoner stinger. Ep21 ends on action cliffhanger. Ep22 ends on city ambient.

**Problem:** 14/22 is too many. The bond-hum fade-out has become the series' default curtain call. It's musically and emotionally correct for the intimate episodes, but using it for action-aftermath episodes too (ep15, ep20) dilutes the effect.

**Fix:** Target 8-10 bond-hum closings across 22 episodes. Keep them for the landmark emotional episodes (1, 2, 9, 10, 12, 16, 18, 19). For action/plot episodes, end on environmental sound, dialogue, or silence. The per-batch report flagged 5/7 in eps 1-7; this confirms the pattern holds through ep22.

---

### 1H. Fire/smoke/burn/ash/ember/flame metaphor density — Note

**Count:** 948 total hits across all 22 episodes (includes character name "Ash" and literal fire SFX). After removing character names and SFX cues, estimated metaphorical/thematic uses: ~250-300.

Per-episode average: ~12-14. Peaks: ep10 (58), ep20 (58), ep21 (61), ep22 (61).

**Problem:** Not a problem per se — fire/smoke is the series' central metaphor system and the title references it. But the late episodes (20-22) are running hotter than the early ones, which may create diminishing returns. When everything is fire and smoke, nothing is.

**Fix:** Review eps 20-22 for metaphorical fire/smoke in *inner monologue* specifically. Ensure that at least 30% of Rune's metaphors in the late run draw from his other register — medical, mechanical, domestic. The series should feel like fire is one note in a chord, not the whole instrument.

---

## 2. VOICE DRIFT

### 2A. Ash's contraction timeline — clean

Ash uses zero contractions in spoken dialogue from eps 1-20. First contractions appear in ep21 ("can't" x2) and ep22 ("doesn't," "don't," "hasn't"). This perfectly matches the SPEECH-PATTERNS.md specification: "eps 21+: Modern with archaic undertow."

**Status:** No issues found.

### 2B. Ash's "almost-laugh" — Warning

**Count:** At least 3 instances of Ash producing a sound described as "almost amused," "closer to a laugh," or "not a laugh" — specifically in eps 21 (line 378: "almost amused"), 21 (line 425: "Closer to a laugh than anything before it"), and 22 (inferred from DIRECTION patterns).

Pattern: `[SFX: Ash's exhale -- rough, brief. Almost amused]`

**Problem:** Ash's emotional thaw is well-tracked, but this specific SFX construction — "Ash's exhale, rough/brief, almost [emotion]" — appears multiple times in eps 21-22 alone. The "almost" qualifier is doing too much work. It's always an exhale, always rough, always "almost" something.

**Fix:** Vary the physical expression. One can be an exhale. One can be a mouth-twitch described in DIRECTION. One can be an actual short laugh — by ep22, he's earned it. The "almost" qualifier should appear once, not as the default for every softened reaction.

### 2C. Rune's spoken register — mostly clean, one cross-batch note

Per-batch reports flagged ep6 line 84 as too eloquent for spoken Rune. Across the full series, spoken Rune generally holds the clipped, paramedic register. However, a subtle drift appears in eps 19-22: Rune's spoken dialogue to Ash becomes increasingly articulate in emotional moments.

Specific instances:
- ep19: "I am dying anyway. The bond was already killing me before last night. The only difference now is that I know what I'm dying for." — This is borderline. The sentence structure is Rune-internal, not Rune-spoken. A paramedic under stress would more likely say: "I was dying before last night. At least now I know why."
- ep21: "They predicted the feelings. They predicted the bond. They did not predict that you would choose to stay human." — The tricolon construction is Kaya's voice, not Rune's. Rune would front-load the conclusion: "They didn't plan for you choosing to stay human. They got the bond right, the feelings right. But not that."

**Severity:** Warning. These are pivotal lines and the current versions are effective. But they break the "gap" — Rune is speaking his internal register out loud.

### 2D. Mika — consistent throughout

Mika's no-bullshit clinical voice holds from ep1 through ep22. Her speech patterns — short imperatives, medical terminology deployed as emotional shorthand, refusal to soften language — are consistent. The per-batch reports found no issues and the cross-batch view confirms. Her "non-negotiable" catchphrase appears in eps 13 and 18, which is acceptable spacing.

**Status:** No issues found.

### 2E. Kaya — slight over-consistency

Kaya's academic register is maintained throughout, but it's almost *too* consistent. His emotional breakthrough in ep13 (the pendant reveal, "Love seems inadequate and accurate in equal measure") is the only time his voice cracks. By ep22, when the stakes are existentially high for him — the discovery that god-eaters were preservers — his register stays formally academic.

**Severity:** Note. This may be intentional (academic evasion as armor). But the listener who heard Kaya break in ep13 might expect another crack in ep22, and it doesn't come.

---

## 3. THE GAP AT SCALE

### 3A. Gap narrowing in romantic peaks — Warning

The gap between Rune-spoken (clipped, deflecting) and Rune-internal (lyrical, vulnerable) is the show's engine. It holds well through eps 1-17. But in eps 18-19, the gap narrows dangerously:

- **Ep18, Scene 2:** Rune's spoken lines to Ash become increasingly vulnerable ("I don't have the luxury of falling apart. People need me."). This is still defensible as pressure cracking him open.
- **Ep19, Scene 2:** "I am dying anyway" and "the only difference now is that I know what I'm dying for" — these are internal-register lines delivered as spoken dialogue. The gap collapses.
- **Ep21, Scene 5:** The argument with Ash about the summoner's design — Rune's spoken rhetoric matches his internal register almost exactly. "They predicted the feelings. They predicted the bond."

**Problem:** The gap should narrow as the series progresses — that's earned. But it should narrow *gradually*, and there should still be a visible distance even in the climactic episodes. Currently, Rune-spoken in eps 19-21 sounds like Rune-internal from eps 8-12. The gap hasn't narrowed; it's collapsed.

**Fix:** In the peak moments, let Rune's spoken lines stay shorter and rougher than his thoughts. The emotion comes through in the *fewer* words, not the *more eloquent* ones. Ep19: "I was already dying. At least now I know what for." Ep21: "They planned the bond. They planned the feelings. They didn't plan you saying no."

---

### 3B. Gap maintenance in action episodes — clean

Episodes 10, 15, 20 (the crisis/action episodes) maintain the gap well. Rune speaks in clipped tactical language while his internal monologue processes the emotional cost. This is where the gap works hardest and it holds.

**Status:** No issues found.

---

## 4. COLD OPEN CATALOG

| Ep | Cold Open Type | Location | Mode |
|----|---------------|----------|------|
| 1 | Dream/nightmare | Darkness | Rune inner monologue |
| 2 | Continuous from ep1 | Shrine | Rune inner monologue |
| 3 | Mundane morning + wrong note | Kitchen, dawn | Rune inner monologue |
| 4 | News audio collage | Darkness | External voices |
| 5 | Mundane morning, cohabitation | Apartment | Rune inner monologue |
| 6 | Ash memory fragment | Darkness | Ash inner monologue |
| 7 | Environmental wrongness | City, morning | Rune inner monologue |
| 8 | Mundane morning, day count | Apartment | Rune inner monologue |
| 9 | Recorded lecture | Lecture hall | Kaya's voice (recorded) |
| 10 | Predawn supernatural event | Apartment | Rune inner monologue |
| 11 | Mundane morning, new normal | Apartment | Rune inner monologue |
| 12 | Night descent | Old quarter | Rune inner monologue |
| 13 | Routine ambulance call | Ambulance bay | Rune inner monologue |
| 14 | Battle planning | Apartment | Dialogue ensemble |
| 15 | Continuous from ep14 | Deep tunnel | Rune inner monologue |
| 16 | Aftermath return home | Apartment, late night | Rune inner monologue |
| 17 | Morning after, unspoken | Apartment, morning | Rune inner monologue |
| 18 | Morning shift, deterioration | Ambulance bay | Rune inner monologue |
| 19 | Morning after kiss, silence | Apartment, morning | Rune inner monologue |
| 20 | Team descent underground | Tunnels | Rune inner monologue |
| 21 | City falling apart, news radio | City, morning | External voices + Rune |
| 22 | Aftermath of attack | Safe house, night | Rune inner monologue |

### Clustering issues — Warning

**"Apartment morning" opens:** eps 3, 5, 8, 11, 17, 19 = 6 of 22 episodes open with Rune waking up in his apartment on a morning. This is a *significant* clustering. The listener will notice the pattern by ep8.

**"Rune inner monologue" mode:** 19 of 22 episodes open in Rune's inner monologue. Only eps 4 (news collage), 6 (Ash memory), and 9 (Kaya lecture) break the pattern.

**Fix (Critical):** At minimum, 2-3 more cold opens need to break out of Rune's head. Candidates:
- **Ep7** could open with the dogs barking before Rune narrates — give the listener 10 seconds of pure environmental before Rune speaks.
- **Ep11** could open with Kaya and Mika already mid-conversation when Rune enters — his monologue starts late, catching up.
- **Ep16** could open with Ash's perspective — his inner monologue for 20 seconds before Rune's returns. This would be the second Ash-POV cold open (after ep6) and would land hard at the midpoint.
- **Ep18** could open with Mika's voice giving a clinical report — Rune doesn't speak until she's done.

The "apartment morning" count should drop to 3-4 maximum. Eps 5 and 11 are the easiest to restructure since they're "new normal" setups that could start elsewhere (the ambulance, the university, the street).

---

## 5. END HOOK CATALOG

| Ep | End Hook Type | Content |
|----|-------------|---------|
| 1 | Bond mystery | Bond hums. "Something in my chest won't let me." |
| 2 | Bond mystery | "I don't know how I know." Bond fade. |
| 3 | Plot threat | Kaya's warning: "It is beginning." God dies. |
| 4 | Empathic dread | Rune feels Ash's hunger, understands it. |
| 5 | Character arrival | Thessa at the door: "God-eater. We have been looking for you." |
| 6 | Emotional tension | Ash in doorway. "His voice cracked on the word *want.*" |
| 7 | Emotional stillness | Ash in doorway. "The dream doesn't come back." |
| 8 | Emotional revelation | Rooftop. "He was looking at me." |
| 9 | Emotional stillness | Ash sits on bed. "It's everything." |
| 10 | Emotional warmth | Hand on shoulder. "The hand holds." Bond settles. |
| 11 | Emotional ache | "I can still feel it." Hand-brush lingers. |
| 12 | Emotional declaration | Hand-holding. "He's choosing." Bond syncs. |
| 13 | Threat + devotion | Summoner calls. "I would follow him into the ground." |
| 14 | Threat + devotion | Chanting below. "I would follow him anywhere." |
| 15 | Plot advancement | "One of them is talking." Acolyte reports. |
| 16 | Emotional breakthrough | "The bond isn't burning. It's breathing." |
| 17 | Emotional echo | "That felt like this." Reflection in glass. |
| 18 | Emotional uncertainty | "The singing and the fever might not be separate things." |
| 19 | Emotional resolve | "I am not afraid." Vow unspoken. |
| 20 | Villain stinger | Summoner recalibrates: "Something he cannot refuse." |
| 21 | Action cliffhanger | Safe house hit. "We're coming." Running. |
| 22 | Emotional resolve | "The weapon grew a heartbeat." Hand held. |

### Clustering issues — Warning

**"Emotional stillness/revelation" cluster (eps 6-12):** Seven consecutive episodes end on an emotional beat between Rune and Ash — no plot hook, no villain, no action. This is the romance engine doing its work, but seven in a row creates a structural monotony. The listener expects every episode to close on Rune staring at Ash and having a feeling.

**Eps 6 and 7:** Both end with "Ash standing in the doorway." Nearly identical staging.

**Eps 13 and 14:** Both end with "I would follow him" declarations (flagged above in 1E).

**Fix:** Break the eps 6-12 streak by adding a plot intrusion to at least 2 of those endings. Ep7 or ep8 could end with a Meridian event (subsonic thrum, a report, a siren) to remind the listener the world is ending. The emotional beat still lands — it just shares the closing with something external.

---

## 6. PACING RHYTHM

### Emotional intensity map (1 = quiet, 5 = peak):

```
Ep  1: |||.      (3) — Establishment, first bond shock
Ep  2: |||.      (3) — Ash introduction, empathic flash
Ep  3: ||||      (4) — Naming, confrontation, building collapse
Ep  4: |||.      (3) — Grief revelation, bond deepening
Ep  5: ||..      (2) — Domestic, slow build, Thessa cliffhanger
Ep  6: ||||      (4) — Cost revealed, Ash's vulnerability
Ep  7: |||.      (3) — Shame, the grove, doorway
Ep  8: ||||      (4) — Rooftop, "beautiful," Mika sees it
Ep  9: ||||.     (4.5) — Trap revealed, bed scene
Ep 10: |||||     (5) — FIRST GOD CRISIS. Sinkhole. First touch.
Ep 11: |||.      (3) — Hand brush, cataloguing, denial cracks
Ep 12: ||||.     (4.5) — Memory recovery, deliberate hand-hold
Ep 13: ||||      (4) — Mika confrontation, Summoner calls
Ep 14: ||||.     (4.5) — Bathroom scene, jaw touch, tunnel descent
Ep 15: |||||     (5) — SPRING BATTLE. Ash refuses. God speaks.
Ep 16: |||.      (3) — Aftermath, care, shared bed
Ep 17: ||||      (4) — "That felt like this," memory, aqueduct clock
Ep 18: |||||     (5) — FIRST KISS. "This is not the bond."
Ep 19: ||||.     (4.5) — Morning after, Vow of Smoke revealed
Ep 20: |||||     (5) — AQUEDUCT BATTLE. Ash's choice. Temple kiss.
Ep 21: |||||     (5) — Summoner reveal, trust shattered, safe house hit
Ep 22: ||||.     (4.5) — Reframing, new origin, hand held
```

### Pacing issues — Warning

**Problem 1: No valley after ep18.** The series hits its emotional peak at the first kiss (ep18), then stays at 4.5-5 for every remaining episode. There is no breathing room. Eps 19-22 are all crisis/revelation/confrontation. The listener has no quiet episode to recover before the act break.

**Fix:** Ep19 should open quieter and stay quieter longer. The morning-after-kiss scene has the bones for this — let it be *actually* quiet for two full scenes before the Vow revelation lands. Currently it escalates from the first page. Give the listener (and the characters) one episode where the emotional register drops to a 3 before the final sprint.

**Problem 2: Eps 10, 15, 18, 20, 21 are all 5s.** Five peak-intensity episodes in a 22-episode run is sustainable, but three of them (18, 20, 21) are consecutive. The listener goes from first kiss to aqueduct battle to summoner reveal with no pause. This is the structural equivalent of screaming for three episodes straight.

**Fix:** Ep19 is the natural valley. It currently runs at 4.5. If restructured as a 3 (quiet morning, the Vow conversation with Kaya as intellectual rather than urgent, the emotional landing happening through *calm* rather than *crisis*), the 20-21-22 sprint would hit harder by contrast.

---

## 7. ADDITIONAL CROSS-BATCH FINDINGS

### 7A. Anchoring-cost description is formulaic — Warning

Every time Rune anchors Ash, the physical cost is described with the same three markers: copper taste, vision greying/whiting at edges, immediate exhaustion. This appears in eps 10, 14, 15 (and referenced in 16, 18).

**Fix:** Vary the sensory cost. One instance: copper taste. Another: sudden cold in the hands. Another: sound dropping out (fitting for an audio drama — a brief moment of near-silence as Rune's hearing dims). The cost should feel unpredictable to the listener, not like checking boxes.

### 7B. Rune's "I know" — Note

Rune says "I know" as a spoken response 11+ times across the series. It's his deflection verb — used when he doesn't want to engage further. This is good character work *if* the frequency is intentional. But it risks sounding like a limited vocabulary rather than a character choice.

**Fix:** No action required if intentional. If not intentional, replace 3-4 instances with other deflections: "Yeah," silence, or a subject change.

### 7C. DIRECTION tags contain non-actable poetry — Warning

Multiple DIRECTION tags across the series contain prose that instructs the reader/writer but gives actors and engineers nothing to work with:

- "The silence between two people who understand grief differently" (ep13)
- "The voice of the person he was before the altar" (ep18)
- "The two mugs by the sink. The maps on the table. Two people in a kitchen" (ep13)

These are mood-setting notes for the author, not production directions. In an audio drama, DIRECTION should tell the actor *what to do with their voice* or the engineer *what to do with the sound*.

**Fix:** Audit all DIRECTION tags. Split into: (1) actable direction ("Ash's voice drops to near-whisper, formal cadence breaking") and (2) mood/visual notes that should be moved to a separate production-notes field or deleted. Visual descriptions (mugs, maps) in DIRECTION are meaningless in audio.

---

## SUMMARY TABLE

| ID | Issue | Severity | Count/Scope | Fix Effort |
|----|-------|----------|-------------|------------|
| 1A | "Two people" formula | Critical | 19 instances / 11 eps | Cut to 6-8 |
| 1B | "The way [x] [verbs]" | Warning | 58 / 21 eps | Cut to 30-35 |
| 1C | "The sound of someone" in DIRECTION | Warning | 14 / 10 eps | Rewrite as actable |
| 1D | "And [all/none/both] of [it/them]" closer | Warning | 15 / 7 eps | Vary closing syntax |
| 1E | "I would follow him" in consecutive eps | Critical | 2 / eps 13-14 | Cut one |
| 1F | "I can feel" as sole bond verb | Warning | 36 / 19 eps | Diversify to 15-18 |
| 1G | Bond-hum closing formula | Warning | 14 / 22 eps | Reduce to 8-10 |
| 1H | Fire/smoke metaphor density in late eps | Note | Elevated in eps 20-22 | Audit metaphor mix |
| 2B | Ash's "almost-laugh" repetition | Warning | 3+ in eps 21-22 | Vary physical expression |
| 2C | Rune spoken too eloquent in peaks | Warning | Eps 19, 21 | Rough up dialogue |
| 2E | Kaya no second crack | Note | Ep 22 | Consider adding break |
| 3A | Gap collapse in eps 19-21 | Warning | 3 episodes | Shorten spoken lines |
| 4 | "Apartment morning" cold opens | Critical | 6 / 22 eps | Reduce to 3-4 |
| 4 | Rune-inner-monologue cold opens | Warning | 19 / 22 eps | Add 2-3 non-Rune opens |
| 5 | Eps 6-12 all emotional closings | Warning | 7 consecutive | Add 2 plot-hook endings |
| 5 | Eps 6-7 identical staging | Warning | "Ash in doorway" x2 | Restage one |
| 6 | No valley after ep18 | Warning | Eps 18-22 all 4.5-5 | Lower ep19 to 3 |
| 6 | Three consecutive 5s (eps 18-20-21) | Warning | 3 eps | Insert valley at ep19 |
| 7A | Anchoring cost always copper/grey | Warning | Eps 10, 14, 15 | Vary sensory markers |
| 7C | Non-actable DIRECTION tags | Warning | Throughout | Audit and split |
