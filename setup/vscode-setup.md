# Install Visual Studio Code

⬅️ [Back to the workshop README](../README.md) · Previous: [GitHub account](github-setup.md)

---

## What is VS Code?

**Visual Studio Code** (VS Code) is a free code editor from Microsoft. It's where you'll read and edit code, run commands, and chat with GitHub Copilot.

## Why are we using it?

- **GitHub Copilot is built in.** You can chat with it, and let it edit files, right next to your code.
- It has a **built-in terminal**, so you can run commands without leaving the editor.
- It's free, popular, and works the same way on Windows and macOS.

---

## Install VS Code

Download it from the official site: <https://code.visualstudio.com/download>

### Windows

1. Download the **Windows** installer ("User Installer" is fine).
2. Run it and accept the license.
3. On the **Select Additional Tasks** screen, make sure these are ticked:
   - ✅ **Add to PATH** (lets you open VS Code from the terminal with `code .`)
   - ✅ **Add "Open with Code" action to Windows Explorer file context menu** (optional, but handy)
4. Finish the installation and open VS Code.

### macOS

1. Download the **Mac** version (Universal works on all Macs).
2. Open the downloaded `.zip` file if it doesn't open by itself, and drag **Visual Studio Code.app** into your **Applications** folder.
3. Open VS Code from Applications.
4. **Enable the `code` command:** in VS Code, press **Cmd + Shift + P**, type `shell command`, and choose **Shell Command: Install 'code' command in PATH**.

### Verify the `code` command

Close and reopen your terminal, then run:

```bash
code --version
```

✅ **Success looks like:** a version number, such as `1.105.0`, followed by a few more lines.

---

## How to open a project folder

You'll do this with the starter project later. There are two ways:

**From VS Code:** choose **File → Open Folder…** (macOS: **File → Open…**), select the project folder, and click **Open** / **Select Folder**.

**From the terminal:** go into the folder and type `code .`. The `.` means "this folder".

```bash
cd simple-expense-tracker
code .
```

> If VS Code asks **"Do you trust the authors of the files in this folder?"**, choose **Yes, I trust the authors** for the workshop project. This allows extensions and Copilot to work fully.

## How to open the integrated terminal

The **integrated terminal** is a terminal inside VS Code, already opened in your project folder.

| Windows | macOS |
| --- | --- |
| Press **Ctrl + `** (the backtick key, usually below Esc) | Press **Ctrl + `** |
| or menu **View → Terminal** | or menu **View → Terminal** |

The terminal opens at the bottom of the window. You can open more than one with the **+** button, which is useful for running the app in one terminal and Copilot CLI in another.

> 🪟 **Windows tip:** after you install PowerShell 7 in the [Copilot CLI setup](copilot-cli-setup.md#windows-install-powershell-7-first), set it as VS Code's default terminal. Click the **⌄** next to **+** in the terminal panel → **Select Default Profile** → **PowerShell** (the one whose path contains `PowerShell\7`).

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `code` is not recognized (Windows) | Reinstall VS Code and make sure **Add to PATH** is ticked, then restart your terminal. |
| `code: command not found` (macOS) | Run **Shell Command: Install 'code' command in PATH** from the Command Palette (Cmd + Shift + P). Make sure VS Code is in your **Applications** folder, not Downloads. |
| The terminal panel doesn't appear | Use the menu **View → Terminal**. |

---

**Next step:** ➡️ [Install and set up Git](git-setup.md)
