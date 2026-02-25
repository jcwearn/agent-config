# Git Workflow

**REQUIRED: Before editing any files**, always follow this workflow to create a branch first. Never commit directly to `main`. This applies to every task that modifies files in the repository.

1. Check for uncommitted changes: `git status --porcelain`
   - If there are modified files (lines starting with ` M`, `M`, `D`, `R`, etc.), stash them: `git stash push -m "auto-stash: $(git branch --show-current) - WIP before branch switch"`
   - If there are only new/untracked files or no changes, skip to the next step
2. Pull the latest from `main`: `git checkout main && git pull origin main`
3. Create a branch: `git checkout -b <type>/<description>` where type matches the work (e.g., `feat/`, `fix/`, `chore/`, `refactor/`, `docs/`)
4. Make changes and commit
5. Push and open a PR: `gh pr create --fill`
6. User merges after review (never use `gh pr merge`)

## Restrictions

1. **Never merge PRs** — Do not run `gh pr merge` or any variant. The user will merge after review.
2. **Never force push to main** — `git push --force` and `--force-with-lease` are prohibited on `main`. They are allowed on feature branches only.
3. **Never delete branches** — Do not run `git branch -D`, `git branch -d`, or `git push origin --delete`. The user handles branch cleanup.
4. **No destructive git operations** — Do not run `git reset --hard`, `git checkout -- .`, `git clean -f`, or similar commands that discard uncommitted work.
