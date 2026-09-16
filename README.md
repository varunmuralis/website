# varunmurali.com

Personal site. Plain HTML, no build step, no dependencies.

## Files

| File | What it is |
|---|---|
| `index.html` | The entire site. All CSS, JavaScript, and the resume image are inside this one file. |
| `varun-murali-resume.pdf` | Linked from the Resume section as "Open the PDF". Must stay in the same folder as `index.html`. |

## Deploying on Vercel

**Fastest, no Git:** go to vercel.com/drop and drag this whole folder into the browser. Name the project and deploy. Live in under a minute.

**Recommended, updates automatically:**

1. Create a new GitHub repository and upload `index.html` and the PDF to it.
2. In Vercel, click Add New, then Project, then import that repository.
3. Framework preset: **Other**. Leave the build command and output directory **empty**. This site has nothing to compile, and setting a build command is the usual reason a static deploy fails.
4. Deploy.

Every push to the repository redeploys the site from then on.

## Deploying on GitHub Pages instead

1. Name the repository `varun200.github.io`, substituting your username, and make it public.
2. Upload both files to the root.
3. Settings, then Pages. Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
4. Live at `https://varun200.github.io` in a few minutes.

## Custom domain

Buy the domain from Cloudflare Registrar or Namecheap, roughly $10 to $15 a year.

In Vercel, go to Settings, then Domains, add the domain, and create the DNS records Vercel shows you at your registrar. Use the values it displays rather than any found in a tutorial, since those change. HTTPS is issued automatically once DNS resolves.

## Change these once you are live

1. Search `index.html` for `varunmurali.com`. It appears four times in the document head and controls how the link previews on LinkedIn and iMessage. Replace with the real URL.
2. Search for `GitHub link coming soon`. Replace both placeholders with the real repository URLs for the messaging app and the bikeshare tool.
3. Add a `preview.png` at 1200 by 630 pixels next to `index.html`. A screenshot of the top of the site works. Without it, shared links show a bare text card.

## Editing the content

Everything is in `index.html` and readable top to bottom. Sections are marked with HTML comments: CAREER, STORY, CONTACT.

- **Colors** are CSS variables at the very top, in the `:root` block. Change `--bg` and `--navy` and the whole site follows. The dark mode palette is in the two blocks directly below it.
- **The Now section** carries a date. Update it when what you are working on changes, or delete the date line. A stale "now" page is worse than not having one.
- **The resume** is embedded as a base64 image inside the Resume section, so it displays without loading a file. If you update your resume, the PDF and that image both need replacing.

## Notes

The site works without JavaScript except for the navigation dropdowns. It supports light and dark mode automatically, and is tested down to 400 pixels wide.
