# Olla — taste, collected

A personal recipe notebook that runs as a web app on your phone: serving scaling, metric/US conversion, a check-off shopping list, favourites, and browsing by season and dish.

## What's in here

| File | What it does |
| --- | --- |
| `index.html` | The whole app: page, styles and code in one file |
| `recipes.json` | Every recipe, plus the app settings (`showSourceLink`) |
| `manifest.webmanifest` | Name, colours and icons for "Add to Home Screen" |
| `sw.js` | Offline support: the app and your recipes keep working without signal |
| `icons/` | The olla app icon in the sizes phones ask for |

## Put it online (GitHub Pages)

1. Upload all of these files to the root of the repo (keep the `icons` folder).
2. In the repo go to **Settings → Pages**, set **Source** to "Deploy from a branch", pick `main` and `/ (root)`, and save.
3. After a minute the app is at `https://<your-username>.github.io/<repo-name>/`.

GitHub Pages sites are public even when the repo is private (on paid plans you can restrict them). The URL is not listed anywhere, but anyone who has it can open the recipes.

## Put it on your phone

- **iPhone (Safari):** open the URL → Share → **Add to Home Screen**.
- **Android (Chrome):** open the URL → ⋮ menu → **Add to Home screen** / **Install app**.

It opens full screen like an app, with the olla icon.

## Where your data lives

- **Recipes** come from `recipes.json` in the repo. The same file goes to every device.
- **Favourites, the shopping list, recipes you tear out, and the source-link setting** are saved on each phone (in the browser's storage). They stay put through updates, but they don't sync between devices. Clearing Safari's or Chrome's website data wipes them.

## Adding recipes

Send the link to Claude in chat. Claude imports the recipe, runs the fidelity tests (nothing lost, nothing invented), and gives you an updated `recipes.json`, or commits it directly if the repo is connected. Reopen the app and the new recipe is there.

Importing and translating inside the app need Claude, so on the phone those buttons explain this instead of running.

## Updating the app itself

When `index.html` changes, also raise `VERSION` at the top of `sw.js` (e.g. `olla-1` → `olla-2`). Otherwise phones may keep showing the old copy from their offline cache.
