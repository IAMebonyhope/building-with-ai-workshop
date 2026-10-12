# Download, Run, and Verify the Starter App

This is the final setup step. You'll download the **Simple Expense Tracker** (the app is called *ExpenseFlow*), run it, and check that every tool works. Then you're ready for the workshop. 🎉

⬅️ [Back to the workshop README](../README.md) · Previous: [Copilot CLI](copilot-cli-setup.md)

---

## Step 1: Clone the repository

**Cloning** means downloading a copy of a GitHub repository, including its full history, to your computer.

First, choose where to keep the project, for example your home folder or a `projects` folder. Open a terminal there, then run:

```bash
git clone https://github.com/IAMebonyhope/simple-expense-tracker.git
```

**What this does:** creates a new folder called `simple-expense-tracker` containing the app's code.

> 💡 **Not sure where you are?** On a fresh terminal you're usually in your home folder (`C:\Users\YourName` on Windows, `/Users/yourname` on macOS). That's a fine place to clone into.

## Step 2: Open the project

```bash
cd simple-expense-tracker
code .
```

**What these commands do:**

- `cd simple-expense-tracker`: **c**hange **d**irectory, moving the terminal *into* the project folder. Most commands below must run from inside this folder.
- `code .`: opens the current folder (`.`) in VS Code.

If VS Code asks **"Do you trust the authors of the files in this folder?"**, click **Yes, I trust the authors**.

From now on, use the **integrated terminal in VS Code** (**Ctrl + `**). It opens in the project folder automatically.

## Step 3: Install dependencies

The project uses **npm** (it has a `package.json` and a `package-lock.json`). In VS Code's terminal, run:

```bash
npm install
```

**What this does:** downloads the libraries the app needs (React, Vite, testing tools) into a `node_modules` folder. It takes 30–90 seconds, and you only need to do it once.

✅ **Success looks like:** a message ending with something like `added 150 packages` and `found 0 vulnerabilities`. Warnings (`npm warn ...`) are usually fine. Red `npm error` lines are not. See [Troubleshooting](#troubleshooting).

## Step 4: Run the application

```bash
npm run dev
```

**What this does:** starts a **development server**, a small web server on your own computer that serves the app and reloads it whenever you save a file.

✅ **Success looks like:**

```text
  VITE v8.x.x  ready in 500 ms

  ➜  Local:   http://localhost:5173/
```

**Open the app:** hold **Ctrl** (Windows) or **Cmd** (macOS) and click the `http://localhost:5173/` link, or type that address into your browser.

> ℹ️ `localhost` means "this computer". The app only runs on your machine, and nobody else can see it.

**To stop the server:** click in the terminal and press **Ctrl + C**. Leave it running while you work. Open a **second terminal** (the **+** button in the terminal panel) for other commands.

## Step 5: Verify your setup

Work through this checklist. **Every item should be ✅ before the workshop.**

### The app

- [ ] The browser shows **ExpenseFlow — Personal Expense & Budget Tracker**.
- [ ] You can see the **Dashboard** with three cards: **Total Allocated Budget** (₦270,000.00), **Total Expenses**, and **Remaining Balance**.
- [ ] You can see **Category Budgets** (six categories) and **Recent Expenses** (a list of expenses).
- [ ] Amounts are shown in Naira (₦).

> If your numbers look different (for example, you opened the app before and added expenses), scroll to the bottom and click **↺ Reset Demo Data**.

### The tests

In a second terminal (inside the project folder), run:

```bash
npm test
```

- [ ] The output ends with **`Tests  40 passed (40)`** (the exact number may differ slightly).

### VS Code and Copilot Chat

- [ ] The `simple-expense-tracker` folder is open in VS Code, and you can see `src`, `tests`, and `README.md` in the Explorer sidebar.
- [ ] Open Copilot Chat (**Ctrl + Alt + I** / **Ctrl + Cmd + I**), choose **Ask**, and send:

  ```text
  In one sentence, what does this project do?
  ```

  Copilot should describe an expense tracker.

### Copilot CLI

In VS Code's terminal (inside the project folder):

```bash
copilot
```

- [ ] Copilot CLI starts, and you're signed in (run `/login` if asked).
- [ ] Ask it: `Which command starts this app? Answer in one sentence.` It should mention `npm run dev`.
- [ ] Exit with **Ctrl + C**.

### Optional agents

- [ ] If you're using [Claude Code](claude-code-setup.md) or another agent, start it in the project folder and ask the same question.

> 💡 You've now used about 2–3 Copilot requests. **Stop here** and save the rest of your free allowance for the workshop.

🎉 **All done? You're ready for the workshop!** If anything isn't working, check the troubleshooting table below. If you're still stuck, arrive 10 minutes early and ask for help.

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| `git clone` fails: "Repository not found" | Check the URL for typos: `https://github.com/IAMebonyhope/simple-expense-tracker.git` |
| `fatal: destination path 'simple-expense-tracker' already exists` | You already cloned it. Run `cd simple-expense-tracker` and continue from Step 2. |
| `npm` / `node` not recognized | Install Node.js. See [Prerequisites](prerequisites.md#install-nodejs). Then **close and reopen** VS Code. |
| `npm install` shows `EBADENGINE` or "Unsupported engine" | Your Node.js is too old. You need **22.12 or newer**. Install the LTS version from <https://nodejs.org>, delete the `node_modules` folder, and run `npm install` again. |
| `npm install` fails with network errors | Check your internet connection. On a work network, try a mobile hotspot. Then run `npm install` again. |
| `npm ERR! enoent ... package.json` | You're not inside the project folder. Run `cd simple-expense-tracker` first. |
| **Windows:** "running scripts is disabled on this system" | Run `Set-ExecutionPolicy -Scope CurrentUser RemoteSigned` once in PowerShell, then try again. |
| `Port 5173 is in use` | Vite automatically uses the next free port (for example 5174). Open the URL shown in the terminal. |
| Browser shows a blank page | Check the terminal for red errors. Make sure `npm install` finished successfully. Try a hard refresh: **Ctrl + Shift + R** / **Cmd + Shift + R**. |
| The app shows different numbers from this guide | Click **↺ Reset Demo Data** at the bottom of the page. |
| `code .` doesn't open VS Code | See [VS Code troubleshooting](vscode-setup.md#troubleshooting), or open the folder via **File → Open Folder**. |
| `copilot` not recognized | See [Copilot CLI troubleshooting](copilot-cli-setup.md#troubleshooting). |

---

**Next:** read the [workshop activities](../README.md#workshop-activities), or skim the [prompting tips](../resources/prompting-tips.md) before the session.
