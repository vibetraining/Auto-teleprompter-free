# Vibe Prompter 🎙️

**The Lean, Context-Aware, Voice-Controlled Teleprompter.**

Stop paying monthly subscriptions for "dumb" scrolling text. Vibe Prompter is a free, single-file teleprompter built for the modern Enablement Architect and Content Creator. It listens to your voice, matches your pace, and runs entirely in your browser.

Created as part of the **[Vibe Training]** methodology: We build custom, lean infrastructure instead of buying closed SaaS platforms.

## 🚀 The Philosophy (Why build this?)

Traditional teleprompter apps either force you to guess your reading speed or rely on clunky, expensive SaaS subscriptions with poor NLP (Natural Language Processing).

As an "AI Tailor", I believe in **Enablement over traditional L&D**. When you're recording "Deep Content" for YouTube, Skool communities, or internal organizational training, the technology should flow with you, not dictate your pace.

Vibe Prompter is built on **Lean Architecture**: it's one `index.html` file with **zero dependencies**. No frameworks, no CDNs, no databases, no backend. It loads instantly and works offline.

## ✨ Key Features

- 🧠 **Context-Lock Engine (Anti-Ghost Jump):** Traditional voice prompters get confused when your script repeats words (e.g. saying "we build" twice in one paragraph). Vibe Prompter only accepts a far jump when the surrounding words match too, so it never skips ahead to the wrong sentence.

- 🚗 **Cruise Control:** If the recognizer misses a word, the prompter keeps rolling at your measured pace. It waits when you stop talking, and never runs more than a few words ahead of what it actually heard.

- 🏃‍♂️ **Pace-Forgiving (Fuzzy Match):** You don't need to read like a robot. Say "uhm", skip a word, add a prefix, or let the recognizer make a small typo. Fuzzy matching keeps track of where you really are.

- 🌍 **Auto Language & Direction Detection:** Paste English and it flows left-to-right with an English speech model. Paste Hebrew or Arabic and it flips to right-to-left. It also detects Spanish, French, German, Italian, Portuguese, Dutch, Russian, Ukrainian, Greek, Hindi, Japanese, Korean and Chinese. You can override the speech language manually.

- ⏩ **Auto-Scroll Mode:** No microphone, or a browser without speech recognition (e.g. Firefox)? Switch to constant-speed scrolling and set the words-per-minute.

- 🪞 **Physical Glass Ready:** 1-click horizontal and vertical flip modes for beam-splitter glass setups (iPad/monitor under the lens). Flips apply only while reading, so the editor stays readable.

- 🎮 **Remote, Clicker & Keyboard Control:** Works with presentation clickers, Bluetooth joysticks and keyboards (see the shortcuts below). Click any word to jump there.

- 🎯 **Smooth, Adjustable Eye-Line:** The text glides continuously to an eye-line you choose, so your gaze stays near the camera lens.

- 💡 **Studio Comforts:** Full-screen mode, keeps the screen awake while reading, progress bar, elapsed/remaining time, a HUD that hides itself, and every setting remembered between sessions.

- 🌐 **Multilingual UI:** English, Hebrew, Spanish and French.

- 🔒 **100% Client-Side:** Your script and settings are stored only in your browser's local storage.

## 🛠️ How to Use (The Lean Way)

You don't need `npm`, Node.js, or a build step.

1. Download or copy the `index.html` file.
2. Double-click to open it in Google Chrome, Microsoft Edge, or Safari.
3. Paste your script, adjust the font size, margins and eye-line, and hit **Start reading**.
4. Allow microphone access when asked (Voice follow mode only).

_Want to host it?_ Drop `index.html` into GitHub Pages, Vercel, or Cloudflare Pages, and you have your own production-ready web app in 30 seconds. Hosting over HTTPS also means the browser remembers your microphone permission.

### ⌨️ Shortcuts (while reading)

| Key | Action |
| --- | --- |
| `Space` | Pause / resume |
| `Esc` | Stop and return to the editor |
| `↑` `←` / `↓` `→` | One word back / forward (hold to keep moving) |
| `PgUp` / `PgDn` | Jump 10 words |
| `Home` | Back to the start |
| `-` / `+` | Slower / faster |
| `F` | Full screen |
| Mouse wheel | Move line by line |
| Click a word | Jump to it (while editing, it sets the start point) |

### 🌐 Browser Support

| Browser | Voice follow | Auto-scroll |
| --- | --- | --- |
| Chrome / Edge (desktop & Android) | ✅ | ✅ |
| Safari (macOS & iOS) | ✅ | ✅ |
| Firefox | ❌ (no Web Speech API) | ✅ |

## 🔐 Privacy Note

The app itself never uploads anything: no analytics and no servers. Voice follow uses your browser's built-in Web Speech API. Depending on the browser, that API may send microphone audio to the vendor's speech service to transcribe it. **Chrome uses Google's servers, for example.** Your script text never leaves your device. If you need fully offline operation, use Auto-scroll mode.

## ⚙️ Tech Stack

- **Frontend:** Plain HTML, CSS and JavaScript. No framework, no build step, no external requests.
- **Speech:** Native Web Speech API with a custom context-aware matching engine (fuzzy matching, context lock, cruise control and adaptive pace).
- **Icons:** Inline SVG.

## 💡 About Vibe Training

The traditional Instructional Designer role is evolving. In the age of Generative AI, we are shifting from creating static SCORM courses to building dynamic, programmatic enablement systems.

**Give the Knowledge for Free. Sell the Execution.** Feel free to fork, modify, and use this tool for your own video production. If you want to learn how to build internal LMS solutions, custom AI tools, and shift your organization's L&D to a Lean, Code-based model, let's connect.

## 📄 License

This project is licensed under the **MIT License**.

In the spirit of _Vibe Training_: The code is completely free. Take it, learn from it, modify it, and use it in your own organizations or personal projects without restrictions.
