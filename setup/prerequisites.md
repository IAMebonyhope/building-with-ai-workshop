# Prerequisites

This page explains what you need before the workshop, and walks you through installing **Node.js**, the first tool on the list.

⬅️ [Back to the workshop README](../README.md)

---

## What you need

| Item | Why you need it | Cost |
| --- | --- | --- |
| A laptop running **Windows 10/11** or **macOS 13+** | To follow along hands-on | n/a |
| A reliable **internet connection** | AI agents run in the cloud | n/a |
| Permission to **install software** on your laptop | Some work laptops block installs. Check with your IT team early. | n/a |
| A **GitHub account** | To use GitHub Copilot and download the project | Free |
| **Node.js** (22.12 or newer) | To run the starter app and install Copilot CLI | Free |
| **Visual Studio Code** | Code editor where you'll use Copilot Chat | Free |
| **Git** | To download the project and save your work | Free |
| **GitHub Copilot** (Free plan) | The main AI coding agent we'll use | Free |
| **GitHub Copilot CLI** | The AI agent you'll use in the terminal | Free (uses your Copilot Free allowance) |

> 💳 **You do not need to pay for anything.** Every required tool is free. A few *optional* tools (like Claude Code) need a paid plan, and those are clearly labelled.

---

## A quick introduction to the terminal

Many steps in this workshop use the **terminal**: a window where you type commands instead of clicking buttons. Don't worry if you've never used one. You'll copy and paste commands from these guides.

**How to open a terminal:**

| Windows | macOS |
| --- | --- |
| Press the **Windows key**, type `PowerShell`, and press **Enter**. | Press **Cmd + Space**, type `Terminal`, and press **Enter**. |

**How to run a command:** paste the command (in grey boxes like the one below) into the terminal and press **Enter**.

```bash
node --version
```

Later, you'll also use the terminal **built into VS Code**, so you won't have to switch windows.

> 💡 **Tip:** After installing new software, **close and reopen your terminal** so it can find the new commands. This fixes most "command not found" errors.

---

## Install Node.js

**What is Node.js?** Node.js lets your computer run JavaScript outside a web browser. The starter app uses it to run its development server and tests, and it comes with **npm**, a tool for installing JavaScript packages.

You need **Node.js 22.12 or newer**. We recommend the current **LTS** (Long-Term Support) version.

### Windows

1. Go to <https://nodejs.org/en/download>.
2. Download the **LTS** version **Windows Installer (.msi)**.
3. Run the installer and accept the default options. If you're asked about "Tools for Native Modules", you can leave it **unchecked**.
4. Close and reopen PowerShell.

<details>
<summary>Prefer the command line? (Windows)</summary>

```powershell
winget install OpenJS.NodeJS.LTS
```
</details>

### macOS

1. Go to <https://nodejs.org/en/download>.
2. Download the **LTS** version **macOS Installer (.pkg)**.
3. Open the downloaded file and follow the installer steps.
4. Close and reopen Terminal.

<details>
<summary>Prefer Homebrew? (macOS)</summary>

If you already use [Homebrew](https://brew.sh):

```bash
brew install node
```
</details>

### Verify Node.js

Run these two commands:

```bash
node --version
npm --version
```

✅ **Success looks like:** `node --version` prints **v22.12.0 or higher** (for example `v24.11.0`), and `npm --version` prints a version number (for example `11.6.0`).

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `node` or `npm` is "not recognized" / "command not found" | Close and reopen the terminal. If it still fails, restart your computer, then reinstall Node.js. |
| `node --version` shows v20 or older | Install the current LTS version from <https://nodejs.org>. The new version replaces the old one. |
| **Windows:** "running scripts is disabled on this system" when running `npm` | Run this once in PowerShell, then try again: `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` |
| Your work laptop blocks installers | Ask your IT team for help, or use a personal laptop for the workshop. |

---

**Next step:** ➡️ [Create a free GitHub account](github-setup.md)
