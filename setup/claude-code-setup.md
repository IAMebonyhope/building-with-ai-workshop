# Claude Code (Optional)

⬅️ [Back to the workshop README](../README.md)

> ℹ️ **This is optional.** You don't need Claude Code for the workshop. GitHub Copilot in VS Code and Copilot CLI cover everything.

> 💳 **Paid plan required.** Claude Code is **not** included in the free Claude plan. You need a paid **Claude Pro** plan (**$20/month**, or $17/month billed annually) or higher, or an Anthropic Console account with pay-as-you-go API billing. Checked October 2026 on the [Claude pricing page](https://claude.com/pricing) and in the [Claude Code docs](https://code.claude.com/docs/en/setup). Prices can change.

---

## What is Claude Code?

**Claude Code** is an AI coding agent made by Anthropic. Like Copilot CLI, it runs in your **terminal**: you start it inside a project folder, describe what you want, and it reads files, edits code, and runs commands such as tests, asking for permission first. It's also available as a VS Code extension and a desktop app.

If you already pay for Claude, you can use Claude Code instead of Copilot CLI in [Part 2](../workshop/02-debug-total-expenses.md) and [Part 4](../workshop/04-structured-engineering-budget-alerts.md). The prompts are the same.

---

## Install

Official guide: <https://code.claude.com/docs/en/setup>

### macOS

```bash
curl -fsSL https://claude.ai/install.sh | bash
```

Or with Homebrew:

```bash
brew install --cask claude-code
```

### Windows (PowerShell)

```powershell
irm https://claude.ai/install.ps1 | iex
```

Or with WinGet:

```powershell
winget install Anthropic.ClaudeCode
```

> Git for Windows (installed in the [Git setup](git-setup.md)) is recommended on Windows, so Claude Code can use Git Bash.

After installing, **open a new terminal** and check the version:

```bash
claude --version
```

✅ **Success looks like:** a version number, such as `2.1.211 (Claude Code)`.

---

## Sign in

1. Go to your project folder and start Claude Code:

   ```bash
   cd simple-expense-tracker
   claude
   ```

2. Follow the prompts. Your browser opens so you can log in with your **Claude Pro (or higher)** account, or your Anthropic Console account.

## Use it with the starter project

- Always start `claude` **from inside** the `simple-expense-tracker` folder, so it works on the right project.
- Type requests in plain English, just like with Copilot CLI.
- Claude Code asks before editing files or running commands. Read each request before approving it.
- Type `/help` for commands. Press **Ctrl + C** to cancel or exit.

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `claude` is not recognized / command not found | Open a new terminal. If it still fails, see [Troubleshoot installation](https://code.claude.com/docs/en/troubleshoot-install). |
| `'irm' is not recognized` | You're in Command Prompt (CMD), not PowerShell. Open PowerShell and run the command again. |
| Login says your plan doesn't include Claude Code | The free Claude plan doesn't include Claude Code. Use GitHub Copilot for the workshop instead. |
| Check your installation | Run `claude doctor` |

---

⬅️ Back to: [Copilot CLI setup](copilot-cli-setup.md) · [Other AI coding agents](other-ai-agents.md)
