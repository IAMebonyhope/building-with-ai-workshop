# Part 4: Structured Engineering: Budget Alerts

⬅️ [Part 3](03-vibe-coding-budget-alerts.md) · [Back to the workshop README](../README.md)

⏱️ **About 25 minutes** · 💬 **About 6–8 Copilot requests**

---

## What you'll learn

How to build a feature with **structured AI-assisted engineering**: the same way professional teams work, with the AI as a collaborator at every stage.

**Specification → Plan → Implement (in small steps) → Test → Review**

At the end you'll compare this result with your vibe-coding attempt from Part 3.

## What we're building

The **same Budget Alerts feature** as in Part 3, this time with clear requirements:

1. **80% Warning:** show a warning when a category's spending reaches 80% of its allocated budget.
2. **100% Alert:** show an alert when spending reaches or exceeds 100% of the allocated budget.
3. **Visual Budget Status:** progress bars showing spending relative to each category's budget.
4. **Fund Reallocation:** transfer available funds from one category's budget to another.
5. **Automatic Updates:** warnings, alerts, and progress bars update whenever expenses or budgets change.

## Tool we'll use

**GitHub Copilot CLI** in the VS Code terminal. It's well suited to step-by-step work: it can write files, run tests, and fix failures in a loop.

> No Copilot CLI? Use **Copilot Chat in Agent mode** in VS Code. You can also use the **Plan** option in the chat picker for the first two steps.

## Starting point

The **same starting point as Part 3**: your `main` branch (after the Part 2 fix), **not** the vibe-coding branch. You're building the feature again from scratch, so the comparison is fair.

---

## Step 1: Open the project

1. Save anything left over from Part 3, then go back to `main` and create a fresh branch:

   ```bash
   git status
   git switch main
   git switch -c part-4-structured
   ```

   If `git status` shows uncommitted changes from Part 3, commit them on the Part 3 branch first (see [Part 3, Step 4](03-vibe-coding-budget-alerts.md#step-4-run-and-test)).

2. Check that the Budget Alerts code from Part 3 is **gone** (you're back to the starting point): refresh the app. There should be no alerts or progress bars.
3. Make sure the app is running (`npm run dev`), and click **↺ Reset Demo Data**.
4. In another VS Code terminal, start Copilot CLI:

   ```bash
   copilot
   ```

## Step 2: Give the AI agent instructions

Work through these prompts **in order**. After each one, **read and review** the response before moving on. That review is what makes this approach work.

### 2a. Specification (no code yet)

```text
Read the codebase. Then help me write a specification for a Budget Alerts feature with these 5 requirements:
1. 80% Warning: show a warning when a category's spending reaches 80% of its allocated budget.
2. 100% Alert: show an alert when spending reaches or exceeds 100% of the allocated budget.
3. Visual Budget Status: progress bars showing spending relative to each category's budget.
4. Fund Reallocation: transfer available funds from one category's budget to another.
5. Automatic Updates: recalculate warnings, alerts and progress bars whenever expenses or budgets change.
List acceptance criteria and edge cases. Save the specification to docs/budget-alerts-spec.md. Don't write code yet.
```

**Review it:** open `docs/budget-alerts-spec.md`. Does it cover these edge cases? If not, ask Copilot to add them:

- A budget of **₦0** (avoid dividing by zero)
- Spending at **exactly 80%** and **exactly 100%**
- Transferring **more than the available amount**
- Transferring **to the same category**
- **Negative or non-numeric** transfer amounts
- Whether to allow transfers **from an over-budget category**
- **Accessibility**: don't rely on colour alone, and make progress bars and alerts readable by screen readers

### 2b. Plan

```text
Based on the spec, create a step-by-step implementation plan. Identify which files change, which new pure functions are needed, and which tests to add. Keep the existing architecture.
```

**Review it:** Does the plan put the calculations in `src/utils/expenseCalculations.js`, next to the existing helpers? Does each step include tests? Is any step too big?

### 2c. Implement, one step at a time

```text
Implement step 1 only: pure functions for budget percentage and status in expenseCalculations.js, with unit tests. Run npm test.
```

When step 1 passes, continue **one step at a time**, reviewing each one:

```text
Step 1 looks good. Now implement the next step only: show the 80% warning and 100% alert in the UI, with component tests. Run npm test.
```

```text
Next step only: add accessible progress bars for each category, with tests. Run npm test.
```

```text
Next step only: add the fund reallocation form, handling the edge cases from the spec, with tests. Run npm test.
```

> 💡 Running short on time or Copilot requests? It's fine to combine the last two steps into one prompt, or to stop after the alerts and progress bars.

### 2d. Review

```text
Review the changes against the spec. Check accessibility, edge cases, and that npm test and npm run build pass. List anything missing.
```

## Step 3: Review the AI-generated changes

Look at the overall change:

```bash
git diff --stat main
```

Check:

- Does every acceptance criterion in `docs/budget-alerts-spec.md` have matching code **and** a test?
- Are the calculations in **pure functions** in `src/utils/expenseCalculations.js`, separate from the UI?
- Are the 80% and 100% thresholds defined in **one place**?
- Did it avoid changing **unrelated** code?
- Do you understand the code well enough to explain it?

## Step 4: Run and test

1. **Automated checks:**

   ```bash
   npm test
   npm run build
   ```

   ✅ Both should pass, including the new tests.

2. **Manual checks in the browser** (click **↺ Reset Demo Data** first):
   - **Food & Dining** (about 85% spent) shows a **warning**
   - **Shopping** (about 109% spent) shows an **over-budget alert**
   - The other categories show no alert, and every category has a **progress bar**
   - Move ₦5,000 from **Transportation** to **Shopping**: Shopping's alert and progress bar update immediately, and the **Total Allocated Budget stays the same** (₦270,000.00)
   - Try invalid transfers (too much, negative, same category). You should get a clear error message.
   - Add a large expense to a category. Its warning or alert appears **without refreshing**.

3. **Save your work:**

   ```bash
   git add -A
   git commit -m "Budget alerts: structured engineering"
   ```

4. **Compare the two attempts:**

   ```bash
   git diff --stat part-3-vibe-coding part-4-structured
   ```

   Switch between the branches (`git switch part-3-vibe-coding` / `git switch part-4-structured`) and try each one in the browser.

## Step 5: Reflect

- Compare Part 3 and Part 4: which result would you trust in production? Which was faster? Which was easier to review?
- When would you choose **vibe coding**, and when would you choose the **structured approach**?

---

## Expected result

- A written specification in `docs/budget-alerts-spec.md`.
- All five Budget Alerts requirements implemented, with the edge cases handled.
- New unit and component tests. `npm test` and `npm run build` pass.
- Your work committed on the `part-4-structured` branch, ready to compare with `part-3-vibe-coding`.

Don't worry if you didn't finish every step. The **process** (spec → plan → small steps → test → review) is the main takeaway, and you can finish at home.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| The Part 3 alerts are still visible after `git switch main` | You may have had uncommitted changes. Run `git status`. Commit them on the Part 3 branch, or discard them with `git restore .`, then switch again. |
| The agent writes code during the spec or plan step | Remind it: *"Don't write code yet. Only update the spec/plan."* Undo unwanted edits with `git restore .` |
| The agent tries to do every step at once | Say: *"Only do the next step, then stop so I can review."* |
| Tests fail after a step | Ask: *"npm test fails with: [paste the error]. Fix the cause, not the test."* |
| `docs/budget-alerts-spec.md` wasn't created | Ask: *"Save the spec you wrote to docs/budget-alerts-spec.md."* |
| You're out of Copilot requests | Pair with a neighbour, or see [free alternatives](../setup/other-ai-agents.md#if-you-run-out-of-copilot-free-requests). |

---

## 🎉 You did it!

You've used AI agents to understand a codebase, debug a real problem, and build a feature two different ways. Keep going:

- [Prompting tips for AI coding agents](../resources/prompting-tips.md)
- [How AI coding agents work, and how to use them safely](../resources/ai-coding-agents.md)
- [Additional learning resources](../resources/additional-resources.md)

⬅️ [Back to the workshop README](../README.md)
