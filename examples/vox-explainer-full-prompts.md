# Vox Explainer Case Study — Full Prompts

This is the complete prompt set for a 60-second Vox-style explainer about the AI economy (inspired by testing work). Every clip uses the locked style sheet with swapped action blocks.

## Reference

Style sheet: See `prompts/vox-explainer-style-sheet.md`

---

## Clip 1 (0:00-0:10) — Opening Hook

**Style**: Locked (Vox explainer)

**Action**:
```
Action: Dollar bills circulate in a loop between three entities labeled 'Nvidia', 'OpenAI', 'Microsoft'. Labels are clearly visible in bold white text. Arrows show circular flow.
Camera: Slow push-in
Duration: 8 seconds
```

**Notes**: Generated with Omni Flash. Text readable at this size.

---

## Clip 2 (0:10-0:20) — Data Point

**Style**: Locked

**Action**:
```
Action: Bar chart grows dramatically. Label reads 'AI Data Centers' in white, bar in bright yellow. Background shows subtle American flag motif (abstracted, not literal).
Camera: Static with chart animation
Duration: 6 seconds
```

**Notes**: This would be better in Remotion for exact data. Omni version required 3 generations to get text clean.

---

## Clip 3 (0:20-0:30) — Key Figures

**Style**: Locked

**Action**:
```
Action: Three silhouettes with black bars over faces (workaround for known-face blocking). Labels below: 'Sam Altman', 'Elon Musk', 'White House'. Text in white, bold.
Camera: Slow pan left to right
Duration: 7 seconds
```

**Notes**: Gemini blocked face generation. Workaround: generated with black bars via GPT image-to-image, then used as reference for video.

---

## Clip 4 (0:30-0:40) — The Gap

**Style**: Locked

**Action**:
```
Action: Two bars appear. Left bar labeled '$1.2 Trillion' (tall, yellow). Right bar labeled 'Actual Spend' (short, white). Gap between them highlighted with red arrow.
Camera: Static
Duration: 6 seconds
```

**Notes**: Again, Remotion would be better for exact chart. Omni usable with curation.

---

## Clip 5 (0:40-0:50) — Chain Reaction

**Style**: Locked

**Action**:
```
Action: Domino effect: chips fall, hit data center icon, triggers stock graph spike, ends with pension document. All labels in white, readable.
Camera: Follows action left to right
Duration: 8 seconds
```

**Notes**: Complex multi-object scene. Required 5 generations to get clean sequence.

---

## Clip 6 (0:50-1:00) — Closing Question

**Style**: Locked

**Action**:
```
Action: Text appears sequentially: 'The question was never if it pops...' then '...it's who gets left holding it.' Text large, white, bold. Background pulses subtly.
Camera: Static
Duration: 8 seconds
```

**Notes**: Typography-focused. Omni handled this well with large fonts.

---

## Production Notes

**Total generations**: ~25-30 across all clips (5-6 per clip average)

**Success rate**: ~60% usable on first gen, ~85% by 3rd gen

**Time budget**: 2-3 hours for full sequence (including curation, light AE polish)

**Hybrid approach used**:
- Omni Flash: Clips 1, 3, 5, 6 (motion + typography)
- Would use Remotion for: Clips 2, 4 (data accuracy)
- AE: Composite, color grade, sound design

**Lessons**:
- Lock style, swap action — works great
- Big fonts only
- Budget for multiple generations
- Hybrid workflow is pro standard

---

*This case study demonstrates real commercial workflow. Not every clip is perfect, but all are shippable with minor fixes.*
