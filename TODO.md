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

## TODO — Milestones (parallelizable)

### M1: Project Scaffold ✅ (done in this session)
- [x] Create folder
- [x] Init git + remote
- [x] Initialize Astro project
- [x] Tailwind CSS setup
- [x] Basic directory structure
- [x] Design tokens (CSS custom properties)

### M2: Layout & Shared Components
- [ ] Header with logo + nav (responsive)
- [ ] Footer (contact, social links, copyright)
- [ ] Cookie consent banner (GDPR-compliant)
- [ ] Mobile navigation (hamburger)
- [ ] Page layout wrapper (consistent spacing)

### M3: Home Page
- [ ] Hero section (brand image, tagline, CTA)
- [ ] "What we do" section (3-4 services)
- [ ] Featured gallery strip (3-4 images)
- [ ] Testimonials / social proof placeholder
- [ ] CTA section ("Plan your event")
- [ ] Footer

### M4: About Us Page
- [ ] Story section (Antima & Shilpa)
- [ ] Values / philosophy
- [ ] Team section (photos + bio)
- [ ] Journey / timeline
- [ ] CTA

### M5: Gallery Page
- [ ] Filterable grid (all / weddings / corporate / private)
- [ ] Lightbox (click to expand)
- [ ] Lazy loading
- [ ] Alt text for SEO
- [ ] Assets folder structure for adding photos

### M6: Contact Page
- [ ] Inquiry form (name, email, phone, event type, date, message)
- [ ] Form validation (client-side)
- [ ] Formspree integration (email to their inbox)
- [ ] Contact info (phone, email, location)
- [ ] Map embed (optional)
- [ ] Social links

### M7: SEO & Performance
- [ ] Meta tags (title, description, OG, Twitter card)
- [ ] Structured data (JSON-LD: LocalBusiness)
- [ ] Sitemap.xml
- [ ] robots.txt
- [ ] Semantic HTML (h1, h2, article, etc.)
- [ ] Image optimization (alt, loading, dimensions)
- [ ] Favicon + apple-touch-icon
- [ ] Lighthouse score target: 90+

### M8: Cookie & Privacy Compliance
- [ ] Cookie consent banner (accept/reject)
- [ ] Privacy policy page (or section)
- [ ] Only load analytics after consent
- [ ] No user data stored without consent
- [ ] Clear language about what's collected

### M9: Assets & Content
- [ ] /public/assets/gallery/ — folder for event photos
- [ ] /public/assets/hero/ — hero images
- [ ] Free stock images for initial gallery (Unsplash/Pexels)
- [ ] Logo files (SVG + PNG)
- [ ] README for non-tech maintainers (how to add photos, edit text)

### M10: Deploy & Hosting
- [ ] Dockerfile (nginx serving static site)
- [ ] docker-compose.yml
- [ ] Deploy to bugaboxes
- [ ] Domain + SSL setup
- [ ] Build script (npm run build → serve dist/)

### M11: QA & Polish
- [ ] Responsive check (320/390/768/1440)
- [ ] Accessibility (contrast, alt text, keyboard nav)
- [ ] No horizontal overflow
- [ ] Cross-browser (Chrome, Safari, Firefox)
- [ ] Form works end-to-end
- [ ] Lighthouse audit
- [ ] Final visual review

## Parallelization Notes
- M2 (layout) blocks M3-M6 (pages need header/footer)
- M3, M4, M5, M6 can be built in parallel AFTER M2
- M7, M8 can be done in parallel with M3-M6
- M9 (assets) can be done at any time
- M10, M11 are final steps

## File Ownership (for parallel agents)
- Agent A: M2 (layout) + M6 (contact)
- Agent B: M3 (home) + M4 (about)
- Agent C: M5 (gallery) + M7 (SEO) + M8 (cookies)
- Agent D: M9 (assets) + M10 (deploy) + M11 (QA)
