# miladjavadi.com

Personal landing site for Milad Javadi. It is a static site with no build step.

## Files

| File | Purpose |
|------|---------|
| `index.html` | The full landing page. CSS and JavaScript are inline. |
| `404.html` | "Page not found" page. |
| `favicon.svg`, `apple-touch-icon.png` | Browser and home-screen icons. |
| `og-image.png` | Preview image for LinkedIn, Slack, and other link shares (1200 x 630). |
| `portrait.jpg` | Hero photo (900 x 1125, 4:5). |
| `Milad_Javadi_Resume_Procurement_Category.pdf` | Downloadable résumé, linked from the nav and contact section. |
| `robots.txt`, `sitemap.xml` | Search engine files. |
| `CNAME` | Custom domain for GitHub Pages (`www.miladjavadi.com`). Other hosts ignore it. |

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
