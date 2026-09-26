# Aura & Scape — Remaining Work

**Status:** Site is built, committed, and **deployed** on bugaboxes.local (Docker, port 8080).

---

## ✅ Done

- [x] Full site built (Astro + Tailwind)
- [x] All 5 pages: Home, About, Gallery, Contact, Privacy
- [x] SEO: meta tags, structured data, sitemap, robots.txt
- [x] Cookie consent + Privacy policy
- [x] Responsive layout with mobile nav
- [x] Gallery with filters + lightbox
- [x] Contact form (Formspree-ready)
- [x] Testimonials section
- [x] Journey timeline on About
- [x] Docker deployment on bugaboxes.local:8080
- [x] MAINTAINERS.md for non-technical team

---

## User Tasks (need Antima/Shilpa)

| Task | Where | Time |
|------|-------|------|
| Replace placeholder SVGs with real photos | `public/assets/gallery/` + `public/assets/hero/` | 30 min |
| Sign up at formspree.io, paste form ID | `src/pages/contact.astro` (search `YOUR_FORM_ID`) | 5 min |
| Add real phone number | `src/components/Footer.astro` + `src/pages/contact.astro` | 2 min |
| Add real email if not using hello@aurascape.in | Same files | 1 min |

After changes: rebuild + redeploy:
```bash
cd ~/github/aurascape && npm run build
scp -r dist/* smanna@bugaboxes.local:~/github/aurascape/
# Container auto-serves new files (mounted volume)
```

---

## Dev Tasks

| Priority | Task | Notes |
|----------|------|-------|
| HIGH | Push to GitHub | `git push -u origin main` (create repo first on GitHub) |
| MED | Lighthouse audit | Run on http://bugaboxes.local:8080, target 90+ |
| MED | Responsive QA | Visual check at 320/390/768/1440 |
| LOW | Map embed on contact | Google Maps iframe |
| LOW | Replace placeholder testimonials | After first real clients |

---

## Deployment Info

```
Server:     bugaboxes.local
Path:       ~/github/aurascape/
Method:     Docker (nginx:alpine)
Container:  aurascape-site
Port:       8080 → 80
Config:     ~/github/aurascape/nginx.conf
Auto-restart: yes
URL:        http://bugaboxes.local:8080
```

### To stop/restart:
```bash
ssh smanna@bugaboxes.local "docker restart aurascape-site"
ssh smanna@bugaboxes.local "docker stop aurascape-site && docker rm aurascape-site"
```

### To change port (e.g., to 80):
```bash
ssh smanna@bugaboxes.local "docker stop aurascape-site && docker rm aurascape-site"
ssh smanna@bugaboxes.local "docker run -d --name aurascape-site --restart unless-stopped -p 80:80 -v ~/github/aurascape:/usr/share/nginx/html:ro -v ~/github/aurascape/nginx.conf:/etc/nginx/conf.d/default.conf:ro nginx:alpine"
```

---

## Quick Reference

```
Project:    ~/github/aurascape
Remote:     git@github.com:theSnehaThing/aurascape.git
Build:      npm run build → dist/
Deploy:     scp -r dist/* smanna@bugaboxes.local:~/github/aurascape/
Preview:    npm run dev → http://localhost:4321
Live:       http://bugaboxes.local:8080
Maintainer: MAINTAINERS.md (for non-technical team)
```
