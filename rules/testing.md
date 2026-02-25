# Testing

- **Before committing**: Always run the project's test suite to verify nothing is broken
- **New functionality**: Write tests for new features and functions
- **Bug fixes**: Add a regression test that reproduces the bug before fixing it
- **Never** skip, disable, or delete failing tests to make CI pass — fix the underlying issue
- **Never** use `--no-verify` to bypass pre-commit hooks
- If no test suite exists, ask the user whether to add one before proceeding

## When Tests Are Not Required

Not all changes need tests. Use judgment for changes where traditional testing doesn't apply:

- **Configuration files** — e.g., `.yml`, `.toml`, `.json` config, environment settings
- **Infrastructure/deployment manifests** — e.g., Kubernetes manifests, Terraform files, Dockerfiles, CI/CD pipelines
- **Documentation-only changes** — e.g., README updates, inline comment edits
- **Static assets** — e.g., images, fonts, copy/content changes

For these, verify correctness through linting, dry-runs, or manual review instead.
