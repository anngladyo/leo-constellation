# Constellation of You — Leo

An interactive Leo constellation experience. Tap a star, discover a piece of
yourself (your song, your animal, your flower...), and let the music carry
you through the rest of the checkpoints.

## Status: early MVP / interactive prototype

This is a working front-end prototype, not the production app. It exists to
test the interaction model (tap-to-reveal, the song-on-first-tap flow,
constellation layout) before investing in the full 3D asset pipeline.

## Files

```
index.html              → the main prototype: Leo constellation + reveal sheet
assets/
  joycelyn_s_dance.mp3   → the "Song" checkpoint track (starts at 0:33 on tap)
deer-3d-demo.html        → standalone rotatable 3D deer proof-of-concept
                            (drag/pinch/scroll), separate from the main flow —
                            shows how a real generated 3D asset would drop in
```

## How to test locally

Just open `index.html` in a browser — no build step, no server required.
Everything is self-contained except the MP3, which must stay in `assets/`
relative to `index.html`.

On iPhone: AirDrop or transfer the whole folder, then open `index.html` in
Safari specifically (not an in-app browser) — the song only starts because
tapping the star is a direct user gesture, which iOS requires for audio
autoplay.

## How to test on a real URL (recommended)

Once this is pushed to GitHub, turn on **GitHub Pages**:

1. Repo → Settings → Pages
2. Source: Deploy from a branch → `main` → `/ (root)`
3. Save — GitHub gives you a URL like
   `https://yourusername.github.io/leo-constellation/`

That URL works on any device, no file transfer needed — just open it in
Safari on your phone. This is the easiest way to test on-device from here on.

## What's placeholder right now

- 14 of the 20 checkpoint categories in the `CHECKPOINTS` array (top of the
  `<script>` in `index.html`) are stand-ins — only Song, Animal, Flower,
  Insect, Cocktail, and Perfume reflect the real mapping so far.
- The "3D reveal" slot in the reveal sheet is inert — it's where a real
  GLB model viewer will render per checkpoint once assets are generated
  (see `deer-3d-demo.html` for how that interaction should feel).
- Star x/y positions were hand-measured off the lion illustration and may
  need small nudges once tested on a real device.

## Next steps

- Fill in the remaining 14 checkpoint categories + values
- Generate real 3D assets per checkpoint (image-to-3D from reference sheets)
- Replace the inert viewer slot with a real GLB/Three.js viewer per checkpoint
- Test tap targets and layout on actual iPhone/iPad hardware
