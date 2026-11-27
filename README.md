# Tree Trunks: Cycle 5 lifting tracker

My own Cycle 5 training app, hosted free on GitHub Pages and installable on my phone's Home Screen. It works offline at the gym.

## What's in this folder

| File | What it does |
|---|---|
| `index.html` | The whole app: program, layout (HTML), styling (CSS) and behaviour (JavaScript) in one file |
| `manifest.webmanifest` | Tells the phone the app's name, icon and colours, which is what makes "Add to Home Screen" feel like a real app |
| `sw.js` | The **service worker**: a small script the browser runs in the background that saves a copy of the app so it opens with no signal |
| `icons/` | The Home Screen icons |

This kind of app is called a **PWA (progressive web app)**: a website that can install like an app.

---

## Part 1: Put it online (about 10 minutes, easiest on a computer)

1. **Make a GitHub account** at github.com (free).
2. **Create a repository** (a project folder on GitHub): click **+** (top right) → **New repository**.
   - Name: `tree-trunks`
   - Visibility: **Public**. Free GitHub Pages needs a public repo, so anyone could read this code. Your workout *logs* are never uploaded; they stay on your phone.
   - Tick **Add a README file**, then **Create repository**.
3. **Upload the files**: in the repo, click **Add file → Upload files**. Drag in everything from this folder, **including the `icons` folder**, so the structure matches the table above. Click **Commit changes**.
   - A **commit** is a saved snapshot of your files with a message. Every change you make becomes one.
4. **Turn on GitHub Pages**: repo **Settings → Pages**. Under *Build and deployment*, set Source to **Deploy from a branch**, Branch to **main**, folder **/ (root)**, then **Save**.
5. Wait a minute or two, then refresh that Settings page. It shows your site address:
   `https://YOUR-USERNAME.github.io/tree-trunks/`

## Part 2: Install it on your iPhone

1. Open that address in **Safari**.
2. Tap **Share** → **Add to Home Screen** → **Add**.
3. Open it from the new icon. It now runs full-screen, and after the first open it works without signal.

## Part 3: Your data

- Everything you tick and type is saved **in the browser on that phone** (a built-in browser feature called `localStorage`). There's no account and no server.
- Deleting the Home Screen icon or clearing Safari's website data erases it.
- **Back it up weekly:** Log tab → **Download .json**. To restore, or to move to a new phone: Log → **Import JSON**.
- At the end of the cycle, Log → **Copy log** and paste it into your next planning chat.

## Part 4: Changing the app (this is where the learning starts)

1. Edit a file on GitHub: open it → pencil icon → change → **Commit changes**. Pages republishes in about a minute.
2. **Every time you change something, open `sw.js` and bump `VERSION`** (`"v1"` → `"v2"`). Otherwise phones keep serving the old cached copy.
3. On the phone, close the app fully and reopen it, sometimes twice, to get the new version.

### Good first edits to try
- Change a cue: search `index.html` for `cue:` and rewrite one.
- Change a planned load: the top-set tables are near the top of the script, e.g. `const SQT=[325,330,...]` is the squat top set for Weeks 1–6.
- Change the colours: the `:root{ --bg: ... --acc: ... }` line at the top of the `<style>` block.

### Next steps when you want to go further
- **Edit on your computer instead of the website:** install **VS Code** and **GitHub Desktop**, "clone" (download) the repo, edit, then "push" (upload) your commits.
- **Preview before publishing:** in the folder, run `python3 -m http.server` and open `http://localhost:8000`.
- **Learn the three languages in order:** HTML (structure) → CSS (looks) → JavaScript (behaviour). MDN Web Docs (developer.mozilla.org) is the best free reference.
- **Bigger ideas:** sync between devices with a free Firebase or Supabase backend, or a screen where you type in your training maxes so friends can use it.
