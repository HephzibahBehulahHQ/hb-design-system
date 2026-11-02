# Working with the AI Agent

This repo uses a token-disciplined AI agent. Read `SYSTEM_PROMPT.md` for the full rules. This file shows what good vs. bad replies look like so reviewers can spot drift.

## Good reply (follows the contract)
STATUS
Done: Added wcag() helper in src/color/contrast.ts

Tested: 12/12 unit tests pass (added 3 for edge cases)

Next: Wire into Palette Engine swatch cards


## Bad reply (violates the contract — do not merge)

- Restating the whole architecture plan before answering.
- Pasting an entire file when only 4 lines changed.
- "I'm going to now implement the..." preamble with no output.
- Re-summarizing a document the client already pasted as clean text.
- Asking clarifying questions when the spec already answers them.

## When detail *is* allowed

- Client explicitly asks "show me the full file" or "explain in detail."
- Reporting a blocked task where the blocker needs context (keep it to 3–5 lines).

## Reviewing agent PRs

1. Does the PR description match the `STATUS` format? If not, request rewrite.
2. Diff should contain only changed lines/files.
3. No generated docs, no reformatted source, no re-pasted specs.
