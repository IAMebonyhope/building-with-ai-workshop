# Turn On GitHub Copilot in VS Code

⬅️ [Back to the workshop README](../README.md) · Previous: [Git](git-setup.md)

---

## What is GitHub Copilot?

**GitHub Copilot** is an AI coding assistant made by GitHub. Inside VS Code it can:

- **Suggest code as you type** (grey "ghost text" you accept with **Tab**).
- **Answer questions** about your code in a chat panel ("What does this file do?").
- **Act as an agent**: read your project, edit several files, run terminal commands such as tests, and fix its own mistakes, while asking your permission along the way.

## How it works inside VS Code

Copilot sends the relevant parts of your code, plus your question, to an AI model in the cloud, and shows the answer in VS Code. In **Agent** mode it can also propose file edits and terminal commands. **You stay in control**: you review every change and can keep or undo it.

---

## Copilot Free: what you get

You'll use **GitHub Copilot Free**. It costs nothing and needs no credit card. Here's what it includes, according to GitHub's [plans page](https://github.com/features/copilot/plans) and [plan documentation](https://docs.github.com/en/copilot/concepts/billing/individual-plans), checked in October 2026:

| Feature | Copilot **Free** | Copilot Pro (paid, $10/month) |
| --- | --- | --- |
| Code suggestions as you type | ✅ Up to **2,000 per month** | ✅ More |
| Copilot Chat in VS Code | ✅ Limited (about **50 chat requests per month**) | ✅ More |
| Agent mode (Copilot edits files and runs commands) | ✅ Limited | ✅ More |
| **Copilot CLI** (terminal agent) | ✅ Included, limited | ✅ More |
| Choice of AI model | Automatic selection only | Choose from more models |
| Copilot cloud agent (assign GitHub issues to Copilot) | ❌ | ✅ |

**Important things to know:**

- 🔁 **Chat, agent mode, and Copilot CLI share one monthly allowance** of GitHub "AI Credits". GitHub doesn't publish an exact number for the Free plan, and heavier tasks (like agent mode working through many files) use more of it.
- 📅 The allowance **resets every month**. Unused requests don't carry over.
- 🛑 When you reach the limit, Copilot stops responding until next month (or until you upgrade). **Nothing is charged automatically.**
- 🏢 Copilot Free is only for **individual accounts** that don't already get Copilot through an organization. See [the note in the GitHub setup guide](github-setup.md#important-copilot-through-a-company-or-school).

> 💡 **The workshop is designed to fit inside Copilot Free.** All four parts need roughly **20–25 prompts** in total. To make sure you have enough left:
> - After you've checked that Copilot works (below), **avoid heavy use until the workshop**.
> - If your allowance resets close to the workshop date, even better.

Pricing and limits can change. The [official plans page](https://github.com/features/copilot/plans) is always the source of truth.

---

## Turn on Copilot in VS Code

In current versions of VS Code, Copilot is **built in**. You just need to sign in with GitHub.

1. **Update VS Code** to the latest version: **Help → Check for Updates** (macOS: **Code → Check for Updates**).
2. Look at the **Status Bar** at the bottom of the VS Code window and find the **Copilot icon** (a small face/pilot icon).
3. Hover over it and select **Use AI Features**, or click it and select **Sign in to use Copilot**.
4. Choose **Continue with GitHub**. Your browser opens. Sign in to GitHub and click **Authorize** when asked.
5. Return to VS Code. If your account doesn't have a paid subscription, you're **automatically enrolled in Copilot Free**.

Other ways to sign in: open the **Accounts** menu (person icon, bottom-left) → **Sign in with GitHub to use GitHub Copilot**, or press **Ctrl + Shift + P** (macOS: **Cmd + Shift + P**) and run **GitHub Copilot: Sign in**.

<details>
<summary>Don't see a Copilot icon at all?</summary>

Your VS Code may be older, or AI features may be turned off.

1. Update VS Code to the latest version and restart it.
2. Open the **Extensions** view (**Ctrl + Shift + X** / **Cmd + Shift + X**), search for **GitHub Copilot Chat**, and click **Install**.
3. Check that AI features aren't disabled: open **Settings** (**Ctrl + ,** / **Cmd + ,**), search for `disable AI features`, and make sure it's **unchecked**.

Official guide: [Set up Copilot in VS Code](https://code.visualstudio.com/docs/copilot/setup)
</details>

---

## Open Copilot Chat

| Windows | macOS |
| --- | --- |
| **Ctrl + Alt + I** | **Ctrl + Cmd + I** |

You can also click the **Copilot / chat icon** in the title bar at the top of the window. The **Chat view** opens on the side.

### Choose how Copilot works

At the bottom of the chat box there's a picker (it usually shows **Agent**). The options you'll use:

| Option | What it does | Used in |
| --- | --- | --- |
| **Ask** | Answers questions. **Doesn't change any files.** Safe for exploring. | Part 1 |
| **Agent** | Can edit files and run terminal commands, asking for your approval. | Part 3 |
| **Plan** | Researches your request and writes a step-by-step plan before any code is written. | Optional in Part 4 |

The exact names can differ slightly between VS Code versions.

### Give Copilot context

- Copilot automatically sees the **file that's open** and any code you've **selected**.
- Type **`#`** in the chat box to attach more: `#file` for a specific file, `#codebase` to let it search the whole project.

---

## Verify that Copilot is working

1. Open any folder in VS Code (or wait and use the starter project after [verify setup](verify-setup.md)).
2. Open Copilot Chat (**Ctrl + Alt + I** / **Ctrl + Cmd + I**) and choose **Ask**.
3. Type this and press **Enter**:

   ```text
   In one sentence, what is a React component?
   ```

✅ **Success looks like:** Copilot replies with a short explanation.

> 🔍 **Check your remaining allowance:** click the **Copilot icon** in the Status Bar. It shows your current usage for the month.

---

## Troubleshooting

| Problem | Fix |
| --- | --- |
| Browser sign-in finished, but VS Code still says "Sign in" | Return to VS Code and wait a few seconds. If nothing happens, run **GitHub Copilot: Sign in** from the Command Palette again. If your browser blocks the redirect, allow `vscode://` links. |
| "You have reached your monthly limit" / chat stops responding | Your Copilot Free allowance is used up for this month. See [free alternatives](other-ai-agents.md#if-you-run-out-of-copilot-free-requests), or pair with a neighbour during the workshop. |
| "Copilot is disabled by your organization" | Your account gets Copilot through an organization that has limited it. Use a personal GitHub account. See [this note](github-setup.md#important-copilot-through-a-company-or-school). |
| Chat says it can't access your files | Make sure you opened the **project folder** (File → Open Folder), not a single file, and that you chose **Yes, I trust the authors**. |
| Proxy or firewall errors at work | Try a different network, such as a home Wi-Fi or mobile hotspot. |

More help: [Troubleshooting Copilot in VS Code](https://code.visualstudio.com/docs/copilot/troubleshooting)

---

**Next step:** ➡️ [Install GitHub Copilot CLI](copilot-cli-setup.md)
