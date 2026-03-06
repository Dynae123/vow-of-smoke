# Turning Dialogue into Internal Monologue

How to make a voice line sound like it's happening inside someone's head rather than being spoken aloud.

---

## The Technique: Bandpass + Micro-Echo

Two filters stacked together, then a volume correction pass.

### Filter 1 — Bandpass (300 Hz – 4 kHz)

Strip the low end and the high end of the voice.

- **Highpass at 300 Hz** removes chest resonance, room rumble, and bass warmth — the qualities that make a voice sound physically present in a space.
- **Lowpass at 4 kHz** removes sibilance, breath air, and high-frequency detail — the qualities that make a voice sound close to a microphone.

What's left is the mid-range: the core of intelligibility without the sense of a body producing the sound. It sounds filtered and internal, like hearing a voice through a layer of consciousness.

### Filter 2 — Micro-Echo (20 ms delay)

A very short echo that's too fast to hear as a distinct repeat. Instead it creates a slight doubling/smearing effect — a subtle sense of the voice bouncing around inside a head rather than projecting outward into a room.

Parameters:
- **In gain:** 0.8 (original signal at 80%)
- **Out gain:** 0.5 (echo at 50%)
- **Delay:** 20 ms
- **Decay:** 0.03 (echo dies almost immediately)

The echo is subliminal. Listeners won't consciously hear it, but they'll feel the difference between a "present" voice and an "internal" one.

### Pass 2 — Volume Correction

The bandpass cuts a lot of energy from the signal, so the processed clip comes out much quieter than the original. Measure the loudness (LUFS) after processing and boost it back up to match your spoken dialogue level.

Without this step, internal monologues get buried under ambient and music.

---

## FFmpeg Commands

### One-pass (processing only)

```bash
ffmpeg -y -i input.mp3 \
  -af "highpass=f=300,lowpass=f=4000,aecho=0.8:0.5:20:0.03" \
  -c:a libmp3lame -b:a 192k -ar 44100 -ac 2 \
  processed.mp3
```

### Two-pass (processing + level correction)

**Pass 1** — Apply the filter:
```bash
ffmpeg -y -i input.mp3 \
  -af "highpass=f=300,lowpass=f=4000,aecho=0.8:0.5:20:0.03" \
  -c:a libmp3lame -b:a 192k -ar 44100 -ac 2 \
  temp.mp3
```

**Measure** — Check the LUFS of the processed file:
```bash
ffmpeg -i temp.mp3 -af loudnorm=print_format=json -f null -
```
Look for `input_i` in the JSON output. That's the integrated loudness.

**Pass 2** — Boost to target level (e.g., if measured at -40 LUFS and target is -22 LUFS, boost by +18 dB):
```bash
ffmpeg -y -i temp.mp3 \
  -af "volume=18dB" \
  -c:a libmp3lame -b:a 192k -ar 44100 -ac 2 \
  output.mp3
```

---

## What NOT to Do

**Don't use `[whispers]`.** Whispered audio combined with bandpass filtering produces something nearly inaudible. Use normal emotional direction tags at full voice — the filter makes it sound internal.

**Don't use reverb.** Large-room reverb (cathedral, hall) makes a voice sound far away, not internal. The micro-echo at 20 ms is the key — it's short enough to feel like it's inside the listener's head rather than bouncing off walls.

**Don't skip the level correction.** The bandpass removes so much energy that an uncompensated internal clip will be 15–25 dB quieter than spoken dialogue. It'll disappear under any ambient track.

---

## Voice Direction for Internal Monologues

Since the bandpass filter creates the "internal" quality, voice direction tags should focus on **emotion and delivery** — not volume.

### Tagging Rules

1. **One tag at the start of each monologue block** (required)
2. **Additional tags only at emotional transitions** within longer monologues
3. **Do NOT tag every sentence** — a 4-sentence block typically needs 1–2 tags
4. **No volume-based tags** (`[whispers]`, `[softly]`, `[quietly]`) — volume is handled by processing

### Good Tags

| Tag | Use for |
|-----|---------|
| `[raw]` | Unguarded emotional exposure |
| `[clinical]` | Detached assessment (paramedic mode) |
| `[shaken]` | Just witnessed something destabilizing |
| `[tender]` | Intimacy, care, vulnerability |
| `[numb]` | Dissociation, overwhelm |
| `[barely holding]` | On the edge of breaking |
| `[dry, resigned]` | Dark humor, gallows self-awareness |
| `[fierce]` | Protective, defiant |
| `[hollow]` | Emptied out, dread |
| `[stunned]` | Realization landing |
| `[aching]` | Longing, grief |
| `[flat, worn]` | Exhaustion, running on empty |
| `[steady, certain]` | Settled resolve |

### Example

Before (old method — wrong):
```markdown
**RUNE (INTERNAL):** [whispers] He's angry that I'm dying. [whispers] Not because
it weakens him. [whispers] Because it's me. [whispers] Somewhere in the last nine
days, the monster on my couch started caring whether I live or die.
```

After (current method — correct):
```markdown
**RUNE (INTERNAL):** [raw, aching] He's angry that I'm dying. Not because it
weakens him. Because it's me. [devastated, tender] Somewhere in the last nine
days, the monster on my couch started caring whether I live or die.
```

---

## Quick Reference

| Parameter | Value | Why |
|-----------|-------|-----|
| Highpass | 300 Hz | Remove body/room presence |
| Lowpass | 4,000 Hz | Remove air/proximity detail |
| Echo delay | 20 ms | Subliminal doubling (not audible as echo) |
| Echo in gain | 0.8 | Keep original strong |
| Echo out gain | 0.5 | Echo at half volume |
| Echo decay | 0.03 | Dies immediately |
| Target LUFS | -22 | Match spoken dialogue level |
