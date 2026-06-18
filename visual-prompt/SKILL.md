---
name: visual-prompt
description: >
  Writes prompts for AI photo and video generation using a unified 5-block structure: character,
  action, environment, technical settings, negative prompt. ALWAYS use this skill when the user
  says: "write a prompt", "generate a prompt", "create a prompt for photo/video/generation",
  "help me with a prompt", "prompt for Midjourney / DALL-E / Flux / Stable Diffusion / Sora /
  Runway / Kling / Pika / Luma / Hailuo / Seedance / Nano Banana / ChatGPT Image / Gemini /
  Perplexity". Also triggers on "draw", "make an image", "animate",
  "make a video", "create a scene", "I want to generate a photo/video". Lithuanian triggers:
  "parašyk promptą", "sukurk vaizdą", "sukurk sceną", "padaryk video", "generuok nuotrauką",
  "prompts vaizdui". Always use this skill — even for vague requests like "girl in a forest"
  or "cool car video". If the user wants to generate any visual content with AI, use this skill.
---

# Visual Prompt Generator — Photo & Video

One skill for writing prompts for any AI generation: photo or video.
The structure is the same for both; the platform is specified by the user or set to a sensible default.

---

## Step 1 — Determine the generation type

If the user hasn't specified — ask with a single question:
> `Is this for a photo or video? And which platform (Midjourney, Flux, Runway, Kling, etc.)?`

If it's obvious from context — skip the question and write the prompt directly.

---

## Step 1.5 — Animated / 3D / Illustrated source check

**Only applies when the reference image is:** a 3D CGI character, anime, cartoon, illustrated character sheet, stylized avatar, or any non-photographic source.

Ask ONE question before writing the prompt:
> `Do you want her/him pulled into the real world (full photorealism), or upgraded within the same stylized universe (cinematic CGI quality)?`

**Path 1 — Stay in the stylized universe (universe consistency)**
Use when the character belongs to an existing cast or animated project.
- Style directive: `ultra-realistic stylized 3D CGI, cinematic animated feature quality`
- Remove: `photorealistic`, `not animated`, `no CGI look`, `realistic pores`
- Add: `slightly exaggerated eyes, elevated cheekbones, stylized anatomy — preserve caricature silhouette language`
- Skin: `real-feeling subsurface scattering — not plastic, not flat` (texture yes, realism no)
- Pose: lean toward strong archetypal body language matching the character's personality — avoid neutral/relaxed stances that weaken their identity

**Path 2 — Cross into photorealism (intentional style break)**
Use when the character is meant to feel like a real person — outsider, dream sequence, social media figure, or "real woman in an exaggerated world" narrative effect.
- Style directive: `photorealistic, shot on [camera], editorial fashion quality`
- Remove: all CGI/stylized language
- Add: `real skin texture, natural pores, realistic anatomy`
- Note: this will create visible visual contrast with any stylized cast members — use intentionally

**If unclear from context — always ask.** These two paths produce completely different results and the wrong choice breaks either universe consistency or the realism goal.

---

## Step 2 — Prompt Structure (unified for photo and video)

Always output the prompt in these five blocks:

---

### 1. 👤 Character Description
Who is in the scene. Be as specific as possible.

**Include:**
- Gender, age, appearance (hair color, eye color, build)
- Clothing and accessories — in detail
- Facial expression, pose, mood
- If there's no character — describe the main subject/object

**Examples:**
- ✅ `Young woman, ~25 years old, wavy auburn hair to shoulders, green eyes, freckles, wearing an oversized white shirt and jeans, looking at camera with a slight smile`
- ❌ `beautiful girl`

---

### 2. 🎬 Character Action
What the character is doing. For video — describe dynamics and change over time.

**For photo:**
- Pose, gesture, interaction with objects
- A static state is also an action

**For video — add:**
- Start → end of movement
- Speed: `slowly`, `smoothly`, `sharply`, `gradually`
- Camera movement: `slow push in`, `tracking shot`, `orbit`, `static shot`

**Examples:**
- Photo: `sitting on a windowsill, arms wrapped around knees, gazing out the window`
- Video: `slowly turns toward the camera, hair blown by wind, camera gently pushes in (slow push in)`

---

### 3. 🌿 Environment Description
Where the scene takes place. Think in three layers: foreground / midground / background.

**Include:**
- Location + time of day + weather
- Lighting: `golden hour`, `neon glow`, `soft diffused`, `overcast`, `candlelight`
- Atmosphere and color palette
- For video: what moves in the background (leaves, crowd, water)

**Example:**
- `Abandoned greenhouse, broken glass on the floor (foreground), rusted metal structures (midground), thick fog and forest outside (background), soft morning light, cool blue-green palette`

---

### 4. ⚙️ Technical Settings

#### For photo:

| Parameter | Options |
|---|---|
| Style | photorealistic, cinematic, illustration, concept art, fashion editorial |
| Camera | shot on Sony A7IV / Canon R5, 85mm lens, f/1.8 |
| Quality | 8K UHD, sharp focus, highly detailed, masterpiece |
| Aspect ratio | 1:1 / 4:5 / 16:9 / 9:16 |

**By platform:**
- **Midjourney:** `--ar 4:5 --v 6.1 --style raw --q 2`
- **Flux / SD:** `masterpiece, best quality, 8k uhd, sharp focus, dslr`
- **DALL-E 3:** plain descriptive text only — no parameters
- **Ideogram:** add `clean typography, legible text` if text in image is needed
- **ChatGPT Image 2 (GPT Image 2):** write a production brief — job, subject, exact text, composition, style, aspect ratio; no special syntax needed; excels at text-in-image and brand assets; include hex codes for brand color accuracy; keep the same conversation thread for consistent multi-image edits
- **Nano Banana / Gemini:** write a descriptive narrative paragraph, not a keyword list — the model understands natural language deeply; use Subject + Composition + Action + Location + Style; supports up to 14 reference images for character consistency; excellent text rendering in multiple languages; refine iteratively in the same chat thread; for Nano Banana Pro add SCALIST breakdown: Subject, Composition, Action, Location, Image style, Specs, Text rendering
- **Perplexity:** lightweight image feature backed by DALL-E 3, FLUX.1, or Nano Banana; use plain descriptive prompts; best for research-driven or contextually grounded visuals; limited editing — not ideal for fine art direction

#### For video:

| Parameter | Options |
|---|---|
| Duration | 5–10 sec (Runway, Pika), up to 30 sec (Kling Pro, Sora) |
| Aspect ratio | 16:9 (landscape), 9:16 (reels/stories), 1:1 |
| Quality | cinematic 4K, 24fps film grain, smooth motion |
| Motion style | slow motion, real-time, timelapse |

**By platform:**
- **Runway Gen-3/4:** `[Camera]: [Subject] [Action], [Setting], [Style]` — keep it short
- **Kling:** detailed description + emphasis on realistic movement
- **Sora:** full paragraph with physics (fabric, water, wind)
- **Pika:** simple + `Pikaffect: [effect name]` if a special effect is needed
- **Luma / Hailuo:** emphasize atmosphere and smooth camera movement
- **Seedance 2.0:** Subject + Action + Environment + Camera + Lighting/Mood + Style; 50–100 words is the sweet spot; camera movement is the single most impactful element (always specify: `slow dolly forward`, `overhead shot`, `handheld close-up`, `tracking shot`); use real-world style references ("Apple keynote style", "Wes Anderson symmetry") as stylistic anchors; supports multi-shot storytelling, audio-video sync, and up to 12 reference inputs; generates 2K at 24fps; define motion explicitly — leaving movement vague leads to flat or static output. **Note:** for full Seedance 2.0 production briefs (shot lists, cinematic sequences), use the dedicated `video-prompt-builder` skill instead

---

### 5. 🚫 Negative Prompt
What should NOT appear in the output.

**Base negative prompt (always include):**
```
worst quality, low quality, blurry, deformed, ugly, watermark, signature, text,
extra limbs, missing limbs, bad anatomy, bad proportions, distorted face,
overexposed, underexposed, noise, grain
```

**Add per use case:**
- Portrait: `+ asymmetrical eyes, crossed eyes, double face, bad skin`
- Video: `+ flickering, jitter, camera shake, stuttering motion`
- Nature/landscape: `+ people, buildings, power lines, cars`
- Product: `+ shadows, reflections, cluttered background`

---

## Step 3 — Output Format

```
📸 PHOTO PROMPT  /  🎬 VIDEO PROMPT
Platform: [name]

👤 Character:
[text]

🎬 Action:
[text]

🌿 Environment:
[text]

⚙️ Technical settings:
[text / parameters]

🚫 Negative prompt:
[text]

---
🔄 Variant 2 — [different style / mood]:
[brief alternative prompt]
```

Always deliver 1 main prompt + 1 variant with a different mood or style.

---

## Quick Templates by Scene Type

### Portrait / Fashion
```
Character: [detailed description]
Action: looking at camera / glancing away / hair moving slightly
Environment: studio background / minimalist / textured wall, soft side light
Tech: fashion editorial, shot on Hasselblad, 80mm, f/2.0, 8K, --ar 4:5
Negative: base + asymmetrical face, bad skin, plastic look
```

### Landscape / Nature
```
Character: none (or small figure for scale)
Action: static / wind moves through grass / water flows
Environment: [location], golden hour / blue hour, God rays, foreground texture
Tech: drone shot / wide angle 16mm, landscape photography, 8K, --ar 16:9
Negative: base + people, buildings, power lines
```

### Product / Commercial
```
Character: [product] — material details, color, shape
Action: static / slow 180° orbit (for video)
Environment: clean studio, marble/wood surface, soft key light + rim light
Tech: commercial photography, 4K, sharp focus, neutral background
Negative: base + cluttered background, harsh shadows, reflections
```

### Cinematic Scene / Action (video)
```
Character: [detailed]
Action: [movement with dynamics] — tracking shot follows / camera orbits
Environment: [atmospheric location], motion in background
Tech: cinematic 4K, 24fps film grain, slow motion x0.5 / real-time
Negative: base + flickering, jitter, camera shake
```
