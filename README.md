# Notepad

A lightweight, Notepad++-style code and text editor that runs entirely in the browser. No install required. Works on any OS, any machine with a browser and an internet connection.

Live at: [laccces.github.io/notepad](https://laccces.github.io/notepad)

---

## Features

- Syntax highlighting for JS, TS, HTML, CSS, Python, SQL, Markdown, YAML, Shell and PHP
- Multiple tabs open simultaneously with unsaved change indicators
- Left pane file tree with folder support and right-click context menu
- Find and replace
- Drag and drop files to open them
- Dark and light mode
- GitHub Gist sync for cross-device access
- Auto-save on window blur and tab switch
- Full session persistence via IndexedDB (tabs and content restored on reload)

---

## Getting Started

Open the URL in any browser. No login, no setup. Your files are stored locally in your browser's IndexedDB and persist across sessions automatically.

---

## Working with Files

**New file** - click the + button in the tab bar or the new file icon in the file tree.

**Open a file** - drag any file from your filesystem onto the editor area. It opens as a new tab.

**Download a file** - right-click the file in the left pane and select Download, or use the download button in the toolbar.

**Rename or delete** - right-click the file or folder in the left pane.

---

## GitHub Gist Sync

Gist sync lets you save files to your GitHub account and load them on any other machine.

### Setup

1. Go to github.com, Settings, Developer settings, Personal access tokens, Tokens (classic)
2. Generate a new token with the `gist` scope only
3. In the editor, click the Settings (gear) icon and paste the token
4. The token is stored in your browser's localStorage and never sent anywhere other than the GitHub API

### Saving

Click Save to Gist. The first save creates a new private Gist in your GitHub account. Subsequent saves update the same Gist. The status bar at the bottom shows the Gist URL after saving.

### Loading on another machine

Click Load Gist and paste either the full Gist URL (e.g. `https://gist.github.com/username/abc123`) or just the ID at the end. The file opens as a new tab.

Each device needs the token added in Settings once. The same token works across all devices.

---

## Persistence

All files and open tabs are saved to your browser's IndexedDB. If you close the tab or refresh, everything is restored automatically when you reopen the editor. Each browser on each machine has its own independent storage, which is why Gist sync is the recommended approach for working across devices.

---

## Limitations

- Files live in the browser. Clearing browser site data will delete local files that have not been synced to a Gist.
- No offline support on first load (CodeMirror loads from CDN).
- Gist sync is one file per Gist. It is not a full filesystem sync.
- No mobile keyboard support tested.

---

## Stack

- CodeMirror 5 (editor engine)
- IndexedDB (local persistence)
- GitHub Gist API (cloud sync)
- Vanilla JS, single HTML file, no build step
- Hosted on GitHub Pages
