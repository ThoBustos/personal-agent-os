# Secrets Management

How Personal Agent OS handles credentials and sensitive data.

## Core Principle

> **Secrets never live in the repository. Ever.**

All credentials, tokens, and API keys are stored outside the git repo in a standardized location that's easy to back up and impossible to accidentally commit.

## Directory Structure

```
~/.config/personal-agent-os/          # All secrets live here
├── google/
│   └── credentials.json              # OAuth client credentials
├── <other-service>/
│   └── <credentials>
└── README.md                         # Local notes (optional)

~/.google-mcp-accounts/               # Auto-managed by Google MCP
├── account1@gmail.com.json           # Per-account OAuth tokens
└── account2@company.com.json
```

## What Goes Where

| Type | Location | Managed By |
|------|----------|------------|
| OAuth client credentials | `~/.config/personal-agent-os/<service>/` | You |
| Per-account tokens | Service-specific (e.g., `~/.google-mcp-accounts/`) | MCP server |
| API keys | `~/.config/personal-agent-os/<service>/` | You |
| Example configs | `config/mcp/*.example.json` in repo | Git |

## Setting Up the Secrets Directory

```bash
# Create the base directory
mkdir -p ~/.config/personal-agent-os

# Set restrictive permissions
chmod 700 ~/.config/personal-agent-os

# Create service-specific directories as needed
mkdir -p ~/.config/personal-agent-os/google
```

## Security Best Practices

### File Permissions

```bash
# Secrets directory: owner only
chmod 700 ~/.config/personal-agent-os

# Credential files: read-only for owner
chmod 600 ~/.config/personal-agent-os/google/credentials.json
```

### Never Commit Secrets

The repo's `config/mcp/.gitignore` blocks everything except example files:

```gitignore
# Ignore all except examples and README
*
!.gitignore
!README.md
!*.example.json
```

### Backup Strategy

Include `~/.config/personal-agent-os/` in your backup system, but:

1. **Encrypt backups** containing credentials
2. **Don't sync to cloud** without encryption
3. **Consider a password manager** for the most sensitive items

### Revoking Access

If credentials are compromised:

1. **Google**: [Revoke at Google Account](https://myaccount.google.com/permissions)
2. **Regenerate** OAuth client credentials in Google Cloud Console
3. **Re-authenticate** all accounts

## Example Files in Repo

The `config/mcp/` directory contains example files showing the expected format:

```
config/mcp/
├── .gitignore
├── README.md
└── google-credentials.example.json
```

These are templates. Copy and modify for your actual credentials:

```bash
# DON'T do this (keeps file in repo location)
cp config/mcp/google-credentials.example.json config/mcp/google-credentials.json

# DO this (puts real credentials in secrets directory)
# Download from Google Cloud Console, then:
mv ~/Downloads/client_secret_*.json ~/.config/personal-agent-os/google/credentials.json
```

## Adding New Services

When integrating a new MCP service:

1. **Create example file** in `config/mcp/<service>.example.json`
2. **Document setup** in `docs/mcp/<service>.md`
3. **Store real credentials** in `~/.config/personal-agent-os/<service>/`
4. **Update this document** with new paths

## Checklist

Before pushing to git, verify:

- [ ] No `.json` files in `config/mcp/` (except `*.example.json`)
- [ ] No credentials in `~/.claude/settings.json` (only paths to credentials)
- [ ] `~/.config/personal-agent-os/` has `700` permissions
- [ ] Credential files have `600` permissions
