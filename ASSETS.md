# Assets to drop in

The code references the following files. Until they exist the site shows a
styled placeholder (broken image for the profile, grey dashed boxes for the
videos). Everything else is text and already wired up.

## Required

| Target path | What goes there |
|---|---|
| `public/profile.jpg` | Your LinkedIn-style portrait. Square-ish, ≥ 512 × 512. |
| `public/logos/meta.svg` | ✅ provided (official Meta infinity mark). |
| `public/logos/ens.svg` | ⚠️ the provided one is a simple text mark. Replace with the real ENS logo if you want. |

## Paper videos / gifs

For each paper, save one short video or gif (looping, muted, ≤ 20 s,
≤ 4 MB is ideal). Tweet URLs are where the media originally lives — open
the tweet, right-click the video → "Save video" (or use `yt-dlp
https://x.com/...`).

| Target path | Tweet source |
|---|---|
| `public/media/papers/neuralset.mp4` | https://x.com/JeanRemiKing/status/1996131891129246038 |
| `public/media/papers/tribev2.mp4` | https://x.com/JeanRemiKing/status/2046564223417811217 |
| `public/media/papers/dinov3-brain.mp4` | https://x.com/JeanRemiKing/status/1962453435199983982 |
| `public/media/papers/scaling-context.mp4` | https://x.com/stephanedascoli/status/2037159637976318338 |
| `public/media/papers/hierarchical-inference.png` | (optional — a key figure from the 2024 paper) |

If a given tweet has a still image rather than a video, save it as `.png`
or `.jpg` instead and change the `media.type` to `"image"` in
`src/pages/index.astro`.

## Talk thumbnails / recordings

| Target path | Source |
|---|---|
| `public/media/talks/genai-workshop.jpg` | Screenshot of https://genai-conference-website.vercel.app/ |
| `public/media/talks/main.jpg` | Thumbnail or poster from the MAIN talk |
| `public/media/talks/neurips-dinov3.mp4` | Short clip from https://next.frame.io/share/2878ed20-48ea-43d9-8f82-4a21807938a5/view/579b34d6-bcb2-4326-a04d-ac6bc10ebfa7 |
| `public/media/talks/ccn.jpg` | Thumbnail from CCN talk |

## How to download a tweet video via `yt-dlp`

```bash
# one-time
pip install yt-dlp
# then
yt-dlp -o public/media/papers/neuralset.mp4 \
  "https://x.com/JeanRemiKing/status/1996131891129246038"
```

After adding the files, just run `npm run build` (or push to `main` to
re-deploy).
