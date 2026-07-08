# Contact Sheet

**Turn real experiences into polished social posts.** Contact Sheet takes rough notes about an externship, internship, conference, or workshop and drafts a platform-tailored post for LinkedIn, Instagram, X, or Facebook — with an optional AI polish pass that fixes spelling, rewrites awkward phrasing, and matches a writing style you like.

> A single self-contained HTML file. No build step, no backend. Open it and go.

---

## Features

- **Platform targeting** — LinkedIn, Instagram, X, and Facebook, each with its own character limit, voice, and live preview mockup.
- **Live drafting** — every field, tone, and style change re-generates the draft instantly.
- **Tone & length control** — Professional, Warm, Excited, Reflective, Humble, Confident, Casual, Story-driven, plus Shorter / More polished / More personal / More professional variants.
- **Writing styles** — pick a common LinkedIn style (Hook + short lines, Reflection, Listicle, Gratitude, Contrarian, Data-first) **or paste a post you admire** and the generator mirrors its structure and rhythm. Style is applied *on top of* a coherent base so the result always reads well.
- **AI polish (optional)** — route the draft through a real LLM to fix misspellings, interpret intent (e.g. "I met Dhruv" → thanks *Dhruv*, not "thank you to I met Dhruv"), and rewrite naturally without inventing facts. Bring your own model:
  - **Llama** locally via [Ollama](https://ollama.com) — free, private, no key
  - **Claude** (Anthropic), **OpenAI GPT**, **DeepSeek**, or **Groq** — bring an API key
- **Photo "film strip"** — drag in photos, mark a hero frame, reorder, and caption them; they render in the platform preview.
- **Drafts** — save, restore, duplicate, and delete drafts (stored in your browser).
- **Export** — copy the post, download as `.txt`, or export a JSON package (post + hashtags + details + photo metadata).

---

## Live demo

Enable **GitHub Pages** (Settings → Pages → Deploy from branch → `main` / root) and the site goes live at:

**https://dereklu-collab.github.io/Linkedin-editor/**

`index.html` is at the repository root, so no configuration is needed.

---

## Running locally

It's a static file — any of these work:

```bash
# Option 1: just open it
open index.html

# Option 2: serve it (recommended, so browser APIs behave)
python3 -m http.server 3001
# then visit http://localhost:3001
```

---

## AI polish setup

AI polish is **off by default** — the template generator always runs first, so the app works with zero setup. To enable it, open the **AI polish** panel in the left sidebar, toggle it on, and pick a provider from **Select AI model**.

### Llama (local, free)

```bash
# 1. Install Ollama → https://ollama.com
# 2. Pull a model
ollama pull llama3.2
# 3. Start it with browser access enabled
OLLAMA_ORIGINS=* ollama serve
```

Then in the app choose **Llama (local via Ollama)** and click **Test connection**.

### Cloud providers (Claude / OpenAI / DeepSeek / Groq)

Pick the provider, paste an API key (get one from the link shown in the panel), and test. Groq has a generous free tier and is very fast.

> **⚠️ About API keys:** keys are stored **only in your browser's localStorage** and sent directly to the provider from your browser. This is fine for personal/local use, but:
> - **Do not commit API keys to the repo.** They live in the browser, not in the code — nothing key-related is ever written to `index.html`.
> - **Do not use production keys.** Treat these as personal development credentials. On a public site, prefer a local Llama model or a restricted/free-tier key.
> - Keys are never included in saved drafts or exported packages.

---

## Tech stack

- **React 18** + **Babel Standalone** (in-browser JSX, no build)
- **Tailwind CSS** (CDN)
- Fonts: Fraunces, Inter, IBM Plex Mono

Everything loads from CDNs, so the app is a single HTML file with no dependencies to install.

---

## Project structure

```
.
├── index.html      # the entire application
├── README.md       # this file
├── LICENSE         # MIT
└── .gitignore
```

---

## License

[MIT](LICENSE) © Derek Lu
