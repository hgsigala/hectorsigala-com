# hectorsigala.com

Personal site. Static HTML, deployed via **GitHub Actions + Vercel CLI** (Pattern A from the team deploy guide). The native Vercel↔GitHub integration is intentionally disconnected — see the 2026-05-23 silent-deploy incident for context.

## Structure

```
.
├── index.html                  # Homepage
├── kids-training/              # Claude Code Sundays
│   ├── index.html              # Landing page — all decks + teacher guide link
│   ├── favicon.png             # Shared deck favicon
│   ├── wk1/index.html          # Week 1 deck — Hello, Claude Code (May 17, 2026)
│   └── wk2/index.html          # Week 2 deck — On the internet (May 24, 2026)
├── teachers/index.html         # Teacher guide (noindex)
├── .github/workflows/deploy.yml  # Pattern A deploy workflow
└── README.md
```

## Deploy

Push to `main` → GitHub Actions runs `vercel deploy --prod` → live in ~30s. Required repo secrets: `VERCEL_TOKEN`, `VERCEL_ORG_ID`, `VERCEL_PROJECT_ID` (all 3 at repo level for personal accounts).

## Local preview

```
cd ~/Sites/hectorsigala-com
python3 -m http.server 8000
# open http://localhost:8000
```

Decks use absolute paths (`/kids-training/favicon.png`) so they work served from any subdir.
