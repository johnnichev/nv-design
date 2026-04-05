# Capability 5: Generate Professional Image Prompts

Create structured, professional-quality prompts for AI image generation tools. Based on the 7 Principles framework from Asimov Academy.

## When to Use

The user needs images for their website (hero photos, product shots, mockups, backgrounds) and wants prompts they can use in AI image generators like ChatGPT/DALL-E, Gemini, Grok, Midjourney, Flux, Seedream, etc.

## The 7 Principles

Every professional image prompt must address these 7 elements:

### 1. Sujeito (Subject)
Who or what is in the image. Be specific: age, ethnicity, hair, clothing, posture, expression. For products: material, shape, size, condition, brand feeling.

### 2. Ação (Action)
What the subject is doing. Natural, unstaged actions feel more authentic: "holding loosely near chest, not presenting it" vs "holding product up to camera."

### 3. Estilo (Style)
The photographic/artistic style. Be specific about camera, lens, and finish:
- "photorealistic, editorial lifestyle photography, Sony A7R IV, clean finish"
- "ultra-realistic product photography, macro detail, Hasselblad H6D"
- "ultra-realistic 3D product render, high-end tech advertising aesthetic"

### 4. Cenário (Scene/Setting)
Where the image takes place. Set the environment, what's NOT there, and the overall feeling:
- "bright home office with large windows, white walls, indoor plants"
- "minimal studio environment, soft white seamless background"
- "floating slightly above a minimal matte white surface, soft shadow beneath"

### 5. Cores (Colors/Lighting)
Color palette AND lighting setup. Be specific:
- "warm neutral tones, soft golden natural light from the right, diffused and airy quality"
- "warm gold and ivory tones, directional soft light from upper left"
- "cool blue and white UI tones with subtle purple accents, soft ambient light from above"

### 6. Enquadramento (Framing/Composition)
Camera angle, shot type, lens, composition rules:
- "medium shot, eye-level angle, rule of thirds composition, 85mm lens, shallow depth of field with creamy bokeh"
- "tight close-up shot, slight low angle, centered composition, 100mm macro lens"
- "front-facing slight angle (15 degrees), centered composition, tight product shot, 35mm equivalent"

### 7. Atmosfera (Mood/Atmosphere)
The emotional feeling the image should convey:
- "inspiring, calm and aspirational mood"
- "luxurious, delicate and premium mood, fashion editorial with natural elegance"
- "modern, trustworthy and premium mood — clean tech brand feeling with confident simplicity"

## Prompt Templates

### Hero Image — Person
```
A confident [nationality] [gender] in [their/her/his] early [age]s, [physical description],
wearing [clothing description],
[action - what they're doing, natural and unstaged],
[smile/expression] looking [direction],
photorealistic, editorial lifestyle photography, [camera model], [finish],
in [setting with specific details], [time of day] light,
[color palette], [lighting direction and quality],
[diffusion quality],
[shot type], [angle], [composition rule],
[lens], [depth of field],
[mood] mood
```

### Product Shot
```
[Close-up/Detail shot] of [product description] on/near [context],
[product state/action],
[product interaction with light],
[photography style], [camera/lens],
[finish/campaign style],
in [environment],
[background elements],
[color tones], [lighting setup],
[rim/accent lighting],
[framing], [angle], [composition],
[lens], [depth of field],
[mood],
[editorial style]
```

### App Mockup / Digital Interface
```
A [device model] in [finish],
displaying [what's on screen - be specific about UI elements],
[render style],
[advertising aesthetic],
[physical position - floating, on surface, held],
[shadow/reflection],
[environment],
[UI color scheme],
[lighting],
[angle], [composition],
[shot type], [lens equivalent],
[mood] —
[brand feeling]
```

## How to Execute

1. Ask the user what kind of image they need (hero with person, product shot, mockup, abstract background)
2. Ask for specifics: product, brand feeling, target audience, color preferences
3. Generate the prompt using the 7 principles, filling in ALL 7 elements
4. Provide the prompt in **English** (better results with most models) and optionally in Portuguese
5. Suggest which AI tool to use:
   - **People/Portraits**: ChatGPT (GPT-Image 1.5), Gemini
   - **Products**: ChatGPT, Seedream 4.5
   - **Mockups**: ChatGPT, Flux
   - **Abstract/Artistic**: Grok Imagine, Qwen Image

## Tips

- Always generate prompts in **English** first — most models perform better in English
- Provide Portuguese translation as a bonus
- "Imperfections" make images more realistic: "visible pores, freckles", "subtle fingerprints, dust", "natural wrinkles in fabric"
- Specify what you DON'T want: "no crowded background", "not tropical or touristic", "no artificial lighting"
- Include resolution and aspect ratio: "16:9 aspect ratio, 2K resolution, ultra high definition"
- Always generate 2+ variations and let the user choose
- Different models have different strengths — no single model is best for everything
