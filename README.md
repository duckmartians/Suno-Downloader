# Suno Downloader

**English** | [Tiếng Việt](README.vi.md)

Desktop app that downloads your songs from **suno.com** at **original quality** — one song, a whole playlist, a profile, or the explore page. Cover art comes along, and every file is verified before it is marked done.

![Main window](docs/screenshots/01-main.png)

## Features

- **Paste one link, get everything**: song · playlist · profile · explore page — the app scans it and shows you the list to pick from
- **Pick exactly what you want**: search the scanned list, select all / deselect, and songs you already have are tagged **Downloaded** so you don't grab them twice
- **Add first, download when ready**: links land in the queue — **Start / Pause / Stop** are separate buttons, nothing downloads until you say so
- **Formats & bitrate**: MP3 (320/256/192/128) · AAC `.m4a` (256/192/128) · **Opus `.opus`** (container swap, no re-encode) · FLAC · WAV · **Original** MP4/Opus, byte-for-byte untouched
- **Parallel queue**: 1–5 at a time, each row showing cover art, percentage, size and length
- **Every file verified**: the app re-reads the MP4 structure — exactly one init segment, no gaps between fragments, total length matching the metadata. Short or corrupt means **failed**, never a silent half-song
- **Survives a crash**: if the background browser dies mid-download, the song is retried automatically (up to 3 attempts) instead of failing
- **Cover art** saved next to the audio, same filename
- **Cookies for private songs**: paste ANY format — Netscape `cookies.txt`, browser-extension JSON, or a raw `a=1; b=2` header. The panel tells you whether the cookies are actually **signed in**
- **Proxy pool**: paste proxies in any shape (`host:port`, `user:pass@host:port`, `socks5://…`), save them to a list, and downloads rotate through it. Re-check tests each one and tags the dead ones
- **History**: everything you've downloaded, with size and date, searchable — this is what powers the *Downloaded* badge
- **Auto-update**: checks GitHub Releases, downloads and installs from inside the app
- **6 languages**: English · Tiếng Việt · 简体中文 · Español · Русский · العربية (right-to-left)

## Screenshots

| Pick songs from a scanned link | Queue, downloading |
|---|---|
| ![Select songs](docs/screenshots/02-scan.png) | ![Queue](docs/screenshots/03-queue.png) |

| Suno cookies (with login state) | Proxy pool |
|---|---|
| ![Cookies](docs/screenshots/04-cookies.png) | ![Proxy](docs/screenshots/05-proxy.png) |

| Download history | Right-to-left (العربية) |
|---|---|
| ![History](docs/screenshots/06-history.png) | ![RTL](docs/screenshots/07-rtl-arabic.png) |

## Install

Grab the latest from [Releases](https://github.com/duckmartians/Suno-Downloader/releases):

- **Windows**: `SunoDownloader-<version>-win-x64.exe`
- **macOS (Apple Silicon)**: `SunoDownloader-<version>-mac-arm64.dmg` — unsigned; on first open, right-click → **Open**, or run
  `xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"`

You need a **G-Labs account with an active Suno plan**. Sign in with Google inside the app; a plan can be bought from the app itself (bank QR, PayPal, or USDT). One account works on **one machine at a time** — signing in elsewhere signs the previous machine out.

## How to use

### 1. Sign in

Open the app and sign in with Google. The badge in the title bar shows your plan's end date (`✓ 30/06/2027`). Click it any time to check or renew.

### 2. Paste a link and scan

Paste any of these into the box at the top left, then press **Scan**:

| Link | What you get |
|---|---|
| `https://suno.com/song/<id>` | that one song |
| `https://suno.com/playlist/<id>` | every song in the playlist |
| `https://suno.com/@<user>` | that profile's songs |
| `https://suno.com/explore` | what's on the explore page |

Large pages take around 30 seconds — the app scrolls the page itself to load every song. Press **Cancel** to stop.

### 3. Pick songs

![Select songs](docs/screenshots/02-scan.png)

The list opens with everything ticked. Type in the search box to narrow it, use **Select all / Deselect**, and note the green **Downloaded** tag — those are already in your history. Press **Download N** to send them to the queue.

### 4. Check the settings

Open **Settings** on the left before you start:

- **Save to** — the output folder. Defaults to `Music/Suno Downloader`.
- **Parallel downloads** — 1 to 5. Each thread runs its own hidden browser window, so memory grows with the number. 1–2 is plenty on most machines.
- **Format** and **Bitrate** — see the table below. Bitrate is greyed out for formats that don't have one.
- **Save cover art next to the audio** — writes `Artist — Title.jpg` beside the audio file.

### 5. Start downloading

Nothing downloads until you press **Start**. While it runs you get **Pause** (stop pulling new songs, finish what's running) and **Stop** (cancel everything). Each row shows a progress bar, percentage, size and length; **Clear finished** tidies up completed rows.

![Queue](docs/screenshots/03-queue.png)

When a song is done, the folder icon opens it in Finder / Explorer.

### 6. Private songs need cookies

Your own unlisted songs need your Suno session. Open **Suno cookies**, paste, and press **Import pasted**. Any of these work:

- `cookies.txt` in Netscape format (browser extension export)
- JSON from a Cookie-Editor style extension
- A raw header string: `__session=abc; other=1`

The row underneath shows the domain, how many cookies were stored, and a green **signed in** tag when a real session cookie is present. No session cookie means private songs will fail.

### 7. Proxy (optional)

Open **Proxy**, paste one proxy per line, and press **Add N proxies**. Formats accepted:

```
203.0.113.24:8080
user:pass@198.51.100.7:3128
socks5://user:pass@192.0.2.55:1080
```

Flip the switch on to use them — downloads rotate through the saved list, a different proxy per song. **Re-check** tests all of them against `suno.com` (or your own test URL) and marks the dead ones so you can remove them in one click.

### 8. History

**History** in the top right lists everything you've downloaded — cover, artist, title, size, date — with a search box. This is also what the *Downloaded* tag reads from, so scanning the same playlist twice won't waste your time. **Clear history** empties the list; your files are untouched.

## Formats

| Choice | File | Re-encoded? | Bitrate |
|---|---|---|---|
| **Original** | `.mp4` | no — exactly what Suno sent | — |
| Opus | `.opus` | no — container swap only | — |
| **MP3** *(default)* | `.mp3` | yes | 320 / 256 / 192 / 128 |
| AAC | `.m4a` | yes | 256 / 192 / 128 |
| FLAC | `.flac` | yes (lossless container, lossy source) | — |
| WAV | `.wav` | yes (uncompressed) | — |

Suno delivers Opus audio inside an MP4 container. **Original** keeps those bytes untouched; everything else is a conversion — more compatible, but never higher quality than the original.

## Where things live

| What | macOS | Windows |
|---|---|---|
| Downloads | `~/Music/Suno Downloader` | `%USERPROFILE%\Music\Suno Downloader` |
| Settings, history, cookies | `~/Library/Application Support/Suno Downloader` | `%APPDATA%\Suno Downloader` |

Everything you set — folder, threads, format, bitrate, cover art, language, proxy list — is saved and restored the next time you open the app.

## Troubleshooting

**"Only got 40% of the song — download it again."**
The connection dropped mid-download. The file is rejected on purpose rather than saved half-finished. Press **Retry** on the row.

**A song fails with "no audio data"**
It's private and the app has no session — add your cookies (step 6).

**Scan finds nothing**
Check that the link is a `suno.com` address and that the page really shows songs when you open it in a browser.

**Everything is locked and the buy screen keeps opening**
Your Suno plan expired, or the account was signed in on another machine. Check the date badge in the title bar.

**macOS says the app is damaged / can't be opened**
It isn't signed by Apple. Right-click → **Open** the first time, or run
`xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"`.
