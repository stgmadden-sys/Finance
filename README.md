# Finance

Wealthr: a single-file static HTML personal finance app (no build step, no server).
All data is stored in the browser's localStorage, private to each device: new visitors go through a short setup and get their own empty planner (or can explore sample data), can protect it with a 4-digit PIN, and back it up or move it between devices with a backup file.

## Layout

- `index.html` – the whole app (HTML, CSS and JS in one file)
- `netlify.toml` – publishes the repo root and sets a CSP allowing Google Fonts,
  Chart.js from jsDelivr, and calls to `api.anthropic.com`

## Deploy to Netlify

Option A – Git (auto-deploys on every push):
1. Netlify → Add new site → Import an existing project → GitHub → this repo.
2. Leave the build command empty; the publish directory comes from `netlify.toml` (`.`).

Option B – CLI:
```bash
npm install -g netlify-cli
netlify login
netlify deploy --prod --dir .
```

## AI advisor

Inside claude.ai the advisor works automatically. On the deployed URL, enter an
Anthropic API key in the app's **Setup** tab (stored only in that browser's localStorage).
