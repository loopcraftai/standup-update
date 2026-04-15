---
name: standup-update
description: Use when the user wants a daily standup update rewritten into a clear three-item Slack reply covering yesterday, today, and blockers. Keeps everything lowercase, makes the smallest grammar and clarity fixes needed, preserves concise meaning, and uses + instead of "and" when joining work items.
---

# Standup Updates

Rewrite a standup update into a clean, Slack-ready reply with exactly three numbered items:

1. what was worked on yesterday
2. what will be worked on today
3. blockers

## Output Rules

- Keep the output to exactly `1.`, `2.`, and `3.`
- Keep everything lowercase
- Make the smallest grammar, spelling, and clarity fixes needed without changing meaning
- Preserve the user's concise, list-like style instead of turning it into polished prose
- Use `+` instead of the standalone word `and` when joining work items
- Keep issue keys, acronyms, and names lowercase too if provided in uppercase
- Do not add intro text, labels, commentary, or code fences
- If the blocker item is empty or clearly means no blockers, output `3. none`

## Editing Guidance

- Prefer short fragments over full sentences
- Keep the original ordering of tasks inside each item unless reordering is needed for clarity
- Expand only ambiguous wording that can be safely clarified from the prompt
- Do not invent progress, plans, or blockers that were not provided
- If fewer than three items are provided, ask for the missing item numbers instead of guessing

## Example

Input:

```text
standup-update
1. Refined story-3 and rerun it throw ai
2. catch upp on static storage and devops stories
3. None
```

Output:

```text
1. refined story-3 + rerun it through ai
2. catch up on static storage + devops stories
3. none
```
