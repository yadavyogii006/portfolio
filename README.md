# Portfolio

Static portfolio site for Yogesh Yadav — projects, demos, and experience.

## Structure

```
portfolio/
├── index.html          # Main page (loads data via JavaScript)
├── data/
│   ├── experience.json # Work history
│   └── projects.json   # Projects with links and demo videos
```

## Local development

Serve the folder over HTTP (required for JSON fetch):

```bash
cd portfolio
python -m http.server 8080
```

Open [http://localhost:8080](http://localhost:8080).

## Updating content

Edit the JSON files in `data/` — no build step required:

- **Experience:** `data/experience.json`
- **Projects:** `data/projects.json`

Each project supports `title`, `description`, `tech`, `liveUrl`, `githubUrl`, and `demoVideo` (YouTube embed URL).

## Deploy on Render

This repo includes a `render.yaml` blueprint for a **Static Site** (free tier, global CDN).

### Option A — Blueprint (recommended)

1. Push this repo to GitHub/GitLab.
2. In [Render Dashboard](https://dashboard.render.com/) → **New** → **Blueprint**.
3. Connect the repo — Render reads `render.yaml` automatically.
4. Click **Apply** — your site goes live at `https://portfolio.onrender.com` (name may vary).

### Option B — Manual static site

1. **New** → **Static Site** → connect your repo.
2. Use these settings:

   | Setting | Value |
   |---------|-------|
   | **Build Command** | *(leave empty)* |
   | **Publish Directory** | `.` |
   | **Environment** | `SKIP_INSTALL_DEPS=true` |

3. Click **Create Static Site**.

No build step or dependencies — Render serves `index.html` and the `data/` folder as-is.

## Updating content

Edit the JSON files in `data/` and push — Render redeploys automatically.
