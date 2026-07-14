# AI Motion Graphics Model Comparison

Practical benchmarks and workflows for AI motion graphics — tested on real commercial projects (Vox-style explainers, brand campaigns, data viz). Written from the perspective of a working AI video creator who ships client work, not just demos.

**Field-tested on**: Vox-style explainers, luxury brand campaigns (Tanishq Jewellery spec), fitness lifestyle content (Horlicks Pro), product spec ads (Campa Cola retro concept).

---

## Why This Exists

I was spending hours every week trying different models for motion graphics — bar charts, animated explainers, typography sequences, brand assets. Every tutorial said "just use X" but X failed on half my use cases.

This repo captures what actually works when you have:
- A client deadline
- Specific brand guidelines (fonts, colors, logo placement)
- Need for consistency across 10-20 clips
- Zero tolerance for garbled text or morphing logos

No hype. Just what I use for what.

---

## Quick Decision Tree

**Need accurate data/charts with exact numbers?**
→ **Remotion** (code-based, programmatic, cheap at scale)

**Need dynamic camera moves, style variety, fast iteration?**
→ **Google Omni Flash** (best understanding of reference images, typography, physics)

**Need cinematic beauty shots (no text)?**
→ **SeaArt 2** (best for pure visual quality)

**On a tight budget but need decent results?**
→ **Omni Flash** (cheapest of top-tier models)

**Need to generate 1000+ personalized videos?**
→ **Remotion** (programmatic replacement, near-zero marginal cost)

**Hybrid approach (recommended for pro work)**:
→ Omni Flash for dynamic shots + Remotion for data/charts + After Effects for polish

---

## Model Comparison (Tested on Commercial Work)

### Google Omni Flash

**Best for**: Motion graphics with text, reference-based consistency, fast iteration

**Strengths**:
- Best-in-class understanding of reference images (style sheets, character sheets, mood boards)
- Typography is readable (not perfect, but usable for 80-90% of shots)
- Handles logos well with image-to-video workflow
- Fluid animations, good physics understanding
- Cheapest among top-tier models

**Weaknesses**:
- Resolution not cinema-grade (fine for social/web)
- Struggles with micro-details (tiny fonts under ~24px equivalent)
- Sensitive on known faces (blocks or distorts — workaround: generate faces separately, composite later)
- Execution can have small artifacts (requires selective editing)

**Usability**: 80-90% there for commercial work. I ship client work with this, but always budget time for fixes.

**When I use it**:
- Vox-style explainer sequences
- Brand campaign motion assets (with logo reference)
- Typography-driven social cuts
- Style-consistent multi-clip sequences

---

### Remotion

**Best for**: Data accuracy, charts, programmatic scaling, fine typography

**Strengths**:
- Pixel-perfect accuracy on numbers, dates, labels
- Programmatic generation (swap names/values across 1000s of videos)
- Near-zero marginal cost at scale
- Full control over timing, easing, transitions
- No AI artifacts (it's code, not diffusion)

**Weaknesses**:
- Steeper learning curve (React + video pipeline)
- Can't do dynamic camera moves easily (parallax possible, but not free-form)
- Less "organic" feel — looks designed, not generated
- Not great for stylized, artistic motion (Vox-style requires manual work)

**When I use it**:
- Bar charts, line graphs with exact data
- Lower-thirds with specific names/titles
- Personalized video campaigns (1000s of variants)
- Any shot where a wrong number would break the piece

---

### SeaArt 2

**Best for**: Cinematic beauty shots, visual quality over text

**Strengths**:
- Best raw visual quality for cinematic images
- Good physics on simple animations
- Handles some complex motion better than Omni

**Weaknesses**:
- Text rendering is unreliable (numbers often garbled)
- Less consistent on reference images
- Struggles with specific object understanding (e.g., renders "camera" as morphed camera-object hybrid)
- More expensive than Omni

**When I use it**:
- B-roll style cinematic shots (no text)
- Mood pieces, brand films without typography
- When visual beauty > information accuracy

---

### Kling 3.0

**Best for**: Limited use in motion graphics (as of testing)

**Strengths**:
- Decent on simple physics

**Weaknesses**:
- No reference mode (in tested platforms — only start-frame)
- Text is largely unusable
- Struggles with object consistency
- Not recommended for motion graphics with text/logos

**When I use it**: Rarely for motion graphics. Better for pure video-to-video stylization.

---

### Happy Horse

**Best for**: Not recommended for motion graphics based on testing

**Weaknesses**:
- Poor understanding of prompts
- Typography falls apart
- Object rendering inconsistent

---

## My Testing Setup

**Platform used**: Artlist (for model access during testing — unlimited generations on image models like Nano Banana, GPT-4 for reference sheets). *Note: Platform choice was for testing convenience, not endorsement.*

**Workflow**:
1. Generate one style reference sheet (locked colors, fonts, elements)
2. Create action blocks per clip (swap actions, keep style locked)
3. Use image-to-video with reference sheet attached
4. Specify style explicitly in video prompt (don't rely on image alone — style drifts mid-clip otherwise)
5. For logos/faces: generate image first, then image-to-video

**Prompt structure that worked**:
```
[STYLE BLOCK - LOCKED]
Colors: [specific hex/names]
Font style: caps, bold, sans-serif
Elements: [list key visual elements]
Background: [description or "varies per clip"]

[ACTION BLOCK - SWAPPED PER CLIP]
Action: [specific motion for this shot]
Camera: [simple move if needed]
Duration: 5-8s
```

---

## Practical Tips (Learned the Hard Way)

### Typography
- **Big fonts work** (AI struggles less)
- **Micro fonts fail** (anything under ~24px equivalent gets garbled)
- **Workaround**: Generate clean typography in Remotion, composite into Omni-generated background

### Logos & Faces
- **Logos**: Generate as image first (text-to-image with logo description), then image-to-video
- **Faces**: Known faces often blocked by Gemini/Omni. Workaround: generate with black bars or stylized treatment, or use non-recognizable angles

### Movement
- **Simple moves = more reliable** (slow push-ins, pans, zooms)
- **Complex choreography = more artifacts** (rapid cuts, multi-object interactions)
- **For dynamic shots**: Accept that you'll need to curate/select the best of 4-8 generations

### Consistency Across Clips
- Lock style in BOTH image and video prompts (don't assume image reference is enough)
- Change ONLY the action block between clips (keep colors, fonts, background style identical)
- For background variations: explicitly note "background varies" in style block

---

## When to Use Hybrid Approach

For a Vox-style explainer (like the sample in examples/):

1. **Omni Flash**: Main motion sequences, camera moves, style shots
2. **Remotion**: Any charts, data viz, lower-thirds with names
3. **After Effects**: Composite, color grade, fix typography errors, add sound design

This is the pro workflow. No single tool does it all yet — but we're 80-90% there for most use cases.

---

## Example Prompts (Screenshot-Worthy)

See `prompts/` directory for full prompt templates:
- `vox-explainer-style-sheet.md` — locked style for explainer series
- `blueprint-style.md` — technical blueprint aesthetic
- `clay-style.md` — playful claymation look
- `glass-animation.md` — refractive glass elements

Each includes:
- Style block (colors, fonts, elements)
- Action block template
- Model-specific tips

---

## Sample Workflows

See `examples/` directory:
- `vox-explainer-full-prompts.md` — every clip from a 60s explainer
- `logo-animation-workflow.md` — safe logo handling
- `chart-hybrid-remotion-omni.md` — combining tools

---

## Limitations to Budget For

**Not there yet**:
- Pixel-perfect text at small sizes
- Known faces without workarounds
- Complex multi-object physics (still improves monthly)
- 100% consistency without manual curation

**Close enough to ship**:
- 80-90% of commercial motion graphics work
- Style-consistent multi-clip sequences
- Typography at readable sizes
- Logo-safe workflows

---

## Contributing

Pull requests welcome if you have:
- Model comparisons with specific use cases
- Prompt templates that worked on client work
- Hybrid workflows (Omni + Remotion + AE)
- Cost/performance benchmarks

Please include:
- Which model(s) tested
- What problem it solves
- Before/after or example clips (links OK)

---

## License

MIT — use freely in your projects and client work. Credit appreciated but not required.

---

**Built by**: [Sagarika Sultana / madebysaira](https://madebysaira.me/)
**Location**: Tripura, India · Working with brands worldwide
**Contact**: madebysaira@proton.me

**Related repos**:
- [cinematic-ai-prompts](https://github.com/madebysaira/cinematic-ai-prompts) — Prompt library for commercial AI video
- [n8n-ai-creator-pipelines](https://github.com/madebysaira/n8n-ai-creator-pipelines) — Automation workflows for AI studios

*Last updated: July 2026 · Based on testing across 50+ commercial clips and 4 model providers*
