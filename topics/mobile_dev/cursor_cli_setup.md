# Cursor + CLI Setup Guide for Flutter Development

This guide explains how to **download Cursor**, configure it with AI providers and coding CLIs (like Codex and Kilo Code), and enable Flutter support.  
It is written for beginners and includes notes on **pricing and limits** for free users.

---

## 1. Install Cursor (the Editor)

1. Go to [cursor.sh](https://cursor.sh) and download the installer for your OS (Windows, macOS, or Linux).  
2. Install and open Cursor.  
3. Go to **Settings → Models / API Keys**.  
   - You can either use **Cursor’s built-in free tier** or provide your own API keys (OpenAI, Anthropic, etc.).

### Pricing (Free vs Pro)
- **Free plan**: limited number of AI requests per day (commonly ~50/day, varies by model).  
- **Pro plan**: higher daily limits, priority access to GPT‑4/Claude models, and more context window.  
- **Bring-your-own-key (BYOK)**: if you add your own OpenAI or Anthropic key, usage is billed directly by the provider (you pay only for what you use).

> Tip: For consistent heavy usage, BYOK is usually cheaper than hitting free-tier limits.

---

## 2. Add Flutter/Dart Support in Cursor

1. Open Extensions panel (**Ctrl/Cmd+Shift+X**).  
2. Install:
   - **Flutter** extension  
   - **Dart** extension (installed automatically with Flutter).  
3. Restart Cursor.  
4. In the integrated terminal, run:
   ```bash
   flutter doctor
   ```
   Fix any issues it shows (e.g., accept Android licenses).

Now Cursor will provide autocomplete, debugging, and syntax support for Flutter projects.

---

## 3. Install OpenAI Codex CLI

**What it is**: Codex CLI is a command-line agent that can plan, edit, and run code tasks in your terminal.  
It complements Cursor’s in-editor AI by handling workflow automation.

### Install
```bash
# Node (global)
npm i -g @openai/codex

# Or on macOS with Homebrew
brew install codex
```

### Configure
Run once:
```bash
codex
```
Follow login or API prompts. Recent builds allow **ChatGPT account login** so you don’t always need an API key.

### Pricing & Limits
- **Free tier**: small daily request allowance when signed in with ChatGPT account (similar to ChatGPT web limits).  
- **With OpenAI API key**: usage billed per token (GPT‑4o, GPT‑4‑Turbo, GPT‑3.5). Costs are the same as OpenAI’s published rates.

---

## 4. Install Kilo Code (AI Coding Agent Extension)

**What it is**: Kilo Code is an open-source VS Code extension (works in Cursor) that automates planning, building, testing, and repairing code.

### Install
1. In Cursor, open Extensions (Ctrl/Cmd+Shift+X).  
2. Search **Kilo Code** and install.  
3. Open Kilo Code Settings → add your provider (OpenAI, Claude, Gemini, etc.).

### Pricing & Limits
- **Extension itself**: Free.  
- **Usage**: depends on the provider API key you configure.  
  - Example: with an OpenAI key, you pay OpenAI rates per request.  
  - With Anthropic/Claude, usage billed per their pricing.

---

## 5. Verify Flutter Toolchain Works in Cursor

1. Open your Flutter project in Cursor.  
2. In terminal, run:
   ```bash
   flutter --version
   flutter doctor
   flutter devices
   ```
3. Start an Android emulator from Android Studio (Device Manager) or connect a physical Android phone with USB debugging enabled.  
4. Run the sample app:
   ```bash
   flutter run
   ```

---

## 6. Quick Setup Checklist

- [ ] Cursor installed and logged in.  
- [ ] Flutter & Dart extensions installed.  
- [ ] Codex CLI installed (`npm i -g @openai/codex` or `brew install codex`).  
- [ ] Kilo Code extension installed.  
- [ ] `flutter doctor` mostly green; emulator runs.  

---

## Example: First AI-Assisted Loop

1. Open your Flutter project in Cursor.  
2. In Cursor Chat, paste your wireframe notes:  
   > “Create a Flutter UI shell with `go_router`, light/dark theme, and placeholder pages (Home, Detail, Settings). Use Riverpod for state.”  
3. Run the app:  
   ```bash
   flutter run
   ```
4. Use Codex CLI in terminal to scaffold tests:  
   ```bash
   codex "Write widget tests for HomePage, add golden test baseline, and fix analyzer warnings."
   ```
5. Use Kilo Code’s workflow panel to implement or refactor features.

---

✅ You now have Cursor + Codex CLI + Kilo Code ready to accelerate Flutter app development!