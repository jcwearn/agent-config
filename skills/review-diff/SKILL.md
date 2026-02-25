# /review-diff

Review current uncommitted changes and provide feedback.

## Usage

```
/review-diff           # Review all staged + unstaged changes
/review-diff --staged  # Review only staged changes
```

## Instructions

1. Run the appropriate diff command based on the argument:
   - Default (no args): `git diff` and `git diff --cached` to capture both unstaged and staged changes
   - `--staged`: `git diff --cached` only
2. If the diff is empty, inform the user there are no changes to review
3. Analyze the diff and flag potential issues:
   - **Bugs**: logic errors, off-by-one mistakes, null/undefined risks, race conditions
   - **Style**: inconsistencies with the surrounding code's conventions
   - **Security**: hardcoded secrets, injection risks, unsafe inputs
   - **Other**: missing error handling, incomplete implementations, leftover debug code
4. Group feedback by file
5. Keep feedback actionable and concise — focus on real problems, not nitpicks
