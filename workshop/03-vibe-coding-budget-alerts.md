# Part 3: Vibe Coding: Budget Alerts

⬅️ [Part 2](02-debug-total-expenses.md) · [Back to the workshop README](../README.md) · Next: [Part 4 →](04-structured-engineering-budget-alerts.md)

⏱️ **About 15 minutes** · 💬 **About 1–3 Copilot requests**

---

## What you'll learn

What happens when you build a feature by **"vibe coding"**: giving an AI agent one high-level request and accepting what it produces, without a specification or plan. You'll judge the result honestly: does it work, is it what you wanted, and would you trust it in a real product?

In [Part 4](04-structured-engineering-budget-alerts.md) you'll build the **same feature** again with a structured approach, and compare the two.

## What we're building

A **Budget Alerts** feature for ExpenseFlow. The full requirements are:

1. **80% Warning:** show a warning when a category's spending reaches 80% of its allocated budget.
2. **100% Alert:** show an alert when spending reaches or exceeds 100% of the allocated budget.
3. **Visual Budget Status:** progress bars showing spending relative to each category's budget.
4. **Fund Reallocation:** transfer available funds from one category's budget to another.
5. **Automatic Updates:** warnings, alerts, and progress bars update whenever expenses or budgets change.

In vibe-coding style, **you won't give the agent this list**. You'll just describe the idea in one sentence, the way many people do.

## Tool we'll use

**GitHub Copilot Chat in VS Code**, in **Agent** mode. Agent mode can create and edit files and run commands.

## Starting point

The project **after Part 2**: your `main` branch, with the Total Expenses fix committed. If you didn't finish Part 2, that's fine. Start from your `main` branch as it is.

You'll work on a **separate branch**, so you can return to this exact starting point in Part 4.

---

## Step 1: Open the project

1. In the VS Code terminal, check that you have no uncommitted changes, then create a branch for this attempt:

   ```bash
   git status
   git switch -c part-3-vibe-coding
   ```

   `git status` should say `working tree clean`. If it doesn't, either commit your changes (see [Part 2, Step 4](02-debug-total-expenses.md#step-4-run-and-test)) or discard them with `git restore .`.

2. Make sure the app is running (`npm run dev`) and open <http://localhost:5173>.
3. Open **Copilot Chat** (**Ctrl + Alt + I** / **Ctrl + Cmd + I**) and choose **Agent** in the picker.
4. Optional: start a **new chat session** (the **+** button in the Chat view), so the conversation from Part 1 doesn't influence the result.

## Step 2: Give the AI agent instructions

Send this **single prompt**, exactly as written:

```text
Add budget alerts to this app. Warn me when I'm close to my budget, alert me when I go over, show progress bars, and let me move money between categories.
```

Then let the agent work. When it asks to edit files or run commands, approve the requests (after reading them!). **Resist the urge to add more instructions.** The point is to see what one vague prompt produces.

When the agent says it's done, click **Keep** (or **Accept**) to keep its changes.

## Step 3: Review the AI-generated changes

Look at what the agent actually did:

```bash
git status
git diff --stat
```

`git diff --stat` lists every changed file and how many lines changed. Then open the **Source Control** panel and click through the changes.

Use this checklist:

| Question | Your answer |
| --- | --- |
| Does it show a **warning at 80%**? | |
| Does it show an **alert at or over 100%**? | |
| Are there **progress bars**? | |
| Can you **move money** between categories? | |
| Do the alerts **update immediately** when you add or delete an expense or edit a budget? | |
| Did it **add or update tests**? | |
| Did it change **unrelated code** (for example, rewrite files it didn't need to touch)? | |
| Did it **hard-code** the 80% and 100% thresholds in several places? | |
| Is the code **easy to understand**? Could you explain it to a teammate? | |

## Step 4: Run and test

1. **Try the feature in the browser.** Click **↺ Reset Demo Data** first. With the demo data you'd expect:
   - **Food & Dining** (about 85% spent) → a **warning**
   - **Shopping** (about 109% spent) → an **over-budget alert**
   - The other categories → no alert
2. **Try to break it:**
   - Move ₦5,000 from **Transportation** to **Shopping**. Does the Shopping alert change?
   - Try moving more money than a category has left, or a negative amount.
   - Set a category budget to **₦0**. Does anything crash or show `NaN` or `Infinity`?
3. **Run the tests:**

   ```bash
   npm test
   npm run build
   ```

   Do they still pass? Did the agent add new tests?
4. **Save this attempt** on its branch (even if it's broken; you'll compare it later):

   ```bash
   git add -A
   git commit -m "Budget alerts: vibe coding attempt"
   ```

## Step 5: Reflect

- Did it work? Is it what *you* would have wanted, or what the AI guessed you wanted?
- **Would you merge this into a real product?** Why, or why not?

---

## Expected result

Results vary from person to person, and that's part of the lesson. You'll probably have *something* that looks like budget alerts, but often with gaps: missing tests, unhandled edge cases (₦0 budgets, invalid transfers), unexpected design choices, or changes to unrelated code. Your attempt is saved on the `part-3-vibe-coding` branch.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| The agent only describes changes instead of making them | Make sure the picker is set to **Agent**, not **Ask**. |
| The app shows a blank page or an error after the changes | Check the terminal running `npm run dev` for a red error. You can paste it into Copilot: *"The app shows this error: [paste]"*. That's fine for vibe coding! |
| The agent seems stuck or keeps going in circles | Click **Stop**, keep what you have, and move on to the review. |
| `git switch -c` says the branch already exists | Use a different name, such as `git switch -c part-3-vibe-coding-2`. |
| You're out of Copilot requests | Pair with a neighbour, or see [free alternatives](../setup/other-ai-agents.md#if-you-run-out-of-copilot-free-requests). |

---

➡️ **Next:** [Part 4: Structured Engineering: Budget Alerts](04-structured-engineering-budget-alerts.md)
