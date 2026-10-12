# Install and Set Up Git

⬅️ [Back to the workshop README](../README.md) · Previous: [VS Code](vscode-setup.md)

---

## What is Git?

**Git** is a version control tool. It keeps a history of every change you make to a project, so you can see what changed, save checkpoints, and go back if something breaks.

## Why do you need it?

- To **download (clone)** the starter project from GitHub.
- To **save checkpoints (commits)** between workshop parts. This matters for AI-assisted coding: if an AI agent makes a mess, Git lets you undo it.
- To work on the same app in separate **branches**: one for the vibe-coding attempt, and a clean one for the structured attempt.

---

## Install Git

### Windows

1. Download **Git for Windows** from <https://git-scm.com/downloads/win>.
2. Run the installer. **The default options are fine.** Keep clicking **Next**.
   - On "Choosing the default editor used by Git", you can pick **Use Visual Studio Code as Git's default editor**.
3. Click **Install**, then **Finish**.
4. Close and reopen your terminal.

This also installs **Git Bash**, a terminal some AI agents can use.

<details>
<summary>Prefer the command line? (Windows)</summary>

```powershell
winget install --id Git.Git -e --source winget
```
</details>

### macOS

Open Terminal and run:

```bash
git --version
```

- If Git is already installed, you'll see a version number. You're done.
- If it isn't, macOS shows a pop-up offering to install the **Command Line Developer Tools**. Click **Install**, wait for it to finish, then run `git --version` again.

<details>
<summary>Prefer Homebrew? (macOS)</summary>

```bash
brew install git
```
</details>

More options: <https://git-scm.com/downloads/mac>

---

## Verify the installation

```bash
git --version
```

✅ **Success looks like:** something like `git version 2.51.0`. Any recent version works.

---

## Tell Git who you are (one-time setup)

Git records a name and email with every checkpoint (commit) you save. Set them once. Use the same email as your GitHub account.

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```

Check that it worked:

```bash
git config --global user.name
git config --global user.email
```

> 🔒 **Want to keep your email private?** GitHub gives you a private "noreply" address. Find it under **GitHub → Settings → Emails**, and use it instead.

---

## The few Git commands you'll use

You don't need to memorise these. The workshop guides tell you exactly when to run them.

| Command | What it does |
| --- | --- |
| `git clone <url>` | Downloads a project from GitHub to your computer |
| `git status` | Shows which files have changed |
| `git diff` | Shows exactly what changed, line by line |
| `git add -A` | Selects all your changes to be saved |
| `git commit -m "message"` | Saves a checkpoint with a short description |
| `git switch -c <name>` | Creates a new branch (a separate line of work) and moves to it |
| `git switch main` | Goes back to the main branch |
| `git restore .` | ⚠️ Throws away all *uncommitted* changes. Useful when an AI edit goes wrong. |

> 💡 VS Code also has a **Source Control** panel (the branching icon in the left sidebar, or **Ctrl + Shift + G** / **Cmd + Shift + G**) where you can see changes and diffs visually.

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `git` is not recognized (Windows) | Close and reopen the terminal. If it still fails, reinstall Git for Windows with the default options. |
| macOS install pop-up doesn't appear | Run `xcode-select --install` in Terminal. |
| `Please tell me who you are` when committing | You skipped the one-time setup. Run the two `git config --global` commands above. |

---

**Next step:** ➡️ [Turn on GitHub Copilot in VS Code](github-copilot-setup.md)
