# memeworks-landing

Marketing landing page for MemeWorks. Single static `index.html` with all assets currently CDN-hosted (Tailwind, Inter, FontAwesome, GSAP, Lenis).

## Structure

```
.
├── index.html      # the page
├── assets/         # local images / CSS / JS (currently empty — all assets are CDN)
├── .gitignore
└── README.md
```

## Local preview

Any static server works. Examples:

```bash
python3 -m http.server 8000
# or
npx serve .
```

Then open http://localhost:8000.

## Deploy — Cloudflare Pages

### Option A: Git integration (recommended)

1. Cloudflare dashboard → **Workers & Pages** → **Create** → **Pages** → **Connect to Git**.
2. Select the `memeworks-landing` repo.
3. Build settings:
   - **Framework preset:** None
   - **Build command:** *(leave blank)*
   - **Build output directory:** `/`
4. Save & deploy. Subsequent pushes to `main` auto-deploy.

### Option B: Wrangler CLI (one-off)

```bash
npx wrangler pages deploy . --project-name=memeworks-landing
```

## Notes

- All third-party assets load from CDN — no build step required.
- `assets/` is reserved for any local images / CSS / JS added later.
