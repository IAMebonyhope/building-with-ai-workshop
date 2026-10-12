# Building with AI: From Idea to Application

Welcome to the **Building with AI** workshop! 👋

In this hands-on session, you'll learn how to use AI coding agents to understand, build, and improve a real application.

You don't need to be an AI expert to participate. If you can follow step-by-step instructions and type commands into a terminal, you're ready.

---

## What You'll Learn

By the end of the workshop, you will be able to:

- **Explore an unfamiliar codebase** by asking an AI agent questions about it.
- **Debug a real problem** by having the AI investigate the root cause before it changes any code.
- **Build a new feature with "vibe coding"**: one high-level prompt, and seeing what the AI produces.
- **Build the same feature with structured AI-assisted engineering**: specification → plan → implementation → testing → review.
- **Compare the two approaches** and decide when each one makes sense.
- **Review, run, and test** AI-generated code instead of trusting it blindly.

## Workshop Details

| | |
| --- | --- |
| **Format** | Hands-on. Bring a laptop and follow along. |
| **Project** | [Simple Expense Tracker](https://github.com/IAMebonyhope/simple-expense-tracker) (an app called *ExpenseFlow*) |
| **Primary tools** | GitHub Copilot in VS Code and GitHub Copilot CLI |

---

## Before the Workshop

> ⏰ **Please finish setup before the workshop.** Installing everything takes about **45–60 minutes**, and there won't be time to do it during the session.

Work through these steps in order. Each link opens a detailed, beginner-friendly guide.

- [ ] 1. Read the [prerequisites](setup/prerequisites.md) and install **Node.js**
- [ ] 2. [Create a free GitHub account](setup/github-setup.md)
- [ ] 3. [Install Visual Studio Code](setup/vscode-setup.md)
- [ ] 4. [Install and set up Git](setup/git-setup.md)
- [ ] 5. [Turn on GitHub Copilot in VS Code](setup/github-copilot-setup.md) (Copilot Free)
- [ ] 6. [Install GitHub Copilot CLI](setup/copilot-cli-setup.md)
- [ ] 7. [Download, run, and verify the starter app](setup/verify-setup.md) ✅

**Optional:**
- [Claude Code](setup/claude-code-setup.md), an alternative terminal agent. Requires a **paid** plan.
- [Other AI coding agents](setup/other-ai-agents.md): a short comparison, including free fallbacks.

> 💡 **Save your free Copilot allowance.** Copilot Free has a limited number of chat and agent requests each month. After you've confirmed Copilot works, avoid using it heavily until the workshop. See [Copilot Free limits](setup/github-copilot-setup.md#copilot-free-what-you-get).

---

## Starter Application

**Repository:** <https://github.com/IAMebonyhope/simple-expense-tracker>

The starter app, **ExpenseFlow**, is a personal expense and budget tracker built with React and Vite. All amounts are in Nigerian Naira (₦). It includes:

- A **dashboard** with total budget, total expenses, remaining balance, and spending by category
- **Category budgets** that you can edit
- An **expense list** where you can add, sort, and delete expenses
- **Sample data** for a typical month, saved in your browser

It's a *starter* project. It's intentionally unfinished, and during the workshop you'll use AI agents to investigate a problem in it and add a new feature.

```bash
git clone https://github.com/IAMebonyhope/simple-expense-tracker.git
cd simple-expense-tracker
npm install
npm run dev
```

Full instructions: [Download, run, and verify the starter app](setup/verify-setup.md).

---

## Workshop Activities

All four parts use the **same starter application**. You download it once, before the workshop, and each part builds on the one before.

| Part | Topic | What You'll Do | Tool |
| ---- | ----- | -------------- | ---- |
| 1 | [Understand the Codebase](workshop/01-understand-the-codebase.md) | Ask an AI agent to explain the project's structure, data flow, and how it saves data. | Copilot Chat (Ask) |
| 2 | [Debug the Total Expenses](workshop/02-debug-total-expenses.md) | Investigate why the dashboard's Total Expenses is wrong, find the root cause, fix it, and prove it with a test. | Copilot CLI |
| 3 | [Vibe Coding: Budget Alerts](workshop/03-vibe-coding-budget-alerts.md) | Build a Budget Alerts feature from one high-level prompt, and evaluate what you get. | Copilot Chat (Agent) |
| 4 | [Structured Engineering: Budget Alerts](workshop/04-structured-engineering-budget-alerts.md) | Build the same feature again, step by step: spec → plan → implement → test → review. | Copilot CLI |

**Rough timing:** welcome and introduction (10 min) · Part 1 (15 min) · Part 2 (20 min) · Part 3 (15 min) · Part 4 (25 min) · wrap-up (5 min).

---

## Post-Workshop Assignment

**Enhance the Simple Expense Tracker with Spending Insights** 📊

After the workshop, put what you learned into practice. You'll add a **Spending Insights** feature (charts of spending by category and over time) to your own copy of the app. You'll follow the full engineering process, with an AI coding agent of your choice as your development partner.

| Stage | Deliverable |
| --- | --- |
| 1. Requirements and Specification | `SPEC.md` |
| 2. Technical Design and Planning | `PLAN.md` |
| 3. Implementation | Working feature, with Git commits |
| 4. Testing and Validation | Automated tests and `TESTING.md` |
| 5. Documentation and Reflection | Updated `README.md` with screenshots, and `REFLECTION.md` |

- 📄 [Assignment brief: requirements, getting started, submission, and grading](assignment/README.md)
- 🛠️ [The five stages, step by step, with suggested prompts](assignment/engineering-process.md)

> **Build with AI. Think like an engineer.**

---

## Additional Resources

- [Prompting tips for AI coding agents](resources/prompting-tips.md)
- [How AI coding agents work, and how to use them safely](resources/ai-coding-agents.md)
- [Additional learning resources](resources/additional-resources.md)

## Need Help?

| Problem | Where to look |
| --- | --- |
| Something didn't install | The **Troubleshooting** section at the bottom of each setup guide |
| The app won't start | [Verify setup → Troubleshooting](setup/verify-setup.md#troubleshooting) |
| Copilot doesn't respond, or says you've hit a limit | [Copilot setup → Troubleshooting](setup/github-copilot-setup.md#troubleshooting) |
| `copilot` command not found | [Copilot CLI setup → Troubleshooting](setup/copilot-cli-setup.md#troubleshooting) |
| The app's numbers look different from the guide | Click **↺ Reset Demo Data** at the bottom of the app |

**Common fixes that solve most problems:**
1. **Close and reopen your terminal** (or VS Code) after installing something.
2. Make sure you're **inside the `simple-expense-tracker` folder** before running `npm` or `copilot` commands.
3. Check your versions: `node --version` should be **v22.12 or newer**.

If you're still stuck during the workshop, raise your hand or pair with a neighbour. 🤝

---

## License

This workshop material is released under the [MIT License](LICENSE).
