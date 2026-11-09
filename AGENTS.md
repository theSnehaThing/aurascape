# AGENTS.md — aurascape (Aura & Scape website)

## One-liner
Astro + Tailwind static site for Aura & Scape (luxury Indian event decor),
deployed via Docker on `bugaboxes.local:8080`.

## Key files
- `TODO.md` / `REMAINING.md` — milestone status and open user tasks (read first).
- `MAINTAINERS.md` — non-technical editing guide; keep it accurate.
- `IMG_CREDITS.md` — placeholder image credits (CC). Do not drop credits when swapping photos.
- `src/pages/` — 5 pages: index, about, gallery, contact, privacy.
- `src/components/` — Header, Footer (contact info lives here too), gallery, lightbox.
- `public/assets/{gallery,hero}/` — current placeholders; real photos replace them in place.

## Brand
- Name "Aura & Scape"; byline Antima & Shilpa. Motto: "Where Memories Become Magic".
- Brand email is **hello@auranscape.co.uk** everywhere (footer, contact, privacy,
  JSON-LD). Don't reintroduce old domains/emails.
- Dark brand = navy #153552 lineage (see git history for token decisions).
- Copy tone: luxurious, romantic; site copy is English.

## Rules
1. Check `REMAINING.md` before claiming work is done; update it when state changes.
2. Contact form goes to FormSubmit — keep the working error state, don't "clean up" fallbacks.
3. SEO/structured data already audited (Lighthouse 98/96/100/100) — preserve meta/JSON-LD; run a production build (`npm run build`) before judging layout changes.
4. Keep the site buildable with only the two dependencies in package.json (astro, @astrojs/sitemap) — no new runtime deps without reason.
5. Deployment is the Docker image on bugaboxes (ports 8080:80); verify changes with the prod build, not dev server only.
