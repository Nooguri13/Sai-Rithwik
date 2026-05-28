# Sai Rithwik Nooguri — Netflix-style Portfolio

This is a Netflix-inspired portfolio site. Hero plays a background video; rows render dynamically from a single JSON file; clicking a card opens a modal with trailer/details/links.

## Structure

- `index.html` — App shell (hero, rows root, modal)
- `styles.css` — Netflix-like dark theme and layout
- `src/app.js` — Fetches JSON and renders UI, modal logic
- `data/content.json` — The single source of truth for all sections/items
- `assets/` — Thumbnails and MP4s you reference in JSON (add your own files)

## Edit Content

Update `data/content.json`. Example snippet:

```json
{
  "title": "Projects",
  "items": [
    {
      "title": "SMS Spam Detection",
      "thumbnail": "assets/proj_sms.jpg",
      "description": "Spam classifier using ML.",
      "video": "assets/proj_sms.mp4",
      "links": [{ "label": "GitHub", "url": "https://github.com/..." }]
    }
  ]
}
```

## Run locally

Because the site fetches `data/content.json`, you should serve files via a local server (not by double-clicking `index.html`). Options:

- VS Code extension: Live Server (Right-click `index.html` → "Open with Live Server").
- Python 3:

```powershell
cd "c:\Users\noogu\OneDrive - University of North Florida\Documents\GitHub\Sai-Rithwik"
python -m http.server 5173
# Then open http://localhost:5173 in your browser
```

## Notes

- Hero title is fixed to your name. The hero video and description come from the Home section's first item in `content.json`.
- The Contact row uses the same poster-style cards. Links open in a new tab, and the modal also shows them.
- Videos are set `autoplay` + `muted` for better compatibility.
