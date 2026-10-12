# How AI Coding Agents Work, and How to Use Them Safely

⬅️ [Back to the workshop README](../README.md)

---

## Assistant vs agent

| | AI coding **assistant** | AI coding **agent** |
| --- | --- | --- |
| What it does | Suggests code or answers questions | Takes **actions** to complete a task |
| Example | Copilot suggesting the next line as you type; Copilot Chat in **Ask** mode | Copilot **Agent** mode, Copilot CLI, Claude Code |
| Who does the work | You apply the suggestion | It reads files, edits code, runs commands, and checks results, with your approval |

## How an agent works (the loop)

An agent repeats a simple loop until the task is done:

1. **Read**: look at the relevant files and your instructions.
2. **Plan**: decide what to do next.
3. **Act**: edit a file or run a command (such as `npm test`). It asks permission first.
4. **Check**: read the result (did the tests pass? was there an error?).
5. **Repeat**, or report back to you.

The AI model itself runs in the cloud. The agent sends it the relevant parts of your code and your prompt, and gets back text, edits, or commands to run on your computer.

## What agents are good at

- Explaining unfamiliar code quickly
- Searching across many files
- Boilerplate and repetitive changes
- Writing tests and running them in a loop until they pass
- Drafting specs, plans, and documentation

## Where agents struggle

- **Being confidently wrong.** They can invent functions or misread code. Always verify.
- **Vague requests.** They fill gaps with guesses (see [Part 3](../workshop/03-vibe-coding-budget-alerts.md)).
- **Treating symptoms.** They may hide a bug instead of fixing it (see [Part 2](../workshop/02-debug-total-expenses.md)).
- **Over-editing.** They change more than needed.
- **Knowing your goals.** They don't know your users, priorities, or constraints unless you tell them.

---

## Using agents safely

1. **Use version control.** Commit before asking an agent to make changes, so you can always undo (`git restore .`).
2. **Read before you approve.** Agents ask before running commands. Understand a command before allowing it, especially anything that deletes files, installs software, or uses `sudo` or admin rights.
3. **Review every change.** Use `git diff` or VS Code's Source Control panel. You're responsible for code you commit, whoever wrote it.
4. **Run the tests yourself.** Don't rely on the agent's summary.
5. **Never share secrets.** Don't paste passwords, API keys, or private data into prompts.
6. **Only work on folders you trust.** Agents read your files. Start them inside the project folder, not your whole home directory.
7. **Install tools only from official sources**, such as the links in the [setup guides](../setup/other-ai-agents.md).

---

**More:** [Prompting tips](prompting-tips.md) · [Additional resources](additional-resources.md)
