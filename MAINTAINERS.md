# Aura & Scape Website — Maintainer Guide

This guide is for non-technical team members. You don't need to know code to update this site.

## Quick Reference

| Task | What to do |
|------|-----------|
| Add a photo to gallery | Drop image in `public/assets/gallery/`, add entry in gallery page |
| Change text/copy | Edit the `.astro` file for that page |
| Change a phone/email | Edit `src/components/Footer.astro` and `src/pages/contact.astro` |
| Update services | Edit `src/pages/index.astro` (the "What We Do" section) |
| Deploy | `npm run build` → upload `dist/` folder to server |

## Folder Structure

```
aurascape/
├── public/
│   └── assets/
│       ├── gallery/      ← Put new event photos here
│       ├── hero/         ← Hero background, team photos
│       └── logos/        ← Logo files
├── src/
│   ├── pages/            ← One file per page
│   │   ├── index.astro   ← Home page
│   │   ├── about.astro   ← About Us
│   │   ├── gallery.astro ← Gallery
│   │   ├── contact.astro ← Contact form
│   │   └── privacy.astro ← Privacy policy
│   ├── components/       ← Shared pieces (header, footer)
│   └── layouts/          ← Page wrapper (SEO, meta tags)
├── Dockerfile            ← For deploying to server
└── docker-compose.yml
```

## How to Add a New Photo to the Gallery

1. Take a photo of your event
2. Resize it to ~600×400px (any image editor, or even phone)
3. Save it as `public/assets/gallery/13.jpg` (next number)
4. Open `src/pages/gallery.astro` in any text editor
5. Add a new line in the `galleryItems` list:
   ```
   { src: '/assets/gallery/13.jpg', alt: 'Description of what the photo shows', category: 'wedding' },
   ```
   - `category` can be: `wedding`, `corporate`, or `private`
   - `alt` is important for SEO — describe the photo in words
6. Rebuild: `npm run build`
7. Deploy (see below)

## How to Update Text

Every page is a `.astro` file. Open it in any text editor (VS Code, Notepad++, even Notepad).

The text you see between HTML tags is what appears on the site. Just change the words.

Example:
```
<p class="text-forest/70">
  From dreamy backdrops to statement décor...
</p>
```

Change the text between `<p>` and `</p>`.

**Warning:** Don't delete the angle brackets or the stuff inside them (`class="..."`). Only change the visible text.

## How to Deploy

### Option A: Via the server (bugaboxes)

```bash
# On your machine:
cd aurascape
npm run build
# This creates a /dist folder with the final site

# Upload to server:
rsync -avz dist/ user@bugaboxes:/var/www/aurascape/

# Or via docker:
scp Dockerfile docker-compose.yml user@bugaboxes:/var/www/aurascape/
ssh user@bugaboxes "cd /var/www/aurascape && docker compose up -d"
```

### Option B: Any static hosting

The `dist/` folder after `npm run build` is just HTML, CSS, and images.
You can upload it to any web server (nginx, Apache, Cloudflare Pages, etc.).

## Updating the Contact Form

The form currently uses Formspree:

1. Go to [formspree.io](https://formspree.io) and sign up (free: 50 submissions/month)
2. Create a new form, point it to your email
3. Copy the form ID (looks like `xyzabcde`)
4. In `src/pages/contact.astro`, find:
   ```
   action="https://formspree.io/f/YOUR_FORM_ID"
   ```
5. Replace `YOUR_FORM_ID` with your actual form ID
6. Rebuild and deploy

## Tips

- **Alt text matters.** Every image needs an `alt` description. This helps Google understand your site.
- **File sizes.** Keep images under 200KB. Use [squoosh.app](https://squoosh.app) to compress.
- **Don't break the structure.** If you're unsure about editing a file, ask.
- **Test before deploying.** Run `npm run dev` to preview locally before going live.

## Commands You Might Need

```bash
npm install       # First time, or if something's broken
npm run dev       # Preview locally at http://localhost:4321
npm run build     # Create the final site in /dist
npm run preview   # Preview the built site
```

## Getting Help

If something breaks or you need a change:
- Email: hello@aurascape.in
- Or ask whoever set this up 🙂
