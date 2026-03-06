# Vow of Smoke
**A 40-episode BL audio drama (16+) — Dark Fantasy / Supernatural + Enemies-to-Lovers**

## Premise
Rune Alessi is a paramedic who keeps having the same nightmare: a burning temple, a voice calling his name, and the feeling of a hand slipping out of his. When he responds to a call at an abandoned shrine and finds a man covered in ritual scars with no memory of who he is, Rune's life fractures into the supernatural. The man calls himself Ash — volatile, unsettling, and bound to Rune through an ancient ritual. As gods across the city begin dying, Rune and Ash are dragged into a war between those trying to save the old gods and those trying to harvest their power.

## Folder Structure
```
Vow of Smoke/
├── README.md
├── preproduction/
│   ├── PITCH.md                    # Show concept and format
│   ├── CHARACTERS.md               # Character profiles
│   ├── OUTLINE.md                  # Full 40-episode outline
│   ├── STORY-BIBLE.md              # Lore, cosmology, world reference
│   ├── VOICE-CASTING.md            # Voice assignments (ElevenLabs)
│   └── INTERNAL-MONOLOGUE-GUIDE.md # Bandpass mind filter technique
├── scripts/
│   └── ep{NN}-{slug}.md            # Per-episode audio drama scripts (1-10)
├── audio/                           # Generated audio (per episode)
│   └── ep{NN}/
│       ├── dialogue/                # Voice line chunks + timestamp JSON
│       ├── sfx/                     # Episode-specific SFX
│       └── assembly/                # Intermediate assembly files
└── sfx_library/                     # Shared SFX across episodes
    ├── ambient/
    ├── foley/
    ├── music/
    └── ui/
```

## Voice Cast

| Character | Voice | Voice ID | Notes |
|-----------|-------|----------|-------|
| **RUNE** | Liam | `TX3LPaxmHKxFdv7VOQHJ` | Narrator / internal monologue |
| **ASH** | Charlie | `IKne3meq5aSn9XLyUdCD` | Pitched down ~3% in assembly |
| **MIKA** | Jessica | `cgSgspJ2msm6clMCkdW9` | Rune's paramedic partner/sister |
| **DISPATCH** | Bill | `pqHfZKP75CvOlQylNhV4` | Cold, flat — radio-filtered in assembly |
| **UNKNOWN VOICE** | Charlie/Ash | `IKne3meq5aSn9XLyUdCD` | Same voice as Ash (revealed later) |

## Script Tag Conventions

| Tag | Purpose | Produces audio? |
|-----|---------|-----------------|
| `[SFX: ...]` | Producible sound effects only | Yes |
| `[AMBIENT: ...]` | Continuous background track for the scene | Yes |
| `[DIRECTION: ...]` | Narrative context, visual descriptions, emotional cues | No |
| `[Beat — Xms]` | Timed silence (standard: 300ms) | Yes (silence) |
| `[Long beat — Xms]` | Timed silence (standard: 800ms) | Yes (silence) |
| `[Silence — Xms]` | Heavy pause (standard: 1500ms) | Yes (silence) |

## Production Pipeline
```
1. Write scripts (04-write-scripts skill, 3-ep chunks)
2. Continuity check (05-continuity skill)
3. Script QA (06-script-qa skill)
4. Voice casting (07-voice-casting skill)
5. Audio tag enhancement (08-audio-tags skill)
6. Generate dialogue (09-generate-audio skill)
7. Final mixing (10-final-mix skill)
8. /scan-audio for quality checks
```

## Status
- **Outline:** Complete (40 episodes)
- **Story Bible:** Complete
- **Characters:** Complete
- **Voice Casting:** Partial (5 of 12+ characters cast)
- **Scripts:** Episodes 1-10 written (Act I) — need rewrite through brain pipeline
- **Audio:** Episode 1 previously produced (legacy pipeline)
