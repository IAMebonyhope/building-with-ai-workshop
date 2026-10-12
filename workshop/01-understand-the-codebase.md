# Part 1: Understand the Codebase with an AI Agent

⬅️ [Back to the workshop README](../README.md) · Next: [Part 2 →](02-debug-total-expenses.md)

⏱️ **About 15 minutes** · 💬 **About 4 Copilot requests**

---

## What you'll learn

How to use an AI agent to **quickly understand a project you've never seen before**: its structure, how data flows through it, and where the important logic lives. This is one of the most useful everyday skills with AI tools, and you'll need this understanding for the rest of the workshop.

## What we're building

Nothing yet! In this part you only **read and ask questions**. No files will change. By the end you should be able to explain:

- What each folder in the project is for
- What happens, step by step, when you add an expense
- How the app saves your data in the browser
- Which values are **stored** and which are **calculated**

## Tool we'll use

**GitHub Copilot Chat in VS Code**, in **Ask** mode. Ask mode answers questions but can't edit files, which makes it safe for exploring.

## Starting point

The fresh starter app that you cloned during [setup](../setup/verify-setup.md). You shouldn't have any changes yet.

---

## Step 1: Open the project

1. Open the `simple-expense-tracker` folder in VS Code (**File → Open Folder**, or `code .` from the terminal).
2. Start the app so you can see it while you learn about it. In the VS Code terminal (**Ctrl + `**), run:

   ```bash
   npm run dev
   ```

   Open <http://localhost:5173> in your browser. If the numbers look different from a fresh start, click **↺ Reset Demo Data** at the bottom of the page.

3. Spend one minute clicking around the app: the dashboard, the category budgets, adding an expense.
4. Open **Copilot Chat** (**Ctrl + Alt + I** on Windows, **Ctrl + Cmd + I** on macOS) and choose **Ask** in the picker at the bottom of the chat box.

## Step 2: Give the AI agent instructions

Send these prompts **one at a time**. Read each answer before sending the next.

**Prompt 1: the big picture**

```text
Explain the architecture of this project. What does each folder do? Keep it beginner-friendly.
```

> 💡 If Copilot only looks at one file, add `#codebase` to the end of the prompt so it searches the whole project.

**Prompt 2: follow the data**

```text
Trace what happens, step by step, when I add a new expense. Name the files and functions involved.
```

**Prompt 3: how data is saved**

```text
How does useLocalStorage work, and when is the sample data written?
```

**Prompt 4: stored vs calculated**

```text
Which values are stored and which are calculated?
```

## Step 3: Review the AI-generated answers

AI agents can be confidently wrong, so **check the answers against the actual code**. Open the files Copilot mentions and confirm:

| Claim to check | Where to look |
| --- | --- |
| `App.jsx` holds the app's main state (`expenses` and `categories`) and passes data and functions down to components as **props** | `src/App.jsx` |
| Each component handles one part of the screen | `src/components/` |
| The data is saved in the browser's `localStorage`, and sample data is only written the **first time** you open the app | `src/hooks/useLocalStorage.js`, `src/data/sampleData.js` |
| Category **spent** and **remaining** amounts are **calculated** from the expenses each time, not stored | `src/utils/expenseCalculations.js` |
| The calculations are plain functions in one utility file | `src/utils/expenseCalculations.js` |

Did Copilot get anything wrong or leave anything out? Note it down. Spotting that is part of the skill.

## Step 4: Run and test

Nothing changed in this part, so this step is about confirming what you learned:

1. In a second terminal, run the test suite:

   ```bash
   npm test
   ```

   ✅ All tests should pass.

2. **Check your understanding in the browser.** Add an expense, then watch which numbers update on the dashboard and in Category Budgets. Refresh the page and confirm the expense is still there. That's `localStorage` at work.

3. Optional (open DevTools with **F12** → **Application** → **Local Storage** → `http://localhost:5173`): you'll see the `expenseflow.expenses` and `expenseflow.categories` keys that Copilot described.

## Step 5: Reflect

- Which answer saved you the most time compared with reading the code yourself?
- Did you find anything Copilot got wrong or skipped? How did you notice?

---

## Expected result

You can explain, in your own words, how the app is organised and how an expense flows from the form → `App.jsx` state → `localStorage` → the dashboard calculations. No files have changed. `git status` shows a clean working tree.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| Copilot gives a generic answer that isn't about this project | Make sure you opened the **folder** (not a single file). Add `#codebase` to your prompt. |
| Copilot tries to edit files | You're in **Agent** mode. Switch the picker to **Ask**. |
| The app shows different numbers than your neighbour's | Click **↺ Reset Demo Data** at the bottom of the app. |
| `npm run dev` says `command not found` / missing packages | Run `npm install` first, from inside the `simple-expense-tracker` folder. |

---

➡️ **Next:** [Part 2: Debug the Total Expenses](02-debug-total-expenses.md)
