# FAQ

## General

### Do I need to know how to code?
No. The methodology is designed for non-coders who want to direct AI to build professional sites. You should understand basic concepts (what HTML/CSS/JS are, what a "section" is, what "hover effect" means) — but you don't write any code manually.

### Which AI model should I use?
For **Design System extraction**: use the best model available. The DS quality determines everything downstream. Claude Opus, Gemini 3 Pro, or GPT-5.2 recommended.

For **site building**: any decent model works once you have a good DS. Even cheaper/faster models produce great results when guided by a design system.

For **creative work** (recombination, deciding layouts): Gemini tends to be more creative; Claude tends to be more precise. Use whichever fits your need.

### Why not just use a website builder (Wix, Squarespace, etc.)?
Those tools produce functional but generic-looking sites. UltraDesign produces sites that look like they were built by a senior design agency — with custom animations, micro-interactions, parallax effects, and unique visual identity. The difference is immediately visible.

### How long does it take to build a complete site?
1-2 hours for a complete landing page (hero + 4-5 sections + footer). The design system extraction takes 5-10 minutes. Most time is spent on refinement.

## Design Systems

### Where do I find reference sites to download?
Four recommended sources:
- **[Webflow](https://webflow.com)** — Gallery of sites created by professional designers
- **[Mobbin](https://mobbin.com)** — UI reference library
- **[Aura.build](https://aura.build)** — Premium design templates
- **[Taskade](https://taskade.com)** — Useful for dashboards and app interfaces

### How do I download a reference site?
Use the [Asimov Site Downloader](https://sd.asimov.academy) (free, online). It creates a Chrome virtual browser to capture everything including dynamically-loaded content. Alternatively, any site downloader browser extension works — you just need the `index.html` and its CSS/JS/image assets.

### Can I combine design systems from completely different styles?
Yes — that's the point. Taking dark theme typography from one reference and colorful card components from another creates something unique. The AI handles the technical merge. You direct what elements come from where.

### The extracted design system is missing some components. What do I do?
Ask Claude for a second pass: "The design system is missing the animation gallery and card components. Add those sections based on the original index.html." Usually the first extraction gets 80-90% right; a second pass fills the gaps.

## Building

### Why section-by-section? Can't AI just build the whole site at once?
It can, but the quality drops significantly. When asked to do too much at once, AI conserves "effort" by simplifying: fewer animations, plain backgrounds, basic hover effects. Building one section at a time lets it focus fully on making each section polished.

### The AI keeps generating purple gradients despite my design system.
Be explicit: "Use ONLY the colors from the design system. No purple or blue gradients." Then reference specific CSS classes from the DS. If it persists, start a new conversation — sometimes the AI's "creative defaults" are sticky within a session.

### My animations aren't working when I open the HTML file.
Check that: (1) the JS/CSS files from the design system are in the correct relative path, (2) CDN libraries (GSAP, ScrollTrigger) are properly linked, (3) you're opening in a browser via a local server (`npx serve .`) rather than double-clicking the file.

## Deployment

### How do I put the site online?
Recommended stack: GitHub (code storage) + Vercel (hosting). Both free tier.
1. Push your code to GitHub
2. Connect Vercel to your GitHub repo
3. Vercel auto-deploys. Your site is live at `your-project.vercel.app`
4. Optionally add a custom domain (~$40/year from any registrar)

### Does the site need a backend?
For static landing pages, portfolios, and marketing sites — no. HTML/CSS/JS files served directly from Vercel. If you need forms, use a service like Formspree or Typeform embedded in the page.
