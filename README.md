# Grand Tour itinerary — phone app

Everything in this folder is ready to publish. Nothing to build, no dependencies.

## Publish it (about two minutes)

1. On GitHub, create a new **public** repo called `grand-tour`.
2. Upload the contents of this folder to the repo root — `index.html`, `sw.js`,
   `manifest.webmanifest`, the four PNGs and `.nojekyll`. Drag-and-drop in the browser
   works fine; no git needed.
3. Repo → **Settings → Pages** → Source: *Deploy from a branch* → Branch: `main`, folder `/ (root)` → Save.
4. Wait a minute, then open **https://nucleus.github.io/grand-tour/**

All paths are relative, so it also works unchanged if you name the repo
`nucleus.github.io` instead — it would then live at `https://nucleus.github.io/`.

## Install it on the phone

Open that URL in Chrome on the Galaxy → menu (⋮) → **Add to Home screen** / **Install app**.

You get an icon, it opens without browser chrome, and because of the service worker the
whole itinerary is cached on first load — so it opens with no signal at all.

## Offline, honestly

- **The itinerary itself works fully offline** once you've opened it once with signal.
  Do that at home before you fly.
- **The map links do not.** Tapping a route or a Maps pin hands off to Google Maps,
  which needs either signal or pre-downloaded maps. Before you go, open Google Maps →
  profile → *Offline maps* → download a region covering Switzerland. On the Furka and in
  the Mesolcina you will otherwise have nothing.

## If you change the itinerary later

Re-copy `../grand_tour_itinerary.html` over `index.html`, re-add the two blocks
(`<link rel="manifest">` etc. before `</head>`, and the service-worker `<script>`
before `</body>`), bump `CACHE = 'grand-tour-v1'` to `v2` in `sw.js`, and re-upload.
The version bump is what makes phones pick up the new copy.

## One thing to be aware of

GitHub Pages on a free account serves from a **public** repo, so the URL is reachable by
anyone who has it. It isn't indexed or linked from anywhere, but it does contain your
dates and the hotel you're in each night. If that bothers you, use the PDF route instead
and skip hosting altogether.
