# ✨ AI BI Dashboard

Upload a CSV, describe the dashboard you want in plain text, and get an animated, branded dashboard: KPI cards, charts, tables, AI insights, DAX-style measures, custom colors and themes. It is a single static page (`index.html`) with no backend, so it runs on GitHub Pages for free.

## Features
- CSV upload, one-click **Auto-design**, or write your own prompt
- 29 color themes, custom palette, page / card / KPI / text / header colors
- Brand name and logo (a monogram is generated if you don’t upload one)
- DAX-style measures: `Margin = DIVIDE(SUM([Profit]),SUM([Revenue]))`
- Animations (`bounce`, `fade`, `zoom`, `slow`, `loop`, `no animation`…)
- Save as PNG, export a standalone live HTML, and **share a public view-only link**

## Prompt cheat sheet
```
title: Q3 Sales
galaxy theme, midnight mode, bounce animation
page background navy, card background white, KPI card background orange, text color white
Margin = DIVIDE(SUM([Profit]),SUM([Revenue]))
KPI cards for Revenue, Profit and Units
KPI Margin
Bar chart of Revenue by Region in red, blue, gold
Area chart of Profit by Month in teal
Donut chart of Units by Category
Table of Region, Category, Profit
AI insights
```

## Deploy on GitHub Pages
1. Create a new **public** repository on GitHub (for example `ai-bi-dashboard`).
2. Upload all files from this folder (or `git push`, see below).
3. Go to **Settings → Pages**. Under **Build and deployment** choose **Deploy from a branch**, branch **main**, folder **/ (root)**, then Save. (Or choose **GitHub Actions**; the included workflow deploys automatically.)
4. After about a minute your app is live at `https://<your-username>.github.io/ai-bi-dashboard/`.

```bash
git init
git add .
git commit -m "AI BI Dashboard"
git branch -M main
git remote add origin https://github.com/<your-username>/ai-bi-dashboard.git
git push -u origin main
```

## Share a live dashboard publicly
1. Build your dashboard in the deployed app.
2. Click **🌍 Share live link**, paste your GitHub Pages URL, and copy the link.
3. Anyone who opens it sees the animated dashboard in view-only mode. The data is packed inside the link; nothing is stored on a server.

For big datasets, use **⬇ Export live HTML**, commit the file as e.g. `sales.html` and share `https://<your-username>.github.io/ai-bi-dashboard/sales.html`.

> Anyone with a link can see the data inside it. Do not share confidential data.

## Limits
- The prompt is read by rules (patterns such as “bar chart of X by Y”), not a language model.
- Supported DAX: SUM, AVERAGE, MIN, MAX, COUNT, COUNTROWS, DISTINCTCOUNT, DIVIDE, IF, ROUND, ABS, CALCULATE (with filters and ALL).
- Uses CDN libraries (Chart.js, PapaParse, html2canvas) so it needs an internet connection.

## License
MIT

## Run locally (Antigravity / VS Code / any terminal)
```bash
npm start          # then open http://localhost:3000
```
No `npm install` is needed. You can also just double-click `index.html`. Try it with `sample-data.csv`.
