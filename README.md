<p align="center">
  <img src="icon128.png" alt="AI Chat Navigator Pro" width="80"/>
</p>

<h1 align="center">AI Chat Navigator Pro</h1>

<p align="center">
  <strong>Highlight, tag, organize & export text from AI chat platforms.</strong><br/>
  Smart Collections auto-categorize your highlights across ChatGPT, Claude, Gemini & 6 more.
</p>

<p align="center">
  <img src="https://img.shields.io/badge/version-2.3.0-4f46e5?style=flat-square" alt="Version"/>
  <img src="https://img.shields.io/badge/manifest-v3-10b981?style=flat-square" alt="Manifest V3"/>
  <img src="https://img.shields.io/badge/platforms-9-f59e0b?style=flat-square" alt="9 Platforms"/>
  <img src="https://img.shields.io/badge/privacy-100%25%20local-22c55e?style=flat-square" alt="Privacy"/>
  <img src="https://img.shields.io/badge/license-proprietary-6b7280?style=flat-square" alt="License"/>
</p>

---

## ✨ Smart Collections — Headline Feature

Your highlights, **automatically organized** with AI-powered categorization:

| Feature | Description |
|---------|-------------|
| **🌐 Cross-Platform View** | Toggle to see highlights from ALL your AI chats — ChatGPT, Claude, Gemini, and more — in one unified view |
| **🤖 Auto-Categorization** | Every highlight is instantly classified: 💻 Code Snippets · ✅ Action Items · 💡 Key Insights · 🐛 Bug Fixes · 📝 Prompts · 📖 Explanations · 🔗 Resources |
| **📋 Session Summary** | One-click condensed summary of all highlights. Long text is intelligently compressed into key bullet points |
| **📊 Free Analytics** | Total highlights, most-used tags, platform breakdown, date ranges — all at a glance |

---

## 🗺️ Live Minimap Navigation

<table>
<tr>
<td width="60%">

- Real-time DOM clone — exact visual replica of your chat, scaled down
- Click or drag to jump to any position instantly
- Highlights glow on the minimap
- Auto-detects streaming — refreshes faster when AI is typing
- Toggle with **Alt+M**

</td>
<td width="40%">

> The minimap sits on the right side of the chat page, giving you a bird's-eye view of the entire conversation. Highlighted messages are visually marked so you can spot saved text at a glance.

</td>
</tr>
</table>

---

## 🎯 Highlight & Tag System

- **Select text** on any AI chat page → click a color-coded tag to save
- **Unlimited custom tags** with full color wheel + 8 preset colors
- **Persistent storage** — highlights survive page refreshes and browser restarts
- **Click to scroll** — jump directly to highlighted text in the chat
- **Cross-chat navigation** — "Different chat" indicator with auto-navigate & scroll
- **Bulk operations** — select multiple, delete with undo (5-second window)
- **Copy to clipboard** — one click on any highlight

---

## 📦 7-Format Export

Export highlights in any format:

| Format | Use Case |
|--------|----------|
| **TXT** | Plain text with tags and dates |
| **JSON** | Structured data for programmatic use |
| **HTML** | Styled document with colors |
| **PDF** | Print-friendly (via browser print) |
| **XML** | Markup format |
| **JS** | JavaScript module with export statement |
| **CSS** | CSS custom properties |

---

## 🌐 Supported Platforms

| Platform | Domains |
|----------|---------|
| **ChatGPT** | chatgpt.com, chat.openai.com |
| **Claude** | claude.ai |
| **Gemini** | gemini.google.com |
| **Grok** | grok.com, x.ai, grok.x.com |
| **Meta AI** | meta.ai |
| **Mistral** | mistral.ai, mistral.chat, chat.mistral.ai |
| **Qwen** | qwen.ai, chat.qwen.ai, tongyi.aliyun.com |
| **DeepSeek** | deepseek.com, chat.deepseek.com |
| **Perplexity** | perplexity.ai |

Auto-detects the AI model in use (GPT-4o, Claude Sonnet, Gemini Pro, etc.)

---

## 🏗️ Architecture

```
├── manifest.json              # Chrome MV3 manifest
├── background.js              # Service worker (tab mgmt, message relay)
├── platforms.json             # Platform detection config
├── privacy-policy.html        # Privacy policy page
├── sidepanel.html/css         # Side panel UI
├── content/
│   ├── config.js              # Shared state variables
│   ├── model-detect.js        # AI model detection
│   ├── message-detect.js      # Message scanning
│   ├── scroll.js              # Scroll container detection
│   ├── gemini.js              # Gemini shadow DOM handling
│   ├── minimap.js             # Live DOM-clone minimap
│   ├── highlights.js          # Highlight persistence & navigation
│   └── main.js                # Bootstrap & message handlers
├── panel/
│   ├── smart-collections.js   # Auto-categorization engine
│   ├── tags.js                # Tag CRUD operations
│   ├── highlights.js          # Highlights display & filtering
│   ├── export.js              # 7-format export engine
│   ├── ui.js                  # UI updates & interactions
│   ├── state.js               # State persistence
│   ├── theme.js               # Dark/light theme
│   ├── config.js              # Panel configuration
│   ├── helpers.js             # Utility functions
│   └── main.js                # Panel entry point
└── icons/                     # Extension icons
```

**Message flow:**
```
Content Script ──→ Background (Service Worker) ──→ Side Panel
     ↑                                                  │
     └──────────────────────────────────────────────────┘
```

---

## 🔒 Privacy

- **100% local** — all data stored in `chrome.storage.local`, per-hostname isolation
- **Zero external connections** — no analytics, no tracking, no telemetry, no API calls
- **No account required** — works immediately after install
- **Full user control** — delete all data anytime via "Clear Data" button
- **Transparent permissions** — every permission justified and minimal

[Read the full Privacy Policy →](privacy-policy.html)

---

## ♿ Accessibility

- Keyboard shortcuts: **Alt+M** (minimap), **Ctrl+E** (export), **Ctrl+F** (search)
- 8 color preset buttons (keyboard alternative to canvas color wheel)
- Focus trapping in all modals
- ARIA labels, `role="alert"` on toasts, screen reader announcements
- Dark & light theme support

---

## 📋 Changelog

### v2.3.0

**✨ New: Smart Collections**
- AI-powered auto-categorization into 7 categories
- Cross-platform view — aggregates highlights from all AI chats
- One-click session summary with intelligent text compression
- Analytics dashboard

**⚡ Performance**
- Minimap clone optimization (incremental updates, no full DOM reclone)
- Message broadcast debouncing (90% less IPC during streaming)
- Selector caching, image placeholder in minimap, memory leak fixes

**🛡️ Compliance**
- Privacy policy, onboarding modal, "Clear All Data" button

**🎨 UX**
- Confirmation dialogs on delete, model detection timeout fallback
- Search result count ("X of Y"), toast screen reader announcements

**♿ Accessibility**
- Color presets, focus trapping, minimap ARIA labels

**🐛 Fixes**
- Chat overview duplicates, scroll-to-highlight on long chats
- Storage migration preserves highlights across version updates
- Cross-chat scroll retry with SPA-aware timing

---

**Minimum Chrome version:** 114 (required for Side Panel API)

---

<p align="center">
  <strong>Powered by SOLVENEERS CORP</strong><br/>
  <sub>Built with care for the AI community</sub>
</p>
