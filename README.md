Vibe Prompter 🎙️

The Lean, Context-Aware, Voice-Controlled Teleprompter.

Stop paying monthly subscriptions for "dumb" scrolling text. Vibe Prompter is a single-file, zero-dependency, AI-powered teleprompter built for the modern Enablement Architect and Content Creator. It listens to your voice, matches your pace, and runs entirely in your browser.

Created as part of the [Vibe Training] methodology: We build custom, lean infrastructure instead of buying closed SaaS platforms.

🚀 The Philosophy (Why build this?)

Traditional teleprompter apps either force you to guess your reading speed or rely on clunky, expensive SaaS subscriptions with poor NLP (Natural Language Processing).

As an "AI Tailor", I believe in Enablement over traditional L&D. When you're recording "Deep Content" for YouTube, Skool communities, or internal organizational training, the technology should flow with you, not dictate your pace.

Vibe Prompter is built on Lean Architecture: It's just one index.html file. No databases, no backends, absolute privacy, and 0 latency.

✨ Key Features

🧠 Context-Lock Engine (Anti-Ghost Jump): Traditional voice-prompters get confused if your text has duplicate words (e.g., saying "we build" twice in one paragraph). Vibe Prompter uses a custom "Tip of the Tongue" buffer and context-validation to ensure it never skips ahead to the wrong paragraph.

🌍 Auto-Language & Direction Detection: Paste English, it flows Left-to-Right and loads the en-US speech model. Paste Hebrew/Arabic, it flips to Right-to-Left and loads the he-IL model. Zero configuration needed.

🏃‍♂️ Pace-Forgiving (Fuzzy Match): You don't need to read like a robot. Add "uhms", skip a word, or add a prefix—the algorithm uses fuzzy matching to keep track of your actual position.

🪞 Physical Glass Ready: 1-click Horizontal and Vertical flip modes for professional glass-beam splitter setups (iPad/Monitor under the lens).

🔒 100% Client-Side Privacy: Uses the native browser Web Speech API. Your script never leaves your device.

🛠️ How to Use (The Lean Way)

You don't need npm, Node.js, or a build step.

Download or copy the index.html file.

Double-click to open it in Google Chrome, Microsoft Edge, or Safari.

Allow Microphone permissions.

Paste your script, adjust your padding/font size, and hit Play.

Want to host it? Drop the index.html file into GitHub Pages, Vercel, or Cloudflare Pages, and you have your own production-ready web app in 30 seconds.

⚙️ Tech Stack

Frontend: React 18 & Tailwind CSS (via CDN)

Compilation: Babel Standalone (In-browser JSX compilation)

AI/Logic: Native Web Speech API with custom Context-Aware array parsing.

Icons: Pure inline SVG (Zero external library dependencies).

💡 About Vibe Training

The traditional Instructional Designer role is evolving. In the age of Generative AI, we are shifting from creating static SCORM courses to building dynamic, programmatic enablement systems.

Give the Knowledge for Free. Sell the Execution.
Feel free to fork, modify, and use this tool for your own video production. If you want to learn how to build internal LMS solutions, custom AI tools, and shift your organization's L&D to a Lean, Code-based model, let's connect.

📄 License

This project is licensed under the MIT License.

In the spirit of Vibe Training: The code is completely free. Take it, learn from it, modify it, and use it in your own organizations or personal projects without restrictions.

Built with ❤️ for the Enablement & L&D Community.
