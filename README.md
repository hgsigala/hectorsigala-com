# hectorsigala.com

Personal site. Static HTML, deployed via Vercel's native GitHub integration.

## Structure

```
.
├── index.html              # Homepage
├── kids-training/          # Claude Code Sundays — lesson deck for Gael & Ivan
│   └── index.html
└── README.md
```

## Deploy

Push to `main` → Vercel auto-deploys (native GitHub integration, not GitHub Actions).

## Local preview

```
cd ~/Sites/hectorsigala-com
python3 -m http.server 8000
# open http://localhost:8000
```

Note: the deck uses `<base href="/kids-training/">`, so it expects to be served at `/kids-training/` — visit `http://localhost:8000/kids-training/` (with trailing slash) for it to find its assets correctly.
