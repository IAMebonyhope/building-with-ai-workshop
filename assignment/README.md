# Post-Workshop Assignment: Spending Insights

⬅️ [Back to the workshop README](../README.md) · Next: [The five stages, step by step →](engineering-process.md)

---

## Overview

During the workshop, you learned how to use AI coding agents to explore an existing codebase, implement functionality, and collaborate with AI throughout the development process.

**Now it's your turn!**

In this assignment, you'll enhance the **Simple Expense Tracker** application by building a new feature called **Spending Insights**.

The goal isn't simply to generate working code with AI. It's to practise following a **structured software engineering process**, using AI as your development partner.

You may use **any AI coding agent** you like: GitHub Copilot, Claude Code, Codex, Cursor, or another. See [Other AI coding agents](../setup/other-ai-agents.md) for options, including free ones.

---

## 1. Feature Requirements: Spending Insights

### Objective

Help users understand their spending habits by adding visual insights into their expenses.

Your implementation must support the following:

| ID | Requirement | Expected Behaviour |
| --- | --- | --- |
| FR1 | Spending by Category | Display a chart showing how much money has been spent in each expense category. |
| FR2 | Spending Trends | Display a chart showing how spending changes over time. |
| FR3 | Total Spending | Display the total amount spent across recorded expenses. |
| FR4 | Dynamic Updates | Automatically update spending insights when expenses are added, edited, or deleted. |
| FR5 | Empty State | Display a helpful message when there's no expense data to visualise. |

> ⚠️ **Two things to know about the starter app:**
>
> - **FR3 (Total Spending):** the starter app has the **Total Expenses bug** you investigated in [Workshop Part 2](../workshop/02-debug-total-expenses.md). Your fork will still contain it, so **fix it first** (run `npm run test:bug` to check). Otherwise your total will be wrong.
> - **FR4 (Dynamic Updates):** the starter app lets you **add** and **delete** expenses, but it has no **edit** feature. Your insights must update when expenses are added or deleted. If you also build an edit feature (optional), insights must update after edits too.

### Implementation flexibility

You decide:

- Which **chart types** best communicate the information (bar, pie/donut, line, area, and so on).
- How to **organise** the Spending Insights interface.
- Whether to create a **dedicated insights page** or **integrate it** into the existing dashboard.
- Which **charting library** or visualisation approach to use, for example a library like [Chart.js](https://www.chartjs.org) or [Recharts](https://recharts.org), or plain SVG/CSS.

Your solution should be intuitive, visually clear, and consistent with the existing application. It already formats amounts in Naira (₦), for example.

> ❗ **Important:** Spending Insights must use the application's **actual expense data**, not hardcoded chart values.

> 💡 **Tip for spending trends:** the sample data covers about four weeks. Think about which time period (day, week, or month) makes the trend easy to read, and write your choice down in `SPEC.md`.

---

## 2. Follow the Software Engineering Process

You must complete **five stages, in order**. Each one produces a deliverable.

| Stage | What you do | Deliverable |
| --- | --- | --- |
| 1. Requirements and Specification | Turn the requirements into a clear spec | `SPEC.md` |
| 2. Technical Design and Planning | Plan how to build it | `PLAN.md` |
| 3. Implementation | Build it, incrementally | Source code + Git commits |
| 4. Testing and Validation | Prove it works | Automated tests + `TESTING.md` |
| 5. Documentation and Reflection | Explain it and reflect on it | Updated `README.md` + `REFLECTION.md` |

👉 **Full instructions, suggested prompts, and what each deliverable must include:** [The five stages, step by step](engineering-process.md)

---

## 3. How to Get Started

### Step 1: Fork the repository

A **fork** is your own copy of someone else's repository on GitHub. You can change it freely, and it's where you'll submit your work.

1. Sign in to GitHub and open <https://github.com/IAMebonyhope/simple-expense-tracker>.
2. Click **Fork** (top-right), then **Create fork**.
3. You now have your own copy at `https://github.com/YOUR-USERNAME/simple-expense-tracker`.

### Step 2: Clone your fork

Use a **new folder** so you don't mix this up with your workshop copy. Replace `YOUR-USERNAME` with your GitHub username:

```bash
git clone https://github.com/YOUR-USERNAME/simple-expense-tracker.git spending-insights
cd spending-insights
npm install
npm run dev
```

The last argument (`spending-insights`) is the folder name, so it won't clash with the `simple-expense-tracker` folder from the workshop.

### Step 3: Open the project and explore

```bash
code .
```

Use your AI coding agent to explore the codebase again, just like in [Workshop Part 1](../workshop/01-understand-the-codebase.md). Pay special attention to how expenses are **stored** (`src/App.jsx`, `src/hooks/useLocalStorage.js`) and **calculated** (`src/utils/expenseCalculations.js`).

### Step 4: Complete the stages in order

Follow [the five stages](engineering-process.md). **Commit after each stage**, so your Git history shows your progress:

```bash
git add -A
git commit -m "Add SPEC.md for Spending Insights"
```

### Step 5: Push your work to GitHub

```bash
git push
```

The first time you push, Git may ask you to sign in to GitHub in your browser. Follow the prompts.

### Step 6: Submit

Submit the link to **your fork**, for example `https://github.com/YOUR-USERNAME/simple-expense-tracker`, using the submission method your instructor shares.

---

## 4. Submission Requirements

Your repository must contain:

| Deliverable | Description |
| --- | --- |
| `README.md` | Updated project overview, setup instructions, and screenshots |
| `SPEC.md` | Spending Insights requirements and acceptance criteria |
| `PLAN.md` | Technical design and implementation plan |
| Source code | Working Spending Insights feature |
| Automated tests | Tests covering spending calculations and functionality |
| `TESTING.md` | Test cases, execution results, and limitations |
| `REFLECTION.md` | Reflection on your AI-assisted development experience |
| Git commits | Meaningful commits showing your development progress |

### Before you submit: checklist

- [ ] `SPEC.md`, `PLAN.md`, `TESTING.md`, and `REFLECTION.md` are in the **root** of the repository (next to `package.json`).
- [ ] All five requirements (FR1–FR5) work in the browser.
- [ ] The charts use real expense data and update when you add or delete an expense.
- [ ] `npm test` passes, including your new tests.
- [ ] `npm run test:bug` passes (the Total Expenses bug is fixed).
- [ ] `npm run build` succeeds.
- [ ] `README.md` describes the feature and includes at least one screenshot.
- [ ] Your Git history has several meaningful commits, not one giant commit.
- [ ] Everything is **pushed** to GitHub. Open your fork in a browser to check.
- [ ] Your fork is **public**, so it can be reviewed.

---

## 5. Evaluation Criteria

| Category | Points |
| --- | ---: |
| Requirements and Specification | 15 |
| Technical Design and Planning | 15 |
| Feature Implementation | 35 |
| Testing and Validation | 25 |
| Documentation and Reflection | 10 |
| **Total** | **100** |

Your work will be evaluated on both the **functionality** of your application and the **engineering process** you followed.

A polished interface alone isn't enough. Your solution should be supported by clear requirements, a thoughtful implementation plan, and evidence of testing.

---

## 6. Final Reminder

AI coding agents can help you write specifications, design solutions, write code, and create tests.

However, **you remain responsible for understanding, reviewing, and validating the work.**

The objective isn't to see how quickly AI can complete the assignment for you. It's to show how you can use AI effectively while applying sound software engineering practices.

### **Build with AI. Think like an engineer.** 🚀

---

**Helpful links:** [Prompting tips](../resources/prompting-tips.md) · [Using AI agents safely](../resources/ai-coding-agents.md) · [Workshop Part 4: the structured approach](../workshop/04-structured-engineering-budget-alerts.md)

➡️ **Next:** [The five stages, step by step](engineering-process.md)
