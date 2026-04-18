# Project Code Red Remodel

This folder contains a full static redesign for `projectcodered.com` built from the current live site's content and assets.

## Primary goal

Move the website off GoDaddy Website Builder and onto a code-friendly deployment flow while keeping the `projectcodered.com` domain registered at GoDaddy.

## Project files

- `index.html`
- `about.html`
- `team.html`
- `our-team.html`
- `events.html`
- `merch.html`
- `contact.html`
- `contact-us.html`
- `styles.css`
- `script.js`
- `vercel.json`
- `assets/images/`
- `MIGRATION.md`

## What changed

- Stronger homepage narrative and visual hierarchy
- Cleaner page structure for About, Team, Events, Merch, and Contact
- Modern typography, spacing, cards, gradients, and subtle motion
- Local copies of key brand and event images so the package is self-contained
- Existing mission, impact themes, certifications, team bios, and event content preserved and reorganized
- URLs prepared to preserve the current public route structure
- Vercel deployment config included

## Recommended publish path

- Keep the domain at GoDaddy
- Put the code in GitHub
- Deploy the repo on Vercel
- Point GoDaddy DNS to Vercel

Read [MIGRATION.md](./MIGRATION.md) for the actual cutover steps.

## Contact form note

The current live site's contact form is managed by GoDaddy Website Builder. This static remodel does not include a live form backend, so if you publish outside GoDaddy you will need to connect a form provider later.

## Local preview

If you have Python available, run:

```powershell
python -m http.server 8000
```

Then open:

`http://localhost:8000`
