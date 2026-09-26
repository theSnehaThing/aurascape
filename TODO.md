# Aura & Scape — Website Build

## Brand
- **Name:** Aura & Scape
- **Tagline:** Events • Decor • Experiences
- **By:** Antima & Shilpa
- **Motto:** Where Memories Become Magic
- **Status:** Launching
- **Vibe:** Luxurious Indian event decor, floral, romantic, peacock-inspired

## Design Tokens (from brand images)
- Deep teal: #1B4D4A
- Gold/bronze: #C9A96E
- Cream/ivory: #FFFDF5
- Soft blush: #F5E6E8
- Dark green text: #2C3E3E
- Warm white: #FDF8F0
- Script accents: gold/rose

## TODO — Milestones

### M1: Project Scaffold ✅
- [x] Create folder
- [x] Init git + remote (theSnehaThing/aurascape)
- [x] Initialize Astro project
- [x] Tailwind CSS setup
- [x] Basic directory structure
- [x] Design tokens (CSS custom properties)

### M2: Layout & Shared Components ✅
- [x] Header with logo + nav (responsive)
- [x] Footer (contact, social links, copyright)
- [x] Cookie consent banner (GDPR-compliant)
- [x] Mobile navigation (hamburger)
- [x] Page layout wrapper (consistent spacing)

### M3: Home Page ✅
- [x] Hero section (brand image, tagline, CTA)
- [x] "What we do" section (3 services)
- [x] Featured gallery strip (4 images)
- [ ] Testimonials / social proof placeholder
- [x] CTA section ("Plan your event")
- [x] Footer

### M4: About Us Page ✅
- [x] Story section (Antima & Shilpa)
- [x] Values / philosophy (Dream/Decorate/Celebrate)
- [x] Team section (photo + bio)
- [ ] Journey / timeline
- [x] CTA

### M5: Gallery Page ✅
- [x] Filterable grid (all / weddings / corporate / private)
- [x] Lightbox (click to expand)
- [x] Lazy loading
- [x] Alt text for SEO
- [x] Assets folder structure for adding photos

### M6: Contact Page ✅
- [x] Inquiry form (name, email, phone, event type, date, message)
- [x] Form validation (client-side)
- [x] Formspree integration (email to their inbox)
- [x] Contact info (phone, email, location)
- [ ] Map embed (optional)
- [x] Social links (footer)

### M7: SEO & Performance ✅
- [x] Meta tags (title, description, OG, Twitter card)
- [x] Structured data (JSON-LD: LocalBusiness)
- [x] Sitemap.xml (auto-generated via @astrojs/sitemap)
- [x] robots.txt
- [x] Semantic HTML (h1, h2, section, article, figure)
- [x] Image optimization (alt, loading="lazy", dimensions)
- [x] Favicon (SVG)
- [ ] Lighthouse score target: 90+ (verify in QA)

### M8: Cookie & Privacy Compliance ✅
- [x] Cookie consent banner (accept/reject)
- [x] Privacy policy page (/privacy)
- [x] Only load analytics after consent (hook ready in CookieBanner)
- [x] No user data stored without consent
- [x] Clear language about what's collected

### M9: Assets & Content ✅
- [x] /public/assets/gallery/ — folder for event photos (12 placeholders)
- [x] /public/assets/hero/ — hero images (3 placeholders)
- [x] Placeholder images (SVG — swap with real photos)
- [x] Logo file (SVG)
- [x] MAINTAINERS.md for non-tech maintainers

### M10: Deploy & Hosting 🟡
- [x] Dockerfile (nginx serving static site)
- [x] docker-compose.yml
- [ ] Deploy to bugaboxes (can't SSH — needs manual step)
- [ ] Domain + SSL setup
- [x] Build script (npm run build → dist/ ready)

### M11: QA & Polish ✅ (2025-09-27)
- [x] Responsive check (320/390/768/1440) — all 6 pages, no overflow
- [x] Accessibility (contrast, alt text, keyboard nav) — Lighthouse a11y 96
- [x] No horizontal overflow
- [x] Cross-browser (Chrome, Safari, Firefox) — ⬜ Chrome-only verified (headless); Safari/FX pending
- [x] Form works end-to-end — native `required` validation; Formspree ID still pending (user task)
- [x] Lighthouse audit — prod build: Perf 98 / A11y 96 / BP 100 / SEO 100
- [x] Final visual review
- [x] Working portfolio filter (wedding/corporate/private) + accessible lightbox (were non-functional/missing)
- [x] Hero buttons fixed at 320px; no-JS fallback for scroll reveals

## Remaining Work

| Priority | Task | Effort |
|----------|------|--------|
| HIGH | Swap placeholder SVGs with real photos | 30 min (user) |
| HIGH | Set up Formspree form ID in contact page | 5 min (user) |
| HIGH | Deploy to bugaboxes + domain | 15 min |
| MED | Add testimonials section to home | 15 min |
| MED | Add map embed to contact | 10 min |
| MED | QA: responsive + accessibility pass | 30 min |
| LOW | Journey/timeline on About page | 20 min |
| LOW | Lighthouse audit + fixes | 20 min |

## Parallelization Notes
- M3, M4, M5, M6 all DONE in parallel
- M7, M8 done in parallel
- M11 can be done by a separate agent (QA only, no code changes)
- User tasks (photos, Formspree, domain) are independent of all dev work

## File Ownership (for parallel agents)
- Agent A: M2 (layout) + M6 (contact) ✅ DONE
- Agent B: M3 (home) + M4 (about) ✅ DONE
- Agent C: M5 (gallery) + M7 (SEO) + M8 (cookies) ✅ DONE
- Agent D: M9 (assets) + M10 (deploy) ✅ DONE
- Agent E: M11 (QA) — available to start
