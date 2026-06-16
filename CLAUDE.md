# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Vibe Prompter** is a single-file, zero-dependency, voice-controlled teleprompter. The entire application lives in `index.html` (~524 lines of JSX). There is no build step, no package.json, no node_modules, and no backend.

## Running the App

Open `index.html` directly in a Chromium-based browser (Chrome, Edge) or Safari. Firefox has limited Web Speech API support. No server or install step is needed.

For a local dev server (optional, for testing HTTPS-gated APIs):
```bash
python3 -m http.server 8080
# then open http://localhost:8080
```

There are no tests, no linter, and no build commands.

## Architecture

The app is a single React 18 component (`App`) written in JSX, compiled in-browser by Babel Standalone. Dependencies are loaded via CDN:
- React 18 + ReactDOM
- Babel Standalone (in-browser JSX transpilation)
- Tailwind CSS (utility styling)

All application logic is inside the `<script type="text/babel">` block in `index.html`.

### Key Subsystems

**Speech Recognition Engine**
Uses the native `window.SpeechRecognition` / `webkitSpeechRecognition` API with `continuous: true` and `interimResults: true`. The recognition language is auto-detected from script content (Hebrew characters → `he-IL`, otherwise `en-US`). The recognizer auto-restarts on `onend` while playback is active.

**Context-Lock (Anti-Ghost Jump) Algorithm**
The core innovation. When a spoken word is matched, the engine:
1. Searches only 12 words ahead of the current position (not the full script)
2. Only considers the last 4 spoken words for matching
3. On large jumps (>2 words), validates that the preceding word also matches before committing
This prevents "ghost jumps" to distant duplicate words or similar phrases.

**Fuzzy Matching**
`fuzzyMatch(spoken, target)` — matches on exact, case-insensitive, or substring (3+ char words). Strips punctuation from both sides before comparing.

**Cruise Control (Auto-Scroll)**
A `setInterval` loop running at 100ms advances `currentWordIndex` by fractional amounts based on learned WPS (words-per-second). WPS starts at 2.5, is clamped to 1.0–5.0, and is updated dynamically after 2+ seconds and 2+ matched words. If speech stops for 2+ seconds, the cruise control continues advancing automatically.

**Keyboard/Joystick Scrolling**
Arrow keys and Page Up/Down move the position manually. A 90ms repeat interval handles held keys. Manual navigation resets the WPS learning state and sync flags.

**Internationalization**
Supports UI in English, Hebrew, Spanish, French (`uiLang` state). Script direction (RTL/LTR) is auto-detected from content. The translations dictionary is at the top of the script block.

### State and Refs Pattern

React state (`useState`) drives rendering: word index, play state, settings. High-frequency values (cruise control tick, speech timing, WPS accumulator) live in `useRef` to avoid re-renders. `localStorage` persists the script text and display settings across sessions.

### Rendering

Words are split on whitespace; newlines are preserved as special tokens that render as `<br/>`. Each word gets a DOM id (`word-${index}`) for scroll-to-center. Past words turn green while playing; the current word gets a blue underline.

## Key Conventions

- **No files should be added.** All code stays in `index.html`. Do not create a `src/` directory, `package.json`, or build pipeline unless explicitly asked.
- The CDN script tags load order matters: React → ReactDOM → Babel → Tailwind, then the `text/babel` script block.
- Inline styles (via Tailwind classes and occasional `style={{}}` props) are the norm; do not introduce CSS files.
- Mirror mode (`mirrorMode`, `flipVertical`) applies CSS `transform: scaleX(-1)` or `scaleY(-1)` to the entire prompter container — keep transforms on that wrapper element.
- RTL support: `direction` is set on the script container; sidebar positioning uses conditional `right`/`left` classes based on the detected language direction.
