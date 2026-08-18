# 🤖 ULTRON V9

> A personal AI desktop assistant with Gemini-powered conversations, voice interaction, system automation, web search, file search, and optional Telegram remote control.

## ✨ Features

- 🧠 **Gemini AI** — Ask questions and have natural conversations.
- 🎙️ **Voice interaction** — Voice input/output support for hands-free use.
- 💻 **Desktop automation** — Launch supported applications on Windows.
- 📂 **File search** — Search common folders on your computer for files.
- 🌐 **Web search** — Open web searches directly from ULTRON.
- 💬 **Telegram remote control** — Send commands remotely with an authorized Telegram account.
- 🖥️ **Terminal + GUI workflow** — Designed for a Windows virtual environment.
- 🔐 **Environment-based secrets** — API keys and Telegram credentials stay outside the source code.

## 🧩 Architecture

```text
                    ┌────────────────────┐
                    │      ULTRON V9     │
                    └─────────┬──────────┘
                              │
              ┌───────────────┼───────────────┐
              ▼               ▼               ▼
          🧠 Gemini       🎙️ Voice        💬 Telegram
              │               │               │
              └───────────────┼───────────────┘
                              ▼
                     ⚙️ Command Engine
                              │
                 ┌────────────┼────────────┐
                 ▼            ▼            ▼
              📂 Files     🌐 Web       💻 Apps
```

## 📋 Requirements

- Windows 10/11
- Python 3.11+ recommended
- Google Gemini API key
- Optional Telegram bot token and numeric Telegram user ID
- Internet connection for Gemini and Telegram features

> If a dependency does not support your Python version, use a supported release such as Python 3.11 or 3.12.

## 🚀 Installation

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/ULTRON-V9.git
cd ULTRON-V9
```

### 2. Create a virtual environment

Windows CMD:

```cmd
python -m venv .venv
.venv\Scripts\activate
```

PowerShell:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
```

### 3. Install dependencies

```cmd
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Configure Gemini

Windows CMD:

```cmd
setx GEMINI_API_KEY "YOUR_GEMINI_API_KEY"
```

Close and reopen the terminal after using `setx`.

PowerShell for the current session:

```powershell
$env:GEMINI_API_KEY="YOUR_GEMINI_API_KEY"
```

**Never commit your real API key to GitHub.**

### 5. Optional Telegram configuration

```cmd
setx ULTRON_TELEGRAM_TOKEN "YOUR_TELEGRAM_BOT_TOKEN"
setx ULTRON_TELEGRAM_USER_ID "YOUR_NUMERIC_TELEGRAM_USER_ID"
```

Restart the terminal after using `setx`.

If these variables are not configured, Telegram remote control can remain disabled.

## ▶️ Running ULTRON

```cmd
.venv\Scripts\activate
python ultron.py
```

If the project includes a launcher:

```cmd
ultron.bat
```

## 🗣️ Example Commands

```text
hello ultron
open brave
find my physics notes
search web for ChatGPT
what is quantum tunneling?
```

Telegram:

```text
/status
/open brave
/search physics
/web ChatGPT
/ask explain quantum physics
```

## 🔐 Security

ULTRON is intended for use on your own computer and accounts.

- Keep Gemini and Telegram credentials private.
- Never commit API keys, bot tokens, or private configuration files.
- Restrict Telegram control to your own authorized user ID.
- Review automation commands before giving them access to sensitive files or applications.
- Only use ULTRON with systems and accounts you are authorized to control.

## 📁 Project Structure

```text
ULTRON-V9/
├── ultron.py
├── ultron.bat
├── requirements.txt
├── .gitignore
├── README.md
└── assets/
    └── ...
```

Do **not** commit `.venv/`.

## 🛠️ Troubleshooting

### Gemini says no API key was provided

```cmd
echo %GEMINI_API_KEY%
```

If it is empty, configure the key and restart the terminal.

### Telegram times out

Check your internet connection and verify the bot token. Telegram remote control can also be disabled by leaving its environment variables unset.

### Piper is missing

If your version uses Piper for local neural TTS:

```cmd
python -m pip install piper-tts
python -m piper --help
```

### Virtual environment is not activated

You should see something similar to:

```text
(.venv) C:\Users\...\ULTRON-V9>
```

## 🗺️ Roadmap

- [ ] Faster voice response
- [ ] Better conversational memory
- [ ] Modular command plugins
- [ ] Improved Android/Termux version
- [ ] More desktop automation
- [ ] Custom ULTRON-style interface
- [ ] Better logging and diagnostics

## ⚠️ Disclaimer

ULTRON is a personal automation and AI-assistant project. Features that interact with your computer, files, applications, or remote services should be used responsibly and only with systems and accounts you are authorized to control.

## 📄 License

Choose a license appropriate for your project before publishing. The MIT License is a common choice for projects intended to be freely used, modified, and distributed.
