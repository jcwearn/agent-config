# /pr-create

Push the current branch and create a pull request with a generated description.

## Usage

```
/pr-create
```

## Instructions

1. Determine the base branch:
   - Check for `main` or `master`: `git rev-parse --verify main 2>/dev/null || git rev-parse --verify master`
   - Use whichever exists (prefer `main` if both exist)

2. Gather context from the current branch:
   - Read all commits: `git log <base>..HEAD --oneline`
   - Read the full diff: `git diff <base>...HEAD`

3. Generate a structured PR description:
   - **Title**: Short summary (under 70 characters), imperative mood
   - **Summary**: 1–3 bullet points explaining what changed and why
   - **Test plan**: Bulleted checklist of how to verify the changes

4. Push the branch:
   - `git push -u origin HEAD`

5. Create the PR:
   ```
   gh pr create --title "<title>" --body "<body>"
   ```

6. Return the PR URL to the user

**Important**: Follow the git-workflow rule — never use `gh pr merge`. The user merges after review.
