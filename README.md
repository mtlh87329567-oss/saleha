# API Token Management Solution
A lightweight, local-first API token management utility designed to help developers simplify credential workflows, safely inject tokens, and avoid hardcoding secrets.

## 🚀 Features
- **Local-First & Secure:** Tokens are encrypted and stored strictly on your local machine using [XDG / Keyring].
- **Dynamic Key Injection:** Safely inject variables into your active runtime environments without risky sidecars.
- **Provider Agnostic:** Built to seamlessly manage keys for OpenAI, Anthropic, Gemini, DeepSeek, and custom endpoints.
- **Automatic Cooldowns:** Built-in detection for rate limits (HTTP 429) or quota exhaustion.

## 📦 Installation
```bash
# Example installation command (e.g., using npm, pip, or cargo)
npm install -g api-token-manager
```

## ⚙️ Configuration
The tool reads its secure routing definitions from a local sidecar configuration file:

| Environment Variable | Type | Required | Description |
| --- | --- | --- | --- |
| `TOKEN_MANAGER_STORE` | String | No | Path to custom local SQLite database or JSON file. |
| `SECRET_CIPHER_KEY` | String | Yes | Encryption key for securing local storage credentials. |

## 💻 Quick Start & Usage
### 1. Initialize the storage
```bash
token-manager init
```
### 2. Add a new service API credential
```bash
token-manager add --provider openai --key sk-proj-...
```

## 🔒 Security Best Practices
Following secure credential protocols, this tool enforces strict runtime isolation. Never commit plain-text API credentials or `.env` files into your GitHub repository context.

## 📄 License
Distributed under the MIT License. See `LICENSE` for more information.
