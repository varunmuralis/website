# varunmurali.com

Personal site for Varun Murali. Plain HTML, no build step, no dependencies, no framework.

## Files

| File | What it is |
|---|---|
| `index.html` | The entire site. CSS, JavaScript, the three photos, and the resume image are all inside this one file. |
| `varun-murali-resume.pdf` | Linked from the Resume section as "Open the PDF". Must stay in the same folder as `index.html`. |

That is everything. Nothing to install, nothing to compile.

## Deploying on Vercel

**Fastest, no Git:** go to vercel.com/drop and drag this folder into the browser. Name the project and deploy.

**Recommended, updates automatically:**

1. Create a GitHub repository and upload `index.html` and the PDF to the **root** of it, not inside a folder.
2. In Vercel: Add New, then Project, then import that repository.
3. Framework Preset: **Other**. Build Command: **empty**. Output Directory: **empty**. This is the step people get wrong. There is nothing to build, and setting a build command is the usual cause of a 404 after deploy.
4. Deploy.

Every push to the repository redeploys from then on.

### If you get a 404

1. Check the file is named exactly `index.html`. Browsers often save it as `index (1).html`, which will not serve as a homepage.
2. Check it sits at the repository root, not in a subfolder.
3. Check the build command and output directory are both empty.
4. Open the Deployments tab. If the latest run shows Error, the reason is at the bottom of the build log.

## Custom domain

Buy the domain from Cloudflare Registrar or Namecheap, roughly $10 to $15 a year. In Vercel: Settings, then Domains, add the domain, then create the DNS records Vercel displays at your registrar. Use the values Vercel shows rather than any from a tutorial, since they change. HTTPS is issued automatically once DNS resolves.

## Change these once you are live

1. Search `index.html` for `varunmurali.com`. It appears four times in the document head and controls how the link previews on LinkedIn and iMessage. Replace with your real URL.
2. Search for `GitHub link coming soon`. Replace both with the real repository URLs for the messaging app and the bikeshare tool.
3. Add a `preview.png` at 1200 by 630 pixels next to `index.html`. A screenshot of the landing screen works. Without it, shared links show a bare text card.

## How the site is built

**Four views, not one long scroll.** The landing screen shows only the name and intro. Career, Story, and Contact each swap in their own screen. Clicking the name in the corner returns home.

**Every view has a real URL:** `/#work`, `/#projects`, `/#toolkit`, `/#resume`, `/#story`, `/#origins`, `/#now`, `/#contact`. These are shareable and the browser back button works.

**Editing content.** Everything is in `index.html`, readable top to bottom, with HTML comments marking each view. Colors are CSS variables in the `:root` block at the very top; change `--bg`, `--navy`, and `--gold` and the whole site follows. The dark mode palette is in the two blocks directly below, and both need the same edit.

**The photos and the resume** are embedded as base64 images, which is why the file is around 960KB. If you replace your resume or a photo, both the PDF and the embedded image need updating.

**The Now section carries a date.** Update it when what you are working on changes, or delete the date line. A stale "now" page is worse than not having one.

## Tested

Routing across all four views, deep links, both dropdowns, keyboard navigation and Escape, light and dark mode, and phone width at 390 pixels with no horizontal scroll. No JavaScript errors. Reduced motion disables all animation.
