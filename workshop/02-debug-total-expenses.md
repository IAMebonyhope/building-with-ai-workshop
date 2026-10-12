# Part 2: Debug the Total Expenses Calculation

⬅️ [Part 1](01-understand-the-codebase.md) · [Back to the workshop README](../README.md) · Next: [Part 3 →](03-vibe-coding-budget-alerts.md)

⏱️ **About 20 minutes** · 💬 **About 3–5 Copilot requests**

---

## What you'll learn

How to use an AI agent to **debug a real problem properly**: investigate and explain the **root cause** first, *then* fix it, and *then* prove the fix with tests. You'll also see the difference between a vague prompt and a well-structured one.

## What we're building

A fix for a bug reported by users: **the dashboard's "Total Expenses" is wrong.** The individual expenses look correct, but the total doesn't add up.

Your job:
1. Confirm the problem.
2. Find out **why** it happens.
3. Fix it in the right place.
4. Prove it's fixed with the tests.

## Tool we'll use

**GitHub Copilot CLI** in the VS Code terminal. It can read the code, run the tests, and make the fix, asking your permission at each step.

> No Copilot CLI? Use **Copilot Chat in Agent mode** in VS Code with the same prompts.

## Starting point

The same project as Part 1, with no changes. Run `git status`. It should say `nothing to commit, working tree clean`.

---

## Step 1: Open the project and see the problem

1. Make sure the app is running (`npm run dev`) and open <http://localhost:5173>.
2. Click **↺ Reset Demo Data** at the bottom of the page, so you have the same data as everyone else.
3. Look at the **Total Expenses** card on the dashboard. Note the value.
4. Now add up the six amounts in the **Expense Breakdown** below it (or in the **Spent** column of Category Budgets). A calculator is fine.

   **Do they match?** 🤔

5. There's also a **regression test** that checks the total. A regression test is an automated check that a specific bug stays fixed. In a second terminal, run:

   ```bash
   npm run test:bug
   ```

   ❌ It **fails**. Read the failure message: it shows the **expected** value and the value it actually **received**.

> 💡 The normal test suite (`npm test`) passes, even though the bug exists. Keep that in mind for the reflection at the end.

## Step 2: Give the AI agent instructions

In a VS Code terminal, inside the project folder, start Copilot CLI:

```bash
copilot
```

**First, here's a prompt NOT to use:**

```text
The total is wrong, fix it.
```

This gives the agent almost no information, and invites it to change code before it understands the problem. That's how you get "fixes" that hide the symptom instead of solving the cause.

**Use this prompt instead:**

```text
The dashboard's Total Expenses doesn't match the sum of the category breakdown. Investigate the root cause before changing any code. Explain what you find, then propose a fix and a test.
```

Copilot will read files and may ask to run commands. **Read each request** and approve it if it makes sense.

Optionally, also ask:

```text
Run npm run test:bug and explain why it fails.
```

When you understand the explanation and agree with the proposed fix, tell it to go ahead:

```text
That makes sense. Please make the fix, then run npm test and npm run test:bug.
```

## Step 3: Review the AI-generated changes

Before you accept that the bug is fixed, **review the change yourself**:

```bash
git diff
```

(Or open the **Source Control** panel in VS Code to see the changes side by side.)

Ask yourself:

- ✅ **Is the fix in the calculation logic itself**, where the bug actually is?
- ❌ Did the agent change the **sample data** to make the numbers look right? That hides the bug instead of fixing it.
- ❌ Did it change the **test's expected value** to match the wrong answer?
- ❌ Did it work around the problem in the **dashboard component**, leaving the broken function in place?
- Can you explain the root cause **in one sentence**, in your own words?

If you're not happy with the change, say so, for example: *"Don't change the sample data. Fix the calculation function instead."* You can also undo everything with `git restore .` and try again.

## Step 4: Run and test

1. Run both test suites (exit Copilot with **Ctrl + C**, or use another terminal):

   ```bash
   npm test
   npm run test:bug
   ```

   ✅ **Both should pass.** `npm run test:bug` should now show `Tests  4 passed (4)`.

2. Check the app in your browser. You may need to refresh. **Total Expenses** should now equal the sum of the category breakdown: **₦200,697.78** with the demo data.

3. Add two or three new expenses, and check that Total Expenses increases by **exactly** the amounts you added.

4. **Save your work** with a commit, so you have a clean checkpoint before Part 3:

   ```bash
   git add -A
   git commit -m "Fix total expenses calculation"
   ```

## Step 5: Reflect

- Why did the normal test suite (`npm test`) pass even though the bug existed? What does that tell you about tests?
- How would the result have been different with the prompt *"The total is wrong, fix it"*?

---

## Expected result

- The dashboard's Total Expenses matches the category breakdown (₦200,697.78 with the demo data).
- `npm test` and `npm run test:bug` both pass.
- The fix is in the calculation logic, not in the sample data, tests, or display code.
- Your fix is committed on the `main` branch.

## Troubleshooting

| Problem | Fix |
| --- | --- |
| The numbers in the app don't match this guide | Click **↺ Reset Demo Data**. |
| The agent changed a lot of files | Undo with `git restore .` and run your prompt again, adding: *"Make the smallest change that fixes the root cause."* |
| `npm run test:bug` still fails after the fix | Read the failure message, and paste it into Copilot: *"This test still fails: [paste]. Why?"* |
| The fix works but you don't understand it | Ask: *"Explain the bug and the fix as if I'm new to JavaScript."* |
| You run out of time | That's OK. Run `git restore .` to discard unfinished changes and continue with Part 3. The next parts don't depend on this fix. |

---

➡️ **Next:** [Part 3: Vibe Coding: Budget Alerts](03-vibe-coding-budget-alerts.md)
