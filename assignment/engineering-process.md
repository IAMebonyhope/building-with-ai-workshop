# Assignment: The Five Stages, Step by Step

⬅️ [Back to the assignment brief](README.md) · [Workshop README](../README.md)

Complete these stages **in order**. Each stage builds on the one before, just like [Workshop Part 4](../workshop/04-structured-engineering-budget-alerts.md), but this time you're in charge of the whole process.

> 💡 **Commit after each stage**, so reviewers can see how your work progressed:
>
> ```bash
> git add -A
> git commit -m "Describe what you did in this stage"
> ```

---

## Stage 1: Requirements and Specification

Before writing code, review the existing application and understand how expenses are stored and managed. Then use your AI coding agent to turn the [feature requirements](README.md#1-feature-requirements-spending-insights) into a clear specification.

### Deliverable: `SPEC.md`

Your specification should include:

- Problem statement
- Feature overview
- Functional requirements
- Acceptance criteria
- Assumptions and constraints
- Out-of-scope functionality

### Suggested AI prompt

```text
Review the existing Simple Expense Tracker application. I want to implement a Spending Insights feature that visualizes spending by category and spending trends over time. Help me create a detailed feature specification with functional requirements, acceptance criteria, and edge cases. Do not write any code yet.
```

### Review before moving on

Read the generated specification and adjust it where needed. For example:

- Does every requirement (FR1–FR5) have **testable** acceptance criteria? "The chart updates immediately after an expense is deleted" is testable. "The chart works well" isn't.
- Did you decide the **time period** for spending trends (day, week, or month)?
- Are edge cases covered: no expenses, only one expense, a category with no spending, very large amounts?
- Is it clear what's **out of scope**?

Save the file as `SPEC.md` in the root of the project, then commit.

---

## Stage 2: Technical Design and Planning

With your specification complete, work with your AI coding agent to plan the implementation.

### Deliverable: `PLAN.md`

Your plan should include:

- Proposed technical approach
- Existing files or components that need to change
- New components or functions required
- Data processing and aggregation approach
- Charting or visualisation approach
- Implementation steps
- Testing strategy

### Suggested AI prompt

```text
Based on SPEC.md, analyze the existing codebase and create a technical implementation plan for Spending Insights. Identify the components that need to change, explain how expense data will be aggregated, and propose an approach for visualizing the results. Include a testing strategy. Do not implement the feature yet.
```

### Review before moving on

- Does the plan **reuse** what's already there? The app already has calculation helpers in `src/utils/expenseCalculations.js`.
- Are the data calculations (totals per category, totals per time period) planned as **separate functions** that can be tested on their own, apart from the charts?
- If the plan adds a charting library, why that one? Is it well maintained?
- Are the steps **small** enough to review one at a time?

Save the file as `PLAN.md`, then commit.

---

## Stage 3: Implementation

Use your AI coding agent to implement Spending Insights, based on your specification and plan.

### Requirements

1. Implement all five functional requirements.
2. Follow your documented plan. **Update `PLAN.md`** if your approach changes.
3. Use actual expense data from the application.
4. Preserve existing application functionality.
5. Keep the code readable and maintainable.
6. Commit your changes using Git.

### Suggested AI prompt

```text
Using SPEC.md and PLAN.md, help me implement the Spending Insights feature. Follow the existing project architecture and implement the feature incrementally. Explain significant changes so I can review and understand the code.
```

### Tips

- Work **one plan step at a time**: implement → review → run → commit.
- Review every change with `git diff` (or VS Code's Source Control panel) before committing.
- Keep the app running (`npm run dev`) and check the browser after each step.
- If the agent changes something unrelated, ask it to undo that part, or use `git restore <file>`.

> **You're responsible for reviewing the generated code and making sure it meets your requirements.**

---

## Stage 4: Testing and Validation

A feature isn't complete just because the code runs. You must verify that Spending Insights behaves correctly.

### Testing requirements

- Write **automated tests** for spending calculations and data aggregation.
- Verify that **category totals** are calculated correctly.
- Verify that **spending trends** reflect the correct time periods.
- Test how the app behaves when **no expenses exist**.
- Verify that insights **update** when expenses are added or deleted (and edited, if you built editing).
- Confirm that **existing functionality** still works.

The project already uses [Vitest](https://vitest.dev) and [React Testing Library](https://testing-library.com/docs/react-testing-library/intro/). Look at the existing files in `tests/` for examples, and run the tests with:

```bash
npm test
```

### Suggested AI prompt

```text
Review the Spending Insights implementation against the acceptance criteria in SPEC.md. Help me write automated tests for spending calculations, category breakdowns, spending trends, and empty states. Run the tests, identify any failures, and help me investigate them.
```

### Deliverable: `TESTING.md`

Document:

- Tests performed (automated and manual)
- Commands used to run the tests
- **Actual** test results. Copy the summary from your terminal, for example `Tests  52 passed (52)`.
- Bugs you found and fixed
- Known limitations

> ❗ **Don't report tests as passing unless you've actually run them and seen them pass.** If a test fails and you can't fix it, say so in `TESTING.md`. Honest reporting is part of the grade.

Before writing `TESTING.md`, run all three checks:

```bash
npm test
npm run test:bug
npm run build
```

---

## Stage 5: Documentation and Reflection

### Update `README.md`

Update the project README to explain the new feature. Include:

- A brief description of Spending Insights
- Instructions to run the application
- **Screenshots** of your Spending Insights interface

**How to add a screenshot:**

1. Take a screenshot of your insights:
   - **Windows:** press **Win + Shift + S** and select an area.
   - **macOS:** press **Cmd + Shift + 4** and select an area.
2. Save it in your project, for example as `docs/screenshots/spending-insights.png`.
3. Add it to `README.md`:

   ```markdown
   ![Spending Insights dashboard](docs/screenshots/spending-insights.png)
   ```

4. Commit and push, then check the README on GitHub to make sure the image appears.

### Deliverable: `REFLECTION.md`

Write a short reflection of about **200–300 words** answering:

1. Which AI coding agent did you use, and how did it help you?
2. What part of the development process was easiest with AI?
3. What challenges did you run into?
4. Describe one situation where you reviewed, corrected, or improved an AI-generated suggestion.
5. What did you learn about using AI in software engineering?

> ✍️ Write this one **yourself**. It's about *your* experience.

---

## All done?

Go through the [submission checklist](README.md#before-you-submit-checklist), push your work, and submit the link to your fork. 🎉

⬅️ [Back to the assignment brief](README.md)
