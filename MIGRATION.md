# Project Code Red Migration Guide

This site is now prepared to move off GoDaddy Website Builder and deploy on Vercel while keeping the `projectcodered.com` domain registered at GoDaddy.

## Recommended stack

- Code lives in GitHub
- Hosting and deploy previews live in Vercel
- Domain registration stays at GoDaddy
- DNS is updated in GoDaddy to point the domain to Vercel

## Why this setup

- You keep ownership of the existing domain
- The website becomes code-based and much easier to iterate on
- Every future change can be versioned
- Vercel gives fast previews and painless rollbacks

## Files already prepared

- Static pages live at the project root
- Shared styling is in `styles.css`
- Shared client behavior is in `script.js`
- Images are local in `assets/images`
- `vercel.json` is included for a clean static deploy

## Current route mapping

The site is set up to preserve the original public URLs:

- `/`
- `/about`
- `/our-team`
- `/events`
- `/merch`
- `/contact-us`

## Migration steps

### 1. Create a GitHub repository

- Create a new GitHub repo, such as `projectcodered-site`
- Upload all files from this folder to that repo

### 2. Import the repo into Vercel

- Sign in to Vercel
- Select `Add New...` then `Project`
- Import the GitHub repo
- Deploy it as a static site

Vercel should detect this as a simple static project because there is no framework build step.

### 3. Add the custom domain in Vercel

- In the Vercel project dashboard, open `Settings`
- Open `Domains`
- Add:
  - `projectcodered.com`
  - `www.projectcodered.com`

Vercel will show you the exact DNS records it expects.

## GoDaddy DNS update

Keep the domain at GoDaddy. Do not transfer the domain unless you explicitly want a registrar change.

In GoDaddy DNS:

- Update only the records Vercel tells you to change for the website
- Leave email-related records alone unless you are also migrating email

That means you should usually keep existing records like:

- MX
- SPF TXT
- DKIM CNAME or TXT
- DMARC TXT
- other non-website verification records

## Low-risk cutover order

1. Deploy to Vercel on the temporary Vercel URL
2. Review the site there first
3. Add the custom domain in Vercel
4. Update GoDaddy DNS with the records Vercel gives you
5. Wait for propagation
6. Re-test the live domain

## Important note about the contact form

The old live contact form is managed by GoDaddy Website Builder. If you move fully off Website Builder, that form will not come with it automatically.

Your next recommended step is to connect a form provider such as:

- Formspree
- Basin
- Tally + automation
- a serverless form endpoint later

## Suggested next tasks

- Connect a custom domain in Vercel
- Add a real contact form provider
- Add analytics in the new stack
- Add an editable content workflow later if needed
