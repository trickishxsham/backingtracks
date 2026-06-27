# IMPROVS2 Backing Tracks

Public track store for the IMPROVS2 app. The app reads `tracks.json` from this repo at
runtime, so **adding a track here makes it appear in the app with no app update**.

## How it works

- The app fetches the manifest from **raw** (always current):
  `https://raw.githubusercontent.com/trickishxsham/backingtracks/main/tracks.json`
- It streams each MP3 from **jsDelivr** (fast global CDN):
  `https://cdn.jsdelivr.net/gh/trickishxsham/backingtracks@main/tracks/<file>.mp3`

## Add a backing track

1. Drop the MP3 into the `tracks/` folder. Keep it under ~15 MB (use MP3, e.g. 192 kbps).
   Use a clean filename, lowercase, no spaces: `blues_shuffle_a_90.mp3`.
2. Add one entry to the `tracks` array in `tracks.json`:

   ```json
   {
     "id": "blues-shuffle-a-90",
     "title": "Blues Shuffle in A",
     "key": "A",
     "bpm": 90,
     "genre": "blues",
     "file": "tracks/blues_shuffle_a_90.mp3",
     "duration": 214
   }
   ```

3. Commit and push. New track shows in the app within minutes.

### Field notes
- `id` — unique, kebab-case. Never reuse.
- `key` / `bpm` — drive in-app filtering by what the player is practicing.
- `file` — path inside this repo.
- `duration` (seconds) and `notes` are optional.

## Rules
- MP3 only. No WAV (too large for the CDN, 20 MB/file jsDelivr limit).
- Only upload tracks you own or have the right to distribute.

## License
CC0-1.0 — public domain. See `LICENSE`.
