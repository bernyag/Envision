# Envision
Envision Digital Agency Home Repo

Static site hosted on Vercel: `index.html` (English) and `es/index.html` (Spanish).

## Editing

`index.html` is the only file to edit by hand. Spanish text lives next to the English as attributes:

- `data-es="..."` replaces the element's content
- `data-es-<attr>="..."` replaces an attribute (`data-es-href`, `data-es-placeholder`, `data-es-content`, ...)

After any change, regenerate the Spanish page and commit both files:

```bash
python3 scripts/build_es.py
```

## Configuration

At the top of the `<script>` block at the bottom of `index.html`:

- `CONFIG.formEndpoint`: Formspree endpoint (e.g. `https://formspree.io/f/abcd1234`). Until set, the contact form opens the visitor's email app with the message pre-filled.
- `CONFIG.ga4Id`: Google Analytics 4 measurement ID (`G-XXXXXXXXXX`). Tracked events: `generate_lead`, `book_call` (Calendly booking), `cta_book`, `click_whatsapp`, `click_email`, `click_phone`.

The site URL (`https://envision-one-alpha.vercel.app`) is used in the `<head>` tags, JSON-LD, `robots.txt` and `sitemap.xml`. Replace it everywhere when you move to a custom domain.

## Assets

- `assets/projects/*.jpg`: portfolio screenshots (800px wide)
- `assets/team/*.jpg`: team photos
- `assets/og-image.jpg`: 1200×630 social preview image
