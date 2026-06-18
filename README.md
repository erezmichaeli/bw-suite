# Bridgewise Support Suite

A suite of internal support tools hosted on GitHub Pages — no backend, no dependencies, just open the browser.

## Tools

| # | Tool | File | Description |
|---|------|------|-------------|
| 1 | Severity Calculator | `severity.html` | Classify escalations and Jira priorities. Detects strategic clients, persists client list in localStorage. |
| 2 | Bulk API Enricher | External (HuggingFace) | Multi-step API enrichment pipelines over CSV files. Link from suite homepage. |
| 3 | Investment Policy Builder | `policy.html` | Visual AND/OR policy rule builder with JSON output, presets, and import/export. |

## Hosting on GitHub Pages

1. Create a repo (e.g. `your-org/bw-support-suite`)
2. Push these files to the `main` branch (or a `gh-pages` branch)
3. In GitHub → Settings → Pages → Source → `main` / `root`
4. Your suite will be live at `https://your-org.github.io/bw-support-suite/`

## Updating the HuggingFace Link

In `index.html`, replace `https://huggingface.co/spaces/YOUR_HF_SPACE` with your actual HuggingFace Space URL.

## File Structure

```
index.html          ← Suite landing page
severity.html       ← Tool 1: Severity Calculator
policy.html         ← Tool 3: Investment Policy Builder
README.md
```

## Local Development

No build step — just open `index.html` in a browser, or run a local server:

```bash
npx serve .
# or
python3 -m http.server 8080
```

## What's New vs Previous Versions

### Severity Calculator
- **Client CRUD** — add, remove clients via "Manage Clients" modal
- **Strategic flag** — toggle any client as strategic; persists in localStorage
- **localStorage persistence** — client list survives page reloads
- Copy-to-clipboard summary instead of screenshot (more reliable)
- Cleaner layout with nav back to suite

### Investment Policy Builder
- **5 built-in presets** — Large Cap US, Mid Cap EU, Exclude Non-Liquid, Index Members, TASE Domestic
- **Import JSON** — paste a previous export to reload a policy
- **Export / Download** — save `bw-policy.json` to disk
- Syntax-highlighted JSON output pane
- Live stats (groups, rules, valid count)

### Suite Landing Page
- Single hub linking all three tools
- Color-coded cards per tool
