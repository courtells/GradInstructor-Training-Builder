# Music Program TA Training

A self-contained, single-file training site for onboarding new teaching assistants in a music program. No build step, no dependencies, no backend — it's one HTML file that runs entirely in the browser.

## Features

- **Modular lessons** — organized as a sidebar list of short training modules, each with an estimated time and a progress tracker (saved locally in the browser).
- **In-browser content editor** — click "Edit content" to add, remove, reorder, and rewrite modules and content blocks directly on the page. No code required for day-to-day edits.
- **Block types**: heading (two levels), paragraph (with bold/italic/list formatting), bulleted/numbered lists, callouts, interactive checklists, quotes, multiple-choice knowledge checks (self-graded), embeds (e.g. a Google Form knowledge check), YouTube videos, images (with alt text), and dividers.
- **Export / Import** — save your edits as a code snippet you can paste back into the file to make them permanent, or re-import previously exported content to keep editing later or move it between browsers.
- **Accessible by design** — semantic landmarks, keyboard-operable controls, labeled form fields, sufficient color contrast, a skip link, and accessible modal dialogs.

## Getting started

### Option A — GitHub Pages (recommended)

1. Push this repo to GitHub.
2. Go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to "Deploy from a branch," choose the `main` branch and `/ (root)` folder, then save.
4. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/` within a minute or two.

### Option B — Open it locally

Just open `index.html` in any modern browser. No server or install needed.

## Editing content

- **In the browser**: click **"Edit content"** in the sidebar. Everything — module text, the sidebar title/subtitle, and every content block — can be added, rewritten, reordered, or deleted from there. Edits autosave to that browser's local storage.
- **Make edits permanent**: click **"Export code"** in the edit banner, copy the code shown, and paste it over the `SITE_SETTINGS` object and `MODULES` array near the top of the `<script>` section in `index.html`, then commit and push.
- **Pick up editing later / move between browsers**: click **"Import code"** and paste in a previously exported block.
- **Directly in code**: `index.html` contains inline documentation (a comment block right above `SITE_SETTINGS`) describing every field and block type if you'd rather hand-edit.

## File structure

```
.
├── index.html   # the entire site — content, styles, and logic
└── README.md    # this file
```

## Notes

- Progress tracking, quiz scores, and content edits made in Edit mode are stored in each visitor's browser (`localStorage`) — they are not shared across devices or visitors. Use Export/Import to move content between browsers, or edit the file directly and redeploy to change what everyone sees.
- The "embed" block is commonly used for a Google Form knowledge check at the end of training; see the in-file documentation for how to have Google Forms email respondents their score automatically.
