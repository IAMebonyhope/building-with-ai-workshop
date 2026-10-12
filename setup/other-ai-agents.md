# Other AI Coding Agents

⬅️ [Back to the workshop README](../README.md)

There are many AI coding agents, and new ones appear all the time. **For this workshop you only need GitHub Copilot** (in VS Code and the CLI). This page is a short comparison so you know what's out there, and what to use if you run out of free Copilot requests.

> 📅 Pricing and free tiers were checked in **October 2026** on each tool's official site. These change often, so always check the official link before signing up.

---

## Quick comparison

| Tool | What it is | Where it runs | Free tier? | Paid plan needed for workshop-style use? | Official getting-started docs |
| --- | --- | --- | --- | --- | --- |
| **GitHub Copilot in VS Code** ⭐ | GitHub's AI assistant built into VS Code: chat, inline suggestions, agent mode | IDE (VS Code) | ✅ **Copilot Free**: 2,000 suggestions/month, limited chat and agent requests | **No.** The workshop is designed to fit in Copilot Free. | [Set up Copilot in VS Code](https://code.visualstudio.com/docs/copilot/setup) |
| **GitHub Copilot CLI** ⭐ | GitHub Copilot as a terminal agent | Terminal | ✅ Included in Copilot Free (shares the same limited allowance) | **No**, but watch your allowance | [Install Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli) |
| **Claude Code** | Anthropic's coding agent | Terminal (also a VS Code extension and desktop app) | ❌ Not in the free Claude plan | **Yes.** Claude Pro ($20/month) or higher, or API billing. | [Claude Code setup](https://code.claude.com/docs/en/setup) · [our guide](claude-code-setup.md) |
| **OpenAI Codex** | OpenAI's coding agent | Desktop app, terminal (CLI), IDE extension, web | ⚠️ Limited. Codex is included in ChatGPT Free for quick tasks in the desktop app. | **Yes, for the CLI.** ChatGPT Plus ($20/month) is the lowest plan that lists the Codex CLI. | [Codex docs](https://developers.openai.com/codex) · [pricing](https://developers.openai.com/codex/pricing) |
| **Gemini CLI → Antigravity CLI** | Google's terminal agent | Terminal | ⚠️ **Changed in June 2026.** Gemini CLI stopped serving free personal accounts on 18 June 2026 and was replaced by **Antigravity CLI**, which has a free individual tier with a weekly usage limit. | Not for light use, but the weekly limit is small | [Gemini CLI quotas and transition notice](https://geminicli.com/docs/resources/quota-and-pricing/) · [Antigravity](https://antigravity.google/download) |
| **Cursor** | A separate code editor (based on VS Code) with AI built in | IDE (its own app) | ✅ **Hobby** plan: free, no credit card, limited agent requests | Not for light use. Pro is $20/month. | [Cursor docs](https://docs.cursor.com) · [pricing](https://cursor.com/pricing) |

⭐ = used in the workshop

---

## Our recommendation

1. **Install GitHub Copilot in VS Code and GitHub Copilot CLI.** They're free with Copilot Free, beginner-friendly, work on Windows and macOS, and can read your project, edit files, and run tests. That covers everything in the workshop.
2. **Optional:** if you already pay for **Claude Pro** or **ChatGPT Plus**, you can use Claude Code or Codex CLI instead of Copilot CLI. The workshop prompts work with any of these agents.
3. **Don't install everything.** One working agent is better than four half-configured ones.

---

## If you run out of Copilot Free requests

Copilot Free has a monthly limit. If you hit it before or during the workshop, here are the most practical **free** options:

| Option | Why | Notes |
| --- | --- | --- |
| **Pair with a neighbour** | Simplest. You learn just as much by driving together. | Recommended during the live session |
| **Cursor (Hobby plan)** | Free, no credit card, looks and works like VS Code, includes an AI agent that can edit files and run commands | Install from [cursor.com](https://cursor.com). Open the `simple-expense-tracker` folder and use its agent chat with the workshop prompts. Its free agent requests are limited too. |
| **Antigravity CLI (free individual tier)** | Free terminal agent from Google, the closest free replacement for a terminal agent | Weekly usage limit. Install from [antigravity.google](https://antigravity.google/download). It's newer, and we haven't tested it with this workshop. |
| **Wait for your monthly reset** | Copilot Free resets every month | Check your usage by clicking the Copilot icon in VS Code's Status Bar |

> ⚠️ When you try other tools, **only install software from the official websites linked above**, and never paste API keys or passwords into prompts.

---

⬅️ [Back to the workshop README](../README.md) · [Copilot CLI setup](copilot-cli-setup.md) · [Claude Code setup](claude-code-setup.md)
