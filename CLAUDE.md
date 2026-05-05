# CLOUDX Proposal Skill

## About
Claude Code skill for generating professional CLOUDX price proposals as HTML documents.

## Key Files
- `cloudx-proposal.skill` — skill definition
- `references/` — reference proposals and templates
- `evals/` — evaluation test cases

## Security Requirements (Mandatory)

### General
- Never hardcode API keys, passwords, or tokens — use environment variables
- Never commit `.env` files, credentials, or private keys
- No `eval()` or `Function()` constructors in any JavaScript context

### Forbidden Patterns
- Hardcoded credentials of any kind
- `eval()` in any JavaScript context
- Catching exceptions without logging (`catch(e) {}`)
