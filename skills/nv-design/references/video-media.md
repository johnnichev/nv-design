# Capability 6: Video & Media Generation

Create video content and media assets for websites using AI tools.

## When to Use

The user needs video backgrounds, product videos, hero animations, or other media for their website.

## Tools

### Google Whisk (Images from Photos)
- **URL:** Google AI Whisk
- **What:** Generates stylized images using your own photos as reference
- **Use for:** Custom hero images, styled product shots, artistic backgrounds
- **Workflow:** Upload reference photo → select style → generate variations

### Google Flow (Video Generation — Veo 3.1)
- **URL:** Google AI Flow
- **What:** Generates video from text or image prompts using Veo 3.1
- **Use for:** Hero background videos, product demos, ambient animations, parallax video content
- **Best for:** Short loops (5-15 seconds) for website backgrounds

## Video for Web Patterns

### Hero Background Video
Requirements for web use:
- **Duration:** 5-15 seconds, seamless loop preferred
- **Resolution:** 1920x1080 minimum
- **Format:** MP4 (H.264) for compatibility, WebM (VP9) for quality/size
- **File size:** Under 5MB for fast loading
- **Audio:** Muted (browsers block autoplay with audio)

```html
<video autoplay muted loop playsinline class="hero-video">
  <source src="assets/videos/hero.webm" type="video/webm">
  <source src="assets/videos/hero.mp4" type="video/mp4">
</video>
```

### Scroll-Controlled Video (Apple-style Parallax)
Video plays as user scrolls — not autoplaying:

```
Requirements for AI prompt:
- Video that tells a visual story when scrubbed frame-by-frame
- Smooth transitions (no sudden cuts)
- Works at any playback speed
- 30fps minimum for smooth scrubbing
- Use GSAP ScrollTrigger for scroll-to-video sync
```

### Ambient/Abstract Backgrounds
Good prompts for background videos:
- "Slowly morphing dark gradient, deep blue to purple, organic fluid motion, 10 second loop"
- "Subtle particle field, white dots on dark background, gentle drift, seamless loop"
- "Soft light rays through fog, golden hour warmth, slow movement, 8 second loop"

## Execution Workflow

1. **Determine what's needed** — background loop, product video, scroll-controlled, ambient
2. **Generate with appropriate tool** — Flow for video, Whisk for styled images
3. **Optimize for web** — compress, right format, right resolution
4. **Integrate** — add to site with correct HTML/CSS (autoplay muted loop for backgrounds)
5. **Fallback** — always provide a static image fallback for slow connections

```html
<!-- Video with image fallback -->
<div class="hero-bg">
  <img src="assets/images/hero-fallback.webp" class="hero-fallback" alt="">
  <video autoplay muted loop playsinline class="hero-video">
    <source src="assets/videos/hero.webm" type="video/webm">
  </video>
</div>
```

## Tips

- Shorter loops (5-8 seconds) are easier to make seamless than longer ones
- Always provide WebM + MP4 sources for cross-browser compatibility
- Use `playsinline` for iOS Safari support
- Compress aggressively — web video should be under 5MB
- For scroll-controlled video, 720p is sufficient (saves bandwidth, scrubbing is small)
- Test on mobile — some devices throttle background video playback
