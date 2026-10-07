# Capstone Radar

A reading feed of papers and engineering news to help choose an EE capstone project.
Each item has a summary, topics, techniques, proposed future research, why it fits,
and an undergrad feasibility rating. Rate items ★ / ? / ✕ and keep notes.

It's a Progressive Web App: host it on GitHub Pages and add it to your iPad Home Screen
to run it full-screen and offline.

## Put it on GitHub Pages

1. Create a repository on github.com (this one is `gabrielawr/CapstoneRadar`).
2. Upload every file in this folder, keeping the folders (`data/`, `icons/`).
   On github.com: **Add file → Upload files**, then drag the whole folder contents in.
3. Go to **Settings → Pages**. Under *Build and deployment* choose
   **Deploy from a branch**, branch `main`, folder `/ (root)`, then **Save**.
4. After a minute your app is at `https://gabrielawr.github.io/CapstoneRadar/`.

## Install on iPad

1. Open that address in **Safari**.
2. Tap **Share → Add to Home Screen → Add**.
3. Open it from the new *Radar* icon. It runs full-screen, without Safari's bars.

## Where things live

| What | File | Who changes it |
|---|---|---|
| Reading list | `data/items.json` | The weekly update (or you) |
| Project sketches | `data/ideas.json` | The weekly update |
| Last / next update dates | `data/meta.json` | The weekly update |
| Your ratings and notes | Your iPad (browser storage) | You, in the app |

Ratings stay on the device. Use **Back up ratings** in the app to copy them, then paste
them into your Claude chat (so the weekly search learns what you like) or import them on
another device.

## Adding new items

Each new item is one object in `data/items.json` with these fields:
`id, theme (vision | wireless | neural | imaging | hci | robotics | audio | impact), kind, source, date, added,
title, authors, url, summary, fit, terms[{term, meaning}], topics[], techniques[], future[],
futureFrom ("paper" | "inferred"), feasibility (1–3), needs`.

After you change files, the app picks up new data the next time it opens online.
If you change `index.html` or `sw.js`, bump `CACHE` in `sw.js` (e.g. `radar-v2`) so the
installed app refreshes.
