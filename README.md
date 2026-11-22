# Pocket GBC

A Game Boy / Game Boy Color emulator that installs on your phone as a PWA.

- Open any `.gb`, `.gbc` or `.zip` ROM from your phone. Games stay in a library on the device.
- Touch controls: a D-pad you can slide your thumb across (diagonals work), A/B, Start/Select. In landscape the buttons sit over the screen, and you can set how see-through they are.
- Fast-forward: tap ▶▶ to turn it on or off, or hold it for a short burst. Speed can be 2×, 3×, 4× or 8×, with an option to mute while it runs.
- Save states: a quick slot plus 4 numbered slots, each with a screenshot. Export one slot or all of a game's saves to your phone's Files (`.gbcstate` / `.gbcbackup`) and import them back on any device.
- Battery saves (the game's own SAVE menu) are written automatically every few seconds and when you leave the app. You can export them as a `.sav` file.
- Works with Bluetooth controllers and a keyboard (arrow keys, X = A, Z = B, Enter = Start, Shift = Select, Space = fast-forward, P = quick save, L = quick load).
- Works offline once installed.

## Deploy (GitHub Pages)

1. Create a new repo (e.g. `pocket-gbc`) and upload every file in this folder to the root of the repo.
2. Go to Settings → Pages → Source: "Deploy from a branch", branch `main`, folder `/ (root)`.
3. Open `https://<your-username>.github.io/pocket-gbc/` on your phone.
   - iPhone: in Safari, tap Share → Add to Home Screen.
   - Android: in Chrome, tap ⋮ → Install app (or use the "Install app" button in the library).

Any static HTTPS host works (Netlify, Cloudflare Pages, Fly.io static). It must be HTTPS for install and offline play to work.

## Notes

- iPhone storage: iOS may clear a website's storage if you don't use it for a few weeks. Once the app is added to the Home Screen it's much safer, but export a backup now and then (Library → Back up everything).
- After you deploy an update, bump `CACHE` in `sw.js` (for example `pocket-gbc-v2`) so phones pick up the new files.
- Emulation is done by WasmBoy (GPL-3.0, see `WASMBOY-LICENSE.txt`).
