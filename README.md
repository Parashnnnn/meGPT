# meGPT

### Your AI. Your machine.

**meGPT** is a private, local AI chat application powered by **Ollama + Qwen3 8B**.

Instead of sending your conversations to a cloud AI provider, meGPT connects to an AI model running directly on your own computer.

> **Your AI. Your machine.**

## 🌐 Live Demo

**Website / UI Preview:**
https://megpt-coral.vercel.app/

> The Vercel deployment is mainly a web preview of meGPT. The AI itself runs locally through Ollama on your computer, so the chat functionality requires the local setup below.

---

## ✨ Features

* 🤖 Qwen3 8B local AI
* 🔒 Private local AI processing
* 💬 Streaming AI responses
* 🧠 Custom system prompt
* 🌡️ Adjustable temperature
* 🗂️ Multiple conversations
* 🔎 Search conversations
* ✏️ Rename conversations
* 🗑️ Delete conversations
* 📥 Export conversations
* 📤 Import conversations
* 🔄 Regenerate responses
* ⛔ Stop AI generation
* 📝 Markdown support
* 💻 Code block rendering
* 📋 Copy responses and code
* ⚙️ AI settings
* 💾 Local conversation history
* 📱 Responsive mobile interface
* 🧩 Ollama model selector
* 🛡️ Local-first architecture

---

# 🛠️ Languages & Technologies

### Languages

* TypeScript
* JavaScript
* HTML
* CSS

### Framework & UI

* Next.js
* React
* Tailwind CSS

### AI

* Ollama
* Qwen3 8B

### Storage

* Browser Local Storage

### Development

* Node.js
* npm
* Git
* GitHub
* Vercel

---

# 🧠 How meGPT Works

meGPT does not use OpenAI, Gemini, Claude, or another cloud AI API for its default AI generation.

The application communicates with **Ollama**, which runs Qwen3 directly on your computer. Qwen3 officially supports running through Ollama, including the `qwen3:8b` model.

```text
                YOU
                 │
                 ▼
            ┌─────────┐
            │  meGPT  │
            │ Next.js │
            └────┬────┘
                 │
                 ▼
          ┌─────────────┐
          │   Ollama    │
          │ localhost   │
          └──────┬──────┘
                 │
                 ▼
          ┌─────────────┐
          │  Qwen3 8B   │
          │ Local Model │
          └──────┬──────┘
                 │
                 ▼
              RESPONSE
```

Ollama normally exposes its local API at `localhost:11434`, which is why the application needs Ollama running on the same computer.

---

# 🚀 Getting Started

## Requirements

Before installing meGPT, you need:

* Windows, macOS, or Linux
* Node.js
* npm
* Ollama
* Qwen3 8B
* Enough RAM/storage to run the model

---

# 1. Install Ollama

Download Ollama from:

https://ollama.com/

Install it normally.

After installation, open your terminal and check:

```bash
ollama --version
```

If Ollama is installed correctly, you should see its version.

---

# 2. Download Qwen3 8B

Run:

```bash
ollama pull qwen3:8b
```

This downloads the Qwen3 8B model to your computer.

You can check your installed models with:

```bash
ollama list
```

You should see:

```text
qwen3:8b
```

Qwen's documentation also lists `ollama run qwen3:8b` as the command for running the Qwen3 8B model through Ollama.

---

# 3. Test Qwen3

Before running meGPT, make sure Qwen3 works.

Run:

```bash
ollama run qwen3:8b
```

Then type something like:

```text
Hello, introduce yourself.
```

If Qwen3 responds, your AI model is working.

To exit the model:

```text
/bye
```

---

# 4. Clone meGPT

Clone this repository:

```bash
git clone https://github.com/YOUR-USERNAME/YOUR-REPOSITORY.git
```

Then enter the project:

```bash
cd megpt
```

> Replace `YOUR-USERNAME/YOUR-REPOSITORY` with your actual GitHub repository.

---

# 5. Install Dependencies

Inside the `megpt` folder, run:

```bash
npm install
```

This installs all required Next.js, React, TypeScript, and other project dependencies.

---

# 6. Start Ollama

Make sure Ollama is running on your computer.

You can also start the service manually with:

```bash
ollama serve
```

Keep Ollama running while using meGPT. Qwen's documentation notes that the Ollama service needs to remain available when using its API.

---

# 7. Start meGPT

Open another terminal inside the `megpt` folder and run:

```bash
npm run dev
```

You should see something similar to:

```text
Local: http://localhost:3000
```

Open:

```text
http://localhost:3000
```

You should now see meGPT.

---

# ✅ That's It

Your setup should now look like:

```text
Your Computer
│
├── meGPT
│   └── localhost:3000
│
└── Ollama
    └── Qwen3 8B
        └── localhost:11434
```

When you send a message:

```text
You
 ↓
meGPT
 ↓
Ollama
 ↓
Qwen3 8B
 ↓
meGPT
 ↓
You
```

---

# 📱 Use meGPT on Your Phone

You can also use meGPT from your phone while your phone and computer are connected to the **same Wi-Fi network**.

### Step 1 — Start meGPT on your computer

Run:

```bash
npm run dev -- --hostname 0.0.0.0
```

### Step 2 — Find your computer's local IP

On Windows:

```bash
ipconfig
```

Find your Wi-Fi **IPv4 Address**.

For example:

```text
IPv4 Address: 192.168.1.7
```

### Step 3 — Open meGPT on your phone

Connect your phone to the same Wi-Fi.

Then open:

```text
http://192.168.1.7:3000
```

Replace `192.168.1.7` with your computer's actual IPv4 address.

### Important

Your computer must remain:

* Turned on
* Connected to Wi-Fi
* Running Ollama
* Running meGPT

This method is for devices connected to the same local network.

---

# 🌐 About the Vercel Version

The project also has a Vercel deployment:

https://megpt-coral.vercel.app/

You can use it to see the meGPT interface and understand how the project looks.

However, the current AI architecture is **local-first**.

Vercel hosts the web interface, but it cannot directly access the Ollama installation running on your personal computer.

Therefore:

```text
❌ Vercel
   ↓
   Your Computer's localhost
   ↓
   Ollama
```

does not work for public visitors.

For a fully public cloud version, meGPT would need a separate online AI backend running the model.

---

# 🔐 Privacy

meGPT is designed around local AI processing.

Your prompts are sent to your local Ollama instance instead of requiring a third-party cloud AI API.

The application also stores conversation history locally in your browser.

```text
Your Prompt
     ↓
   meGPT
     ↓
  Local Ollama
     ↓
   Qwen3 8B
     ↓
   Response
```

No OpenAI API key, Gemini API key, or Claude API key is required for the default setup.

> Local processing improves privacy, but your computer, browser, operating system, network, and other software can still have their own logging or telemetry.

---

# 📁 Project Structure

```text
megpt/
│
├── app/
│   ├── api/
│   └── ...
│
├── components/
│
├── lib/
│
├── public/
│
├── types/
│
├── package.json
├── tsconfig.json
├── next.config.*
└── README.md
```

---

# 🧪 Development Commands

### Start development server

```bash
npm run dev
```

### Start with network access

```bash
npm run dev -- --hostname 0.0.0.0
```

### Run lint

```bash
npm run lint
```

### Create production build

```bash
npm run build
```

---

# ⚠️ Troubleshooting

## Ollama is not connecting

Make sure Ollama is running.

Try:

```bash
ollama serve
```

Then check that Qwen3 is installed:

```bash
ollama list
```

If `qwen3:8b` is missing:

```bash
ollama pull qwen3:8b
```

---

## meGPT opens but AI does not respond

Check these three things:

```text
1. Ollama is running
2. qwen3:8b is installed
3. npm run dev is running
```

Test Qwen directly:

```bash
ollama run qwen3:8b
```

If Qwen works directly but meGPT doesn't, check the terminal where `npm run dev` is running for an error.

---

## Phone cannot open meGPT

Make sure:

* Computer and phone are on the same Wi-Fi
* You used the computer's correct IPv4 address
* meGPT was started with:

```bash
npm run dev -- --hostname 0.0.0.0
```

* Your computer is not blocking the connection with its firewall

---

# 🗺️ Roadmap

* [x] Local Qwen3 integration
* [x] Streaming responses
* [x] Conversation history
* [x] Conversation search
* [x] Import/export
* [x] Model selector
* [x] Temperature control
* [x] Custom system prompt
* [x] Responsive UI
* [x] Mobile local-network access
* [ ] PWA / installable mobile experience
* [ ] Optional cloud AI backend
* [ ] Authentication
* [ ] Multi-user cloud deployment

---

# 📜 License

Add your preferred license here.

---

## Built With

**Next.js · React · TypeScript · Tailwind CSS · Ollama · Qwen3**

### meGPT

> **Your AI. Your machine.**
