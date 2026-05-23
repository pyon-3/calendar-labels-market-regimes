# Publishing Notes

This repository should contain only public research artifacts.

## Public-only rule

Commit only:

- Markdown research notes
- methodology and limitation notes
- derived figures
- aggregated result tables
- sanitized script notes

Do not commit:

- `.env`
- API keys
- raw J-Quants responses
- raw vendor files
- full price caches
- credentials
- notebooks with local paths or hidden tokens
- personal email addresses unless intentionally public

## Local pre-publish checklist

Run these checks before pushing:

```bash
git status --short
find . -type f | grep -Ei '(\.env|token|secret|price_cache|jquants_|raw_data|private)'
grep -RInE --exclude=PUBLISHING.md '([J]QUANTS_API_KEY|[Rr]efresh[Tt]oken|[Ii]d[Tt]oken|[Pp]assword|mailaddress|gmail\.com)' .
```

Expected result: no sensitive files in the git index.

## Repository rename

Recommended public repository name:

```text
market-regime-research-notes
```

If renaming the existing GitHub repository, update the remote URL after the GitHub-side rename:

```bash
git remote set-url origin git@github.com:pyon-3/market-regime-research-notes.git
```

## Publishing stance

The repository presents research notes, not trading systems.

Every note should clearly separate:

- hypothesis
- data construction
- proxy limitations
- descriptive results
- interpretation
- non-advice disclaimer
