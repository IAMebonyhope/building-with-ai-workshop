# Install GitHub Copilot CLI

⬅️ [Back to the workshop README](../README.md) · Previous: [Copilot in VS Code](github-copilot-setup.md)

---

## What is GitHub Copilot CLI?

**GitHub Copilot CLI** is GitHub Copilot that runs **in your terminal** instead of in an editor. You start it inside a project folder and describe what you want in plain English. It can read your files, make changes, and run commands such as `npm test`, asking for your permission first.

## How is it different from Copilot in VS Code?

| | Copilot in VS Code | Copilot CLI |
| --- | --- | --- |
| Where it runs | Inside the VS Code editor | In any terminal (including VS Code's terminal) |
| How you see changes | Visual diffs in the editor | Diffs in the terminal; open the files in VS Code to inspect them |
| Good for | Exploring code, reviewing edits visually | Agent-style tasks: investigate → change → run tests → repeat |
| Free plan? | ✅ Copilot Free | ✅ Copilot Free, sharing the same monthly allowance |

In the workshop you'll use **both**, so you can compare them.

> ✅ **Free plan availability (checked October 2026):** GitHub's [plan documentation](https://docs.github.com/en/copilot/concepts/billing/individual-plans) states that "all plans include Copilot CLI", including **Copilot Free**. Every prompt uses your monthly Copilot allowance, the **same** allowance as Copilot Chat in VS Code, so use it sparingly before the workshop. See [Copilot Free limits](github-copilot-setup.md#copilot-free-what-you-get).
>
> Copilot CLI is a newer product, and its features may change. If it doesn't work for you on the day, you can do every workshop part with **Copilot Chat in Agent mode** in VS Code instead.

---

## Before you install

You need:

- An active GitHub Copilot plan. **Copilot Free counts.** Do the [Copilot in VS Code](github-copilot-setup.md) setup first.
- **Node.js 22 or newer** if you install with npm. You already installed it in [Prerequisites](prerequisites.md#install-nodejs).
- **Windows only:** **PowerShell 7** (Copilot CLI needs PowerShell v6 or higher, and Windows comes with the older v5.1). See below.

### Windows: install PowerShell 7 first

1. Open **PowerShell** and run:

   ```powershell
   winget install --id Microsoft.PowerShell --source winget
   ```

2. Close the window. From now on, open **PowerShell 7**: press the Windows key and type `pwsh`, or look for **PowerShell 7** in the Start menu. It has a black icon, unlike the blue one for the older Windows PowerShell.
3. Check the version:

   ```powershell
   $PSVersionTable.PSVersion
   ```

   ✅ The **Major** number should be **7**.

More options: [Installing PowerShell on Windows](https://learn.microsoft.com/powershell/scripting/install/installing-powershell-on-windows)

> 💡 Set PowerShell 7 as the default terminal in VS Code. See the [tip in the VS Code guide](vscode-setup.md#how-to-open-the-integrated-terminal).

---

## Install Copilot CLI

Pick **one** method. These are the official commands from [GitHub's install guide](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli).

### Windows (in PowerShell 7)

```powershell
winget install GitHub.Copilot
```

Or, using npm:

```powershell
npm install -g @github/copilot
```

### macOS

Using npm (works for everyone who installed Node.js):

```bash
npm install -g @github/copilot
```

Or, with Homebrew:

```bash
brew install --cask copilot-cli
```

Or, with the install script:

```bash
curl -fsSL https://gh.io/copilot-install | bash
```

> **macOS npm permission error (`EACCES`)?** Don't use `sudo`. See [Troubleshooting](#troubleshooting) below.

After installing, **close and reopen your terminal**.

---

## Launch and sign in

1. Go to a project folder. You'll use the starter project, but any folder works for testing.

   ```bash
   cd simple-expense-tracker
   ```

2. Start Copilot CLI:

   ```bash
   copilot
   ```

3. **Trust the folder:** the first time, Copilot asks whether you trust the files in this folder. Choose **Yes** for the workshop project.
4. **Sign in:** if you're not logged in, type this command inside Copilot CLI and press **Enter**:

   ```text
   /login
   ```

   Follow the on-screen instructions. Usually you copy a one-time code, open the link in your browser, paste the code, and authorize. You only need to do this once.

### Useful things to know inside Copilot CLI

| Action | How |
| --- | --- |
| Ask for something | Type your request in plain English and press **Enter** |
| Approve an action | When Copilot wants to edit a file or run a command, it asks. Read the request, then choose to allow it once, allow similar actions, or deny it. |
| See help and shortcuts | Type `/help` |
| Stop Copilot while it's working | Press **Ctrl + C** |
| Exit Copilot CLI | Press **Ctrl + C** when it's idle (you may need to press it twice), or type `/exit` |

> 🛡️ **Copilot won't change your files without your approval.** Always read what it's about to do before saying yes, especially for commands you don't recognise.

---

## Verify that Copilot CLI is working

1. In a terminal, go to any folder and run `copilot`.
2. Type:

   ```text
   What files are in this folder? Answer in one short sentence.
   ```

✅ **Success looks like:** Copilot lists or summarises the files. It may ask for permission to look at the folder first.

Then exit with **Ctrl + C**.

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `copilot` is not recognized / command not found | Close and reopen the terminal. If you used npm, run `npm install -g @github/copilot` again and watch for errors. |
| **Windows:** errors about PowerShell version | You're in the old Windows PowerShell (v5.1). Open **PowerShell 7** (`pwsh`) instead. |
| **macOS:** `EACCES: permission denied` during `npm install -g` | Don't use `sudo`. Use the Homebrew or install-script method instead, or follow [npm's guide to fixing permissions](https://docs.npmjs.com/resolving-eacces-permissions-errors-when-installing-packages-globally). |
| npm install fails with `ignore-scripts` errors | Run `npm_config_ignore_scripts=false npm install -g @github/copilot` (macOS), as described in GitHub's install guide. |
| "You don't have access to Copilot" / subscription error | Make sure you completed [Copilot in VS Code setup](github-copilot-setup.md) with the **same** GitHub account, so that Copilot Free is active. If your account gets Copilot through an organization, an admin may have disabled the CLI. |
| Login code page won't open | Copy the URL shown in the terminal and paste it into your browser manually. |
| Copilot stops responding / limit reached | Your monthly Copilot Free allowance is used up. See [free alternatives](other-ai-agents.md#if-you-run-out-of-copilot-free-requests). |

Official docs: [Getting started with Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/cli-getting-started)

---

**Next step:** ➡️ [Download, run, and verify the starter app](verify-setup.md)

Optional: [Claude Code](claude-code-setup.md) · [Other AI coding agents](other-ai-agents.md)
