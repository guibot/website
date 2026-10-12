+++
title = "GWiki"
date = 2026-10-12
lastUpdate = 0
status = "ongoing"
tags = ["wiki", "webapp", "vibecode"]
featured = true
cover = "gwiki.jpg"
showCover = false
+++

## minimalistic, self-hosted wiki

A lightweight wiki that runs from a single Python file and a single HTML file. 
No install, no build step, no dependencies. 
Notes live as plain Markdown or HTML files on disk, so they stay readable and easy to back up.

[Source on GitHub](https://github.com/guibot/gwiki)

![](gwiki.jpg)

### What it does

- Single-file frontend (`index.html`, CSS and JS inline) and a Python stdlib server (`server_wiki.py`).
- Custom regex Markdown parser, no external library.
- Topics are grouped in categories; names come from folder and file slugs.
- Inline editor: split-pane Markdown with live preview, or a WYSIWYG editor for HTML topics with image upload, paste and resize.
- Drag-and-drop ordering of categories and topics.
- Deep links through the URL hash, so any page can be bookmarked or shared.
- Category labels with custom name and color, plus a generated QR code exported as JPEG or PDF.

### Modes

The server detects the mode on startup:

- **Standalone**: a single `topics/` folder at the root goes straight to the wiki.
- **Hub**: several sub-wiki folders at the root show a card grid, each with its own cover, name and tagline.

The hub has an animated subtitle that cycles through a custom word list with text effects (scramble, glitch, wave, rainbow), and a settings panel for title, colors and logo.

### Admin

Append `?admin` to the URL. The first visit sets a password, stored as a salted SHA-256 hash. Every write endpoint (create, edit, rename, delete) needs the session token.

### Running

```bash
python3 server_wiki.py
# open http://localhost:8080
```

<br>

Install and API details are in the [repo](https://github.com/guibot/gwiki). Orchestrated by me, built with Claude Code.
