# DeepChat — Mobile AI Client

DeepChat is a powerful, single-file HTML AI client designed specifically for Android and mobile browsers. It runs entirely in your browser, connects directly to top AI providers (DeepSeek, Claude, Gemini, OpenAI, Qwen), and keeps your data local and secure.

No backend, no servers, no tracking. Just one `index.html` file.

## ✨ Features

- **Local Semantic Search (NEW):** Runs `all-MiniLM-L6-v2` locally on your phone using Transformers.js. It calculates vector embeddings to retrieve relevant memories based on *meaning*, not just keywords.
- **Context Warning (NEW):** Automatically tracks token usage and warns you when a chat is getting too long (nearing the 1-million token limit).
- **Multi-Provider Support:** Switch between DeepSeek, Claude, Gemini, ChatGPT, and Qwen on the fly.
- **Memory Bank:** The AI can save facts about you and remember them in future chats. Memories can be Global or scoped to specific Projects.
- **Projects & Prompts:** Organize chats into projects with custom system prompts, and save reusable prompts with `{{variables}}`.
- **Encrypted Storage:** All chats, projects, and memories are encrypted locally using AES-256-GCM and protected by a PIN.
- **Vault:** Hide sensitive chats behind a PIN and access them via a long-press on the sidebar title.
- **Second Opinion:** Ask two different AI models the same question side-by-side and pick the best answer.
- **Web Search:** Integrates with Tavily to let the AI search the web.
- **Tools:** AI can fetch URLs and save facts to memory automatically (function calling).
- **Mobile-First Design:** Native-feeling UI with swipe gestures, auto-resizing inputs, haptic feedback, and Dark Mode.

## 🚀 Setup

Since DeepChat is a single HTML file, setup is instant.

1. **Download** the `index.html` file.
2. **Host it** anywhere (GitHub Pages, Vercel, Netlify) or just open it directly in your browser.
3. **Configure:** Tap the gear icon ⚙️ in the sidebar, select your provider, and paste your API Key. 
4. **Secure:** We highly recommend turning on **App Lock** to encrypt your chats.

*(Note: The first time you use the Memory feature, the app will download a 25MB embedding model. It caches locally, so it only happens once.)*

## 🔒 Privacy & Security

- **100% Local:** Your API keys, chat history, and memories never touch a DeepChat server (because there isn't one).
- **Encryption:** If App Lock is enabled, your chat data is stored in `localStorage` as AES-256-GCM ciphertext.
- **Local AI:** The semantic search model runs entirely inside your browser's WebAssembly. No text is sent to HuggingFace or any external server for embedding.

## 🛠️ Technical Details

- **Embedding:** `Xenova/all-MiniLM-L6-v2` via Transformers.js (384-dimensional vectors, cosine similarity).
- **Markdown:** Parsed via `marked.js`.
- **Styling:** Tailwind CSS (via CDN).
- **Icons:** FontAwesome 6.
- **Crypto:** Web Crypto API (PBKDF2 for key derivation, AES-GCM for encryption).

## 📝 Usage Tips

- **Vault:** Long-press the "DeepChat" title in the sidebar to open your Vault.
- **Branching:** Tap the branch icon on any message to fork the conversation into a new chat from that point.
- **Bookmarks:** Star important messages to easily jump back to them later.
- **Memory:** By default, unpinned memories only get injected if they are semantically relevant to your prompt. If you want a memory to *always* be sent, hit the star icon next to it to Pin it.