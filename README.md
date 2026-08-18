# Vithal Life Science — Website

A single-file static website (`index.html`, with CSS/JS embedded inside it).
No build step, no dependencies — just open it and it works.

## 1. Open the project in VS Code

1. Put `index.html` in its own folder, e.g. `vithal-site/`.
2. Open VS Code → **File → Open Folder…** → select `vithal-site/`.
3. You should see `index.html` in the Explorer panel on the left.

## 2. Easiest way to view it: just open the file

- In VS Code's Explorer, right-click `index.html` → **"Reveal in File Explorer / Finder"**,
  then double-click the file to open it in your default browser.
- Or drag `index.html` straight into any open Chrome/Firefox/Edge window.

This works fine for this site since everything (CSS, JS, fonts via CDN) is self-contained
in one file. The only limitation: some browsers restrict certain features (like
`fetch`/`localStorage`) when opened via `file://` — this site doesn't use those, so you're safe.

## 3. Recommended: run a local server (closer to "real" web hosting)

Running through a local server avoids `file://` quirks and lets you test on your phone
too (via your computer's local IP). Pick ONE of these:

### Option A — VS Code "Live Server" extension (easiest, no terminal needed)
1. In VS Code, go to the Extensions panel (left sidebar, or `Ctrl+Shift+X` / `Cmd+Shift+X`).
2. Search for **"Live Server"** by Ritwick Dey → click **Install**.
3. Right-click `index.html` in the Explorer → **"Open with Live Server"**.
4. Your browser opens automatically at something like `http://127.0.0.1:5500/index.html`.
5. Live Server auto-reloads the page whenever you save changes to the file. 

### Option B — Python's built-in server (no extensions needed)
Open the VS Code integrated terminal (`` Ctrl+` `` / `` Cmd+` ``) and run:

```bash
cd vithal-site
python3 -m http.server 8000
```

Then open your browser to:

```
http://localhost:8000
```

(Windows users without `python3` on PATH may need `python -m http.server 8000` instead.)

### Option C — Node's `serve` package
If you have Node.js installed:

```bash
cd vithal-site
npx serve .
```

It will print a local URL (usually `http://localhost:3000`) — open that in your browser.

## 4. Making edits

- All HTML structure, CSS (inside the `<style>` tag), and JS (inside the `<script>` tag)
  live in `index.html` — there's nothing else to configure.
- If you're using Live Server, just save the file (`Ctrl+S` / `Cmd+S`) and the browser
  tab refreshes automatically.
- If you're using `http.server` or `serve`, just refresh the browser tab manually after saving.

## 5. Publishing it for real (optional, when you're ready)

Once you're happy with it locally, you can put it online for free with any of these
(no backend needed since it's a static file):

- **GitHub Pages** — push this folder to a GitHub repo, enable Pages in repo Settings.
- **Netlify / Vercel** — drag-and-drop the folder onto their web dashboard (Netlify Drop
  is the fastest: netlify.com/drop).
- **Cloudflare Pages** — connect a GitHub repo or drag-and-drop upload.

Any of these will give you a live public URL in a couple of minutes.
