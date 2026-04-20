# CLOUDX Proposal Skill — הצעות מחיר

Claude Code skill for generating professional CLOUDX price proposals as polished HTML documents, ready for PDF export.

## Features

- 8-page Hebrew RTL document with consistent CLOUDX branding
- Handles both **new** and **existing** clients with distinct tones and structures
- Adapts to any service type: specification, implementation, consulting, training, support
- Blue gradient cover, gold accents, data cards, numbered-circle lists
- PDF generation via Chrome headless

## Installation

```bash
claude install-skill cloudx-proposal.skill
```

Or clone and symlink:

```bash
git clone https://github.com/cloudx-il/cloudx-proposal-skill.git
ln -s "$(pwd)/cloudx-proposal-skill" ~/.claude/skills/cloudx-proposal
```

## Usage

In any Claude Code conversation:

```
תכין לי הצעת מחיר ל...
```

Or invoke directly:

```
/cloudx-proposal
```

The skill will ask for all required inputs before generating.

## Structure

```
├── SKILL.md                      # Main skill instructions
├── assets/
│   └── proposal-template.html    # Complete CSS + HTML structure
├── references/
│   └── content-guide.md          # Content rules, tone, new/existing differences
└── evals/
    └── evals.json                # Test cases
```

## License

Internal use — CLOUDX IL.
