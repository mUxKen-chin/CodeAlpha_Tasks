# Aurum — Premium Music Player

A single-file, browser-based music player with a vinyl-record theme, built with plain HTML, CSS, and JavaScript. No build step, no dependencies, no backend — open the file and it works.

## Features

- **Playback controls** — play, pause, next, previous, shuffle, and 3-state repeat (off / repeat all / repeat one)
- **Now playing display** — track title, artist, and live progress bar with drag-to-seek
- **Volume control** — custom slider wired directly to the audio element
- **Playlist / queue** — click any track to jump to it, remove tracks, live "now playing" indicator with an animated equalizer icon
- **Autoplay** — toggle whether the next track starts automatically when one ends
- **Import your own music** — add local audio files via a file picker or drag-and-drop; reads duration automatically and parses "Artist - Title" style filenames
- **Vinyl-style visual centerpiece** — the album art is a spinning record with a tonearm that lifts and drops as you play/pause
- **Keyboard shortcuts** — `Space` to play/pause, `←` / `→` for previous/next
- **Fully responsive** — fixed-width sticky player panel on desktop, stacked full-page layout on mobile

## Getting Started

1. Download `premium-music-player.html`
2. Open it in any modern browser (Chrome, Edge, Firefox, Safari)
3. Click **Import** (or drag files onto the playlist panel) and choose audio files from your device — MP3, WAV, M4A, or any format your browser supports
4. Click a track in the playlist to start listening

No installation, server, or internet connection is required to play music (an internet connection is only used to load the Google Fonts used for styling).

## Project Structure

This is a single self-contained file:

```
premium-music-player.html   # HTML structure, CSS styling, and JavaScript logic all in one file
```

## How Import Works

Audio files never leave your browser. When you import a file, the app creates a temporary local object URL (`URL.createObjectURL`) so the browser's built-in `<audio>` element can play it directly from disk. Nothing is uploaded anywhere.

## Tech Stack

- **HTML5** `<audio>` element for playback
- **CSS Grid** for the two-panel layout (sticky player + scrollable playlist)
- **Vanilla JavaScript** (no frameworks) for all interactivity
- **Google Fonts** — Fraunces (display), Inter (UI text), JetBrains Mono (time/data)

## Browser Support

Works in any modern, evergreen browser with support for the HTML5 Audio API, CSS Grid, and `URL.createObjectURL`. Recommended: latest Chrome, Edge, Firefox, or Safari.

## Notes & Limitations

- Playlists are **not saved** between sessions — reimport your files each time you open the app.
- Only works with audio files already on your device; there's no built-in music catalog or streaming source.
- File format support depends on your browser's native audio codec support.

## License

Free to use, modify, and extend for personal or commercial projects.
