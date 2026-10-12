# Prompting Tips for AI Coding Agents

⬅️ [Back to the workshop README](../README.md)

A **prompt** is the instruction you give an AI agent. Better prompts get better results, and the good news is that good prompts are just **clear communication**, the same way you'd brief a teammate.

---

## The five habits

### 1. Give context

Tell the agent what the project is, what you're looking at, and what you've already noticed.

| ❌ Vague | ✅ Specific |
| --- | --- |
| `The total is wrong.` | `The dashboard's Total Expenses doesn't match the sum of the category breakdown.` |

In VS Code, use `#file` or `#codebase` to point Copilot at the right code.

### 2. Say what "done" looks like

Describe the expected behaviour, ideally as checkable criteria.

```text
Show a warning when a category's spending reaches 80% of its budget, and an alert at 100% or more.
```

### 3. Ask for understanding before action

For bugs and unfamiliar code, ask the agent to **investigate and explain first**.

```text
Investigate the root cause before changing any code. Explain what you find, then propose a fix.
```

### 4. Work in small steps

Big requests produce big, hard-to-review changes. Ask for one step, review it, then continue.

```text
Implement step 1 only, with unit tests. Run npm test, then stop so I can review.
```

### 5. Ask for verification

Have the agent prove its work with tests and builds.

```text
Run npm test and npm run build, and fix any failures. Fix the cause, not the test.
```

---

## Useful prompt patterns

| Goal | Prompt |
| --- | --- |
| Understand a project | `Explain the architecture of this project. What does each folder do?` |
| Trace a feature | `Trace what happens, step by step, when I [action]. Name the files and functions involved.` |
| Debug | `[Symptom]. Investigate the root cause before changing any code. Explain what you find, then propose a fix and a test.` |
| Plan a feature | `Based on these requirements, create a step-by-step implementation plan. Identify which files change and which tests to add. Don't write code yet.` |
| Keep changes small | `Make the smallest change that fixes the root cause. Don't change unrelated code.` |
| Learn from the result | `Explain this change as if I'm new to JavaScript.` |
| Review | `Review the changes against the spec. Check edge cases and accessibility. List anything missing.` |

---

## When the agent goes off track

- **It changed too much?** Undo with `git restore .` (this discards uncommitted changes) and rerun a more specific prompt.
- **It's going in circles?** Stop it, and give it the exact error message or a clearer next step.
- **It says it's done, but it isn't?** Ask it to run the tests, or run them yourself. Trust the evidence, not the summary.
- **It "fixed" a test by changing the expected value?** Push back: *"Fix the code, not the test."*

---

## Vibe coding vs structured engineering

| | Vibe coding | Structured engineering |
| --- | --- | --- |
| How | One high-level prompt; accept the result | Spec → plan → small steps → test → review |
| Speed | Fast to start | Slower to start, often faster to *finish correctly* |
| Good for | Prototypes, experiments, throwaway scripts, learning | Code you'll ship, maintain, or share with a team |
| Risk | Hidden bugs, missed requirements, hard-to-review changes | More effort up front |

Neither is "wrong". Experienced developers choose based on what's at stake.

---

**More:** [How AI coding agents work, and how to use them safely](ai-coding-agents.md) · [Additional resources](additional-resources.md)
