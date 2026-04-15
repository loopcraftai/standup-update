# Standup Update Skill

`standup-update` is a reusable skill for rewriting rough daily standup notes into a clear, structured update.

It can be used in Codex, shared in Slack, or adapted to similar standup workflows in other tools.

The skill is designed for quick status reporting and always returns exactly three numbered items:

1. what was worked on yesterday
2. what will be worked on today
3. blockers

## Purpose

This skill helps standardize standup updates without over-editing the user's original wording. It is intended for cases where the input is informal, inconsistent, or contains minor grammar and spelling issues, but the meaning should remain unchanged.

## Skill Behavior

- keeps the output entirely lowercase
- makes only the smallest grammar, spelling, and clarity fixes needed
- preserves the user's concise, list-style format
- uses `+` instead of the standalone word `and` when joining work items
- returns `3. none` when the blocker entry clearly indicates there are no blockers
- avoids adding commentary, labels, or extra framing

## Expected Input

Provide the skill name followed by three numbered items:

```text
standup-update
1. refined story-3 and rerun it throw ai
2. catch upp on static storage and devops stories
3. none
```

## Example Output

```text
1. refined story-3 + rerun it through ai
2. catch up on static storage + devops stories
3. none
```

## Usage Notes

- all three standup items should be provided
- if fewer than three items are included, the skill should request the missing item numbers instead of guessing
- the skill favors minimal correction over rewriting into polished prose
