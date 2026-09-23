# miladjavadi.com

Personal landing site for Milad Javadi. It is a static site with no build step.

The page is config-driven: `index.html` holds a `CONFIG` object with one entry per
audience track (`pricing`, `strategy`, `economics`), and a small render engine builds
every section from that data based on the `?track=` query parameter (default `pricing`).
There is no per-track hard-coded section HTML — add or edit content by editing `CONFIG`,
not the render functions. A `<noscript>` fallback covers the no-JS case.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The full landing page: config, render engine, and inline CSS. |
| `404.html` | "Page not found" page. |
| `favicon.svg`, `apple-touch-icon.png` | Browser and home-screen icons. |
| `og-image.png` | Preview image for LinkedIn, Slack, and other link shares (1200 x 630). |
| `portrait.jpg` | Hero photo (900 x 1125, 4:5). |
| `Milad_Javadi_Resume_Pricing.pdf` | Resume for the pricing/procurement track (nav, contact). |
| `Milad_Javadi_Resume_Strategy.pdf` | Resume for the strategy/operations track. |
| `Milad_Javadi_Resume_Economics.pdf` | Academic CV for the research/economics track. |
| `robots.txt`, `sitemap.xml` | Search engine files. Sitemap lists all three track URLs. |
| `CNAME` | Custom domain for GitHub Pages (`www.miladjavadi.com`). Other hosts ignore it. |

## Tracks

| Track | URL | Audience |
|-------|-----|----------|
| Pricing (default) | `/` | Recruiters, pricing/RGM/procurement roles |
| Strategy | `/?track=strategy` | Retail ops, transformation, program leadership |
| Economics | `/?track=economics` | Research, applied economics, academic |

Each track config controls: document title/meta description/canonical/JSON-LD, hero
headline and rotating roles, the proof-bar metrics, section order, expertise cards,
case studies (pricing/strategy only), experience mode (full timeline vs. the T3
consolidated single block), the differentiator section (pricing/strategy only), the
contact ask, and the resume file. All facts must trace back to the career-tailor
skill's `canonical-facts.md` — do not invent metrics, titles, or dates.

## Preview locally

```bash
cd website
python3 -m http.server 8000
# open http://localhost:8000
```

## Deploy

Upload the contents of this `website/` folder to any static host. Common options:

- **Netlify or Cloudflare Pages:** connect this repository, leave the build command empty, and set the publish (output) directory to `website`.
- **GitHub Pages:** "Deploy from a branch" serves only the repository root or `/docs`. To use it, move these files to one of those locations, or deploy the `website` folder with a GitHub Actions Pages workflow.

Then add `www.miladjavadi.com` as the custom domain in the host's dashboard and follow its DNS instructions. Redirect the apex domain (`miladjavadi.com`) to `www`.

## Edit content

All text is in `index.html`. Each section starts with a comment, such as `<!-- Experience -->`.

- **Colors and fonts:** the tokens at the top of the `<style>` block (`:root`).
- **Share preview text:** the `og:` and `twitter:` meta tags in `<head>`.
- **Search data:** the JSON-LD block in `<head>`.

Keep every metric consistent with the current résumé.
