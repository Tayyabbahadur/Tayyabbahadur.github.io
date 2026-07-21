# Tayyab Bahadur — Portfolio

A single-page, dark-themed portfolio site built with plain HTML, CSS, and JavaScript (no build step, no framework).

## Structure

```
portfolio/
├── index.html
├── css/style.css
├── js/script.js
├── assets/          ← put your resume PDF and any images here
└── README.md
```

## 1. Preview it locally

```bash
cd portfolio
python3 -m http.server 8000
```

Then open http://localhost:8000 in your browser.

## 2. Connect the contact form (Formspree)

The form in the Contact section posts to Formspree so messages land in your inbox — no backend server needed.

1. Go to https://formspree.io and sign up (free) with `tayyabbahadur4@gmail.com`.
2. Create a new form and verify your email — Formspree will email you a confirmation link.
3. Copy the form endpoint it gives you, e.g. `https://formspree.io/f/abcd1234`.
4. Open [index.html](index.html) and find this line in the Contact section:
   ```html
   <form id="contactForm" class="contact-form reveal" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
5. Replace `YOUR_FORM_ID` with your real ID (e.g. `abcd1234`).

That's it — submissions will be emailed to you, and the page shows an inline success/error message without reloading. Formspree's free tier includes 50 submissions/month, which is plenty for a portfolio.

## 3. Add your resume

Drop your resume PDF into `assets/` and name it `Tayyab_Bahadur_Resume.pdf` (the "Download Resume" button in the hero already points to that path). If you use a different filename, update the `href` in [index.html](index.html).

## 4. Add your real social links

In [index.html](index.html), find the social buttons in the Contact section and replace the placeholder `href="#"` with your actual profile URLs:

```html
<a href="https://linkedin.com/in/your-handle" class="social-btn" data-social="linkedin">LinkedIn</a>
<a href="https://github.com/your-handle" class="social-btn" data-social="github">GitHub</a>
```

Also update the `LinkedIn` / `GitHub` links at the top of the resume-derived header if you add them elsewhere.

## 5. Deploy

Any static host works since there's no build step:

- **GitHub Pages** — push this folder to a repo, enable Pages on the `main` branch.
- **Netlify / Vercel** — drag-and-drop the folder or connect the repo; no build command needed.

## Customizing

- Colors, spacing, and fonts are controlled by CSS variables at the top of [css/style.css](css/style.css) (`:root { ... }`).
- Section content lives directly in [index.html](index.html) — each section is clearly commented (`<!-- HERO -->`, `<!-- PROJECTS -->`, etc.).
