# Quickstart

Get from zero to a professional site in under 2 hours.

## 1. Install (30 seconds)

```bash
npx skills add johnnichev/UltraDesign@ultradesign -g -y
```

Or manually:
```bash
git clone https://github.com/johnnichev/UltraDesign.git
mkdir -p ~/.claude/skills/ultradesign
cp -r UltraDesign/skills/ultradesign/* ~/.claude/skills/ultradesign/
```

## 2. Download a Reference Site

Find a site you admire on [Webflow](https://webflow.com), [Mobbin](https://mobbin.com), [Aura.build](https://aura.build), or [Taskade](https://taskade.com).

Download it using the [Asimov Site Downloader](https://sd.asimov.academy) or any site downloader tool. You need the `index.html` and its assets (CSS, JS, images, fonts).

## 3. Extract the Design System

Open your project in Claude Code and say:

```
I downloaded this reference site to ./reference/index.html
Extract its design system.
```

Claude generates a `design-system.html` in the same folder — your site's visual DNA.

## 4. Build Your Site

```
Using the design system we just extracted, build a landing page for [your product/service].
Start with the hero section.
```

Claude builds one section at a time. After each section, review and ask for refinements:

```
Make the background more interesting. Add subtle animation.
Polish the hover effects on the buttons.
```

Then continue:

```
Now build the features section. Use cards with hover lift effects.
```

## 5. Deploy

```
Organize the project for production and prepare for deployment.
```

Then push to GitHub + Vercel:

```bash
git init && git add . && git commit -m "initial site"
gh repo create my-site --public --push
# Connect to Vercel at vercel.com
```

Your site is live.

## Tips

- **Use Git checkpoints** after each section. If something breaks, you can roll back.
- **Generate 2-3 versions** of important sections (especially the hero) and pick the best.
- **Don't skip the design system.** Jumping straight to "build me a site" produces the same generic results every AI gives. The DS is what makes the difference.
- **Iterate.** First version is never final. 2-3 refinement passes per section is normal.
- **References beat prompts.** A screenshot of a layout you like + a design system produces better results than any text description.
