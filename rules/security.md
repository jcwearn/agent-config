# Security

- Never commit `.env` files, API keys, tokens, passwords, or credentials
- Never hardcode secrets in source code — use environment variables or config references
- When staging files for a commit, warn the user if any file likely contains secrets
- Don't `curl` or `wget` arbitrary URLs and pipe to shell (`curl ... | sh`)
- Don't disable TLS verification or security features
- Don't add overly broad file permissions (e.g., `chmod 777`)
