# Vox Explainer Style Sheet

Use this as a locked style reference for Vox-style motion graphics explainers.

## Style Block (LOCKED across all clips)

```
Style: Modern explainer, Vox-inspired
Colors: Deep blue (#1a237e), bright yellow (#ffeb3b), white (#ffffff), charcoal (#424242)
Font style: Bold, caps, sans-serif (similar to Proxima Nova or similar)
Elements: Geometric shapes, clean lines, minimal icons, data-driven visuals
Background: Dark gradient (blue to charcoal), varies slightly per clip for visual interest
Typography: Large, readable text (min 24px equivalent), high contrast
```

## Action Block Template (SWAP per clip)

```
Action: [Describe specific motion - e.g., "Dollar bills circulate in a loop between three entities labeled 'Nvidia', 'OpenAI', 'Microsoft'"]
Camera: [Simple move - e.g., "Slow push-in", "Static with subtle zoom", "Pan left to right"]
Duration: 5-8 seconds
Additional notes: [Any specific timing or emphasis]
```

## Full Prompt Example

```
[STYLE - LOCKED]
Style: Modern explainer, Vox-inspired
Colors: Deep blue (#1a237e), bright yellow (#ffeb3b), white (#ffffff), charcoal (#424242)
Font style: Bold, caps, sans-serif
Elements: Geometric shapes, clean lines, minimal icons, data-driven visuals
Background: Dark gradient (blue to charcoal)
Typography: Large, readable text, high contrast

[ACTION - THIS CLIP]
Action: Dollar bills circulate in a loop between three entities labeled 'Nvidia', 'OpenAI', 'Microsoft'. Labels are clearly visible in bold white text.
Camera: Slow push-in
Duration: 6 seconds
```

## Model-Specific Tips

**Omni Flash**:
- Attach this style sheet as reference image
- Also include style block in text prompt (don't rely on image alone)
- Works best with big fonts — avoid micro-details

**Remotion**:
- Use for any data viz, charts, exact numbers
- Programmatic replacement possible for names/values

**Kling / SeaArt**:
- Not recommended for text-heavy motion graphics
- Use only for B-roll beauty shots without typography

---

## Notes from Production

- Generated reference sheet once, reused across 15+ clips
- Changed only action block per clip
- Style stayed 90%+ consistent
- Budget 2-3 generations per clip to get clean text
