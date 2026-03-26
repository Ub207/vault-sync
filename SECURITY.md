# Security Policy

## Reporting Vulnerabilities

If you discover a security vulnerability, please report it responsibly by emailing **usmanubaidurrehman@gmail.com**.

Do not open a public issue for security vulnerabilities.

## Security Practices

### Secrets Management
- All API keys, tokens, and passwords stored in `.env` files (never committed)
- OAuth2 tokens stored locally, excluded from sync
- Session files (WhatsApp, LinkedIn) excluded from sync
- Banking credentials never leave the local machine

### Access Control
- Human-in-the-loop approval for all outbound actions
- Secondary approval required for transactions > PKR 10,000
- Rate limiting on all external API calls
- Audit trail for every action taken

### Infrastructure
- Cloud VM access via SSH key only (no password auth)
- All vault sync over HTTPS
- No sensitive data in git history
- `.gitignore` enforced for all secret patterns

### Monitoring
- Cloud health monitor with Slack alerts
- Stale claim detection (4-hour expiry)
- Process watchdog with auto-restart
- Weekly CEO briefing includes security status
