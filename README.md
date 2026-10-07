<h1 align="center">Suno Downloader</h1>

<p align="center"><b>A desktop app that downloads music from suno.com at original quality - one song, a whole playlist, a profile or the Explore page, with cover art, and every file verified before it is marked done.</b></p>

<p align="center">
  <b>English</b> ·
  <a href="README.vi.md">Tiếng Việt</a>
</p>

<p align="center">
  <a href="https://github.com/duckmartians/Suno-Downloader/releases/latest"><img alt="Download for Windows" src="https://img.shields.io/badge/Download-Windows-0078D6?style=for-the-badge&logo=windows&logoColor=white"></a>&nbsp;
  <a href="https://github.com/duckmartians/Suno-Downloader/releases/latest"><img alt="Download for macOS (Apple Silicon)" src="https://img.shields.io/badge/Download-macOS%20Apple%20Silicon-000000?style=for-the-badge&logo=apple&logoColor=white"></a>&nbsp;
  <a href="https://github.com/duckmartians/Suno-Downloader/releases/latest"><img alt="Download for macOS (Intel)" src="https://img.shields.io/badge/Download-macOS%20Intel-555555?style=for-the-badge&logo=apple&logoColor=white"></a>
</p>

---

## Install

### Step 1 - Pick the right build for your machine

Open the latest release on **[Releases](https://github.com/duckmartians/Suno-Downloader/releases/latest)** and download the file that matches your machine (`<version>` is the release number, e.g. `1.0.1`):

| Your machine | Download | Notes |
|---|---|---|
| 🪟 **Windows (64-bit)** | [`SunoDownloader-<version>-win-x64.exe`](https://github.com/duckmartians/Suno-Downloader/releases/latest) | Installer |
| 🍎 **Mac with Apple chip (M1/M2/M3/M4)** | [`SunoDownloader-<version>-mac-arm64.dmg`](https://github.com/duckmartians/Suno-Downloader/releases/latest) | Macs from ~late 2020 onward |
| 🍎 **Mac with Intel chip** | [`SunoDownloader-<version>-mac-intel.dmg`](https://github.com/duckmartians/Suno-Downloader/releases/latest) | Older Macs (before 2020) |

**Not sure which chip your Mac has?** Click the  menu (top-left) → **About This Mac**:
- A **Chip** line reading "Apple M1 / M2 / M3…" → download the **arm64** build.
- A **Processor** line reading "Intel…" → download the **intel** build.

> The **Intel** build still runs on an Apple-chip Mac (just slower), but the **arm64** build will **not open** on an Intel Mac - so pick the right one.

Nothing else to install: FFmpeg and the background browser ship inside the app - you don't need Chrome.

### Step 2 - Install

<details open>
<summary><b>🪟 On Windows</b></summary>

1. Open the downloaded **`SunoDownloader-<version>-win-x64.exe`**.
2. If **"Windows protected your PC"** (SmartScreen) appears: click **More info** → **Run anyway**. *(The app isn't code-signed with a Microsoft certificate, so it's flagged - it isn't a virus.)*
3. Let the installer finish, then launch **Suno Downloader** from the **Start Menu**.

</details>

<details open>
<summary><b>🍎 On macOS</b></summary>

1. Open the downloaded **`.dmg`**, then **drag Suno Downloader into the Applications folder**.
2. Go to **Applications**, **right-click** (or Control-click) **Suno Downloader** → **Open** → click **Open** again in the dialog. *(The app is only ad-hoc signed, not signed with an Apple Developer ID, so you must open it this way the **first time**; afterwards it opens normally.)*
3. If macOS says the app is **"damaged / can't be opened"**, or there's no Open button, open **Terminal** and paste:
   ```bash
   xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"
   ```
   Then open the app again.

</details>

### Step 3 - Sign in &amp; buy the Suno plan

**You need an account with an active Suno plan - there is no free tier.** Open the app and sign in with Google; without an active plan the app opens the purchase screen. The Suno plan is its own plan, separate from G-Labs Studio's plans, time-based and with no auto-renewal:

| Duration | Bank QR (VietQR) | PayPal / USDT |
|---|---|---|
| 1 month | 50,000₫ | $3 |
| 6 months | 250,000₫ | $15 |
| 1 year | 500,000₫ | $30 |

Every plan unlocks all features. Pay from inside the app by **bank QR (VietQR)**, **PayPal** or **USDT** (USDT is activated manually - message the developer after paying, as the purchase screen explains). One account runs on **one machine at a time** - signing in elsewhere signs the previous machine out. The badge in the title bar shows your plan's end date; click it to check or renew.

The app **updates itself**: the version badge in the title bar checks GitHub Releases. On Windows it downloads the new installer and runs it; on macOS it downloads and opens the new `.dmg` so you can drag the app into Applications again.

---

## First run

1. **Open the app and sign in with Google.** The date badge in the title bar confirms your Suno plan.
2. **Paste a Suno link** into the box at the top left - a song, playlist, profile or the Explore page - and press **Scan**. Large pages take around 30 seconds while the app scrolls them to load every song.
3. **Pick songs** in the list that opens (everything is ticked) and press **Download N** to put them in the queue.
4. **Check Settings** on the left: output folder, parallel downloads, format and bitrate, cover art.
5. **Press Start.** Nothing downloads until you do. When a song is done, its folder icon opens it in Finder / Explorer.

Private (unlisted) songs of your own also need your Suno session - add it under **Suno cookies** first.

---

## Features

![Suno Downloader](docs/screenshots/01-main.png)

- **One link, the whole batch** - song · playlist · profile · Explore page; the app scans the page and shows you the list to pick from.
- **Pick exactly what you want** - search the scanned list, select all / deselect, and songs you already have are tagged **Downloaded** so you don't grab them twice.
- **Add first, download when ready** - links land in the queue; **Start / Pause / Stop** are separate buttons.
- **Formats &amp; bitrate** - **Original** MP4 byte-for-byte untouched, Opus (container swap, no re-encode), MP3, AAC, FLAC, WAV - see [Formats](#formats).
- **Parallel queue** - 1-5 songs at a time, each row showing cover art, percentage, size and length.
- **Every file verified** - the app re-reads the MP4 structure (exactly one init segment, no gaps between fragments, total length matching the metadata). Short or corrupt means **failed**, never a silent half-song.
- **Survives a crash** - if the background browser dies mid-download, the song is retried automatically (up to 3 attempts).
- **Cover art** saved next to the audio, same file name.
- **Cookies for private songs** - paste Netscape `cookies.txt`, browser-extension JSON or a raw `a=1; b=2` header; the panel tells you whether they are actually **signed in**. The app never reads your browser's cookie store on its own.
- **Proxy pool** - paste proxies in any shape, downloads rotate through the list, re-check marks the dead ones.
- **History** - everything you've downloaded, searchable; it powers the *Downloaded* tag.
- **6 languages** - English · Tiếng Việt · 简体中文 · Español · Русский · العربية (right-to-left).

---

## Pages

### 🔗 Link &amp; scan

![Main window](docs/screenshots/01-main.png)

Paste any of these into the box at the top left, then press **Scan** (**Cancel scan** stops it):

| Link | What you get |
|---|---|
| `https://suno.com/song/<id>` | that one song |
| `https://suno.com/playlist/<id>` | every song in the playlist |
| `https://suno.com/@<user>` | that profile's songs |
| `https://suno.com/explore` | what's on the Explore page |

### ✅ Select songs

![Select songs](docs/screenshots/02-scan.png)

The list opens with everything ticked. Type in the search box to narrow it, use **Select all / Deselect**, and note the green **Downloaded** tag - those songs are already in your history. **Download N** sends the selection to the queue.

### ⬇️ Download queue

![Queue](docs/screenshots/03-queue.png)

**Start** begins downloading; **Pause** stops pulling new songs but finishes the running ones; **Stop** cancels everything. Each row shows a progress bar, percentage, size and length, and lets you **Preview** the song, **Show in folder**, or **Retry** a failed row (**Retry failed** does them all). **Clear finished** tidies up completed rows.

### ⚙️ Settings

On the left, before you start:

- **Save to** - the output folder. Defaults to `Music/Suno Downloader`.
- **Parallel downloads** - 1 to 5. Each thread runs its own hidden browser window, so memory grows with the number; 1-2 is plenty on most machines.
- **Format** and **Bitrate** - see [Formats](#formats). Bitrate is greyed out for formats that don't have one.
- **Save cover art next to the audio** - writes `Artist - Title.jpg` beside the audio file.

### 🍪 Suno cookies

![Cookies](docs/screenshots/04-cookies.png)

Your own unlisted songs need your Suno session. Open **Suno cookies**, paste, and press **Import pasted**. Accepted: Netscape `cookies.txt` (browser-extension export), JSON from a Cookie-Editor style extension, or a raw header string such as `__session=abc; other=1`. The row underneath shows the domain, how many cookies were stored, and a green **signed in** tag when a real session cookie is present - without one, private songs will fail.

### 🌐 Proxy

![Proxy](docs/screenshots/05-proxy.png)

Optional. Paste one proxy per line and press **Add N proxies**:

```
203.0.113.24:8080
user:pass@198.51.100.7:3128
socks5://user:pass@192.0.2.55:1080
```

Flip the switch on and downloads rotate through the saved list, a different proxy per song. **Re-check** tests every proxy against `suno.com` (or your own test URL) and marks the dead ones so you can remove them in one click.

### 🕘 History

![History](docs/screenshots/06-history.png)

**History** (top right) lists everything you've downloaded - cover, artist, title, size, date - with a search box. It is also what the *Downloaded* tag reads from, so scanning the same playlist twice won't waste your time. **Clear history** empties the list; your music files are untouched.

### 🌍 Languages

![Right-to-left (العربية)](docs/screenshots/07-rtl-arabic.png)

The interface comes in English, Tiếng Việt, 简体中文, Español, Русский and العربية; Arabic switches the whole layout to right-to-left.

---

## Formats

| Choice | File | Re-encoded? | Bitrate |
|---|---|---|---|
| **Original** | `.mp4` | no - exactly what Suno sent | - |
| Opus | `.opus` | no - container swap only | - |
| **MP3** *(default)* | `.mp3` | yes | 320 / 256 / 192 / 128 |
| AAC | `.m4a` | yes | 256 / 192 / 128 |
| FLAC | `.flac` | yes (lossless container, lossy source) | - |
| WAV | `.wav` | yes (uncompressed) | - |

Suno delivers Opus audio inside an MP4 container. **Original** keeps those bytes untouched; everything else is a conversion - more compatible, but never higher quality than the original.

---

## Where your data lives

| What | macOS | Windows |
|---|---|---|
| Downloads (changeable in Settings) | `~/Music/Suno Downloader` | `%USERPROFILE%\Music\Suno Downloader` |
| Settings, history, cookies, proxy list | `~/Library/Application Support/Suno Downloader` | `%APPDATA%\Suno Downloader` |

Everything you set - folder, threads, format, bitrate, cover art, language, proxy list - is saved and restored the next time you open the app.

---

## Troubleshooting

**"Only got 40% of the song - download it again."** - the connection dropped mid-download. The file is rejected on purpose rather than saved half-finished. Press **Retry** on the row.

**A song fails with "no audio data"** - it's private and the app has no session. Add your cookies under **Suno cookies**.

**Scan finds nothing** - check that the link is a `suno.com` address and that the page really shows songs when you open it in a browser.

**Everything is locked and the buy screen keeps opening** - your Suno plan expired, or the account signed in on another machine. Check the date badge in the title bar and renew.

**The app is slow or uses a lot of memory** - every parallel download is a hidden browser window. Lower **Parallel downloads** to 1-2 in Settings.

**Windows blocks it at "Windows protected your PC"** - click **More info → Run anyway**. The app isn't code-signed with a Microsoft certificate, so it's flagged - it isn't a virus.

**macOS says the app is damaged / can't be opened** - it isn't signed with an Apple Developer ID. Right-click → **Open** the first time, or run `xattr -dr com.apple.quarantine "/Applications/Suno Downloader.app"`.

**An update won't install** - download the latest build manually from [Releases](https://github.com/duckmartians/Suno-Downloader/releases/latest).

---

<sub>Suno Downloader is an independent tool, not affiliated with or endorsed by Suno, Inc. Only download content you have the right to use, and follow Suno's terms.</sub>
