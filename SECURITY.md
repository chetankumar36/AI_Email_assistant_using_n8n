# Security

## Never commit secrets

Do not upload:

- API keys
- OAuth access/refresh tokens
- Telegram bot tokens
- Passwords
- Private webhook URLs
- Authorization headers
- Private email data
- Service-account private keys

## Recommended approach

Keep credentials in n8n's credential manager and reconnect them after importing the workflow.

For Git:

```gitignore
.env
.env.*
*.pem
*.key
credentials.json
service-account.json
secrets/
```

The workflow JSON may be uploaded as a template, but inspect it before publishing.

If a secret is ever committed:

1. Revoke/rotate the secret.
2. Remove it from the repository.
3. Check Git history if necessary.
4. Create a new credential.
