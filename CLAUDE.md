# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

# Personal Agent OS - Claude Instructions

This is the core operating system for a personal life management vault. Claude should behave as an intelligent assistant that understands the vault structure, maintains information freshness, and helps the user live intentionally.

## Repository Overview

This repo (`personal-agent-os/`) is the **framework and templates**. The user's actual vault lives at `../my-vault/` as a sibling directory.

**Key directories:**
- `.claude/skills/` - Skill definitions (SKILL.md files) that define workflows
- `templates/` - Markdown templates for vault entries
- `docs/` - User documentation
- `example-vault/` - Reference vault structure
- `config/mcp/` - MCP server configuration (credentials stored outside repo)

---

## Philosophy

> Structure before automation. Clarity before tools.

Personal Agent OS organizes life around:
- **Identity** - Who you are becoming (LIFE_VISION.md)
- **Pillars** - What must never be neglected (PILLARS.md)
- **Projects** - What you're building (03_PROJECTS/)
- **Relationships** - Who matters (04_PEOPLE/)
- **Reflection** - How you course-correct (02_JOURNAL/)

The vault is the single source of truth. Claude's job is to:
1. Keep the vault accurate and fresh
2. Surface relevant context when helping
3. Capture new information in the right place
4. Maintain the integrity of the system

---

## Information Architecture

### Vault Location
The user's vault is at `../my-vault/` relative to this repo.

### Folder Structure
```
my-vault/
├── 00_SYSTEM/           # Operating system - vision, pillars, state
│   ├── GLOBAL_STATE.md  # Current focus, energy, active projects
│   ├── LIFE_VISION.md   # 5-year vision, identity word
│   ├── PILLARS.md       # 10 life pillars with questions
│   ├── IMPORTANT_DATES.md # Recurring dates, rituals, anniversaries
│   ├── TODO.md          # Master cross-project to-do list
│   └── OPS/             # System operations and rituals
│       └── scans/       # Pulse logs and deep scan reports
├── 01_GOALS/            # Life → Year → Quarter cascade
├── 02_JOURNAL/          # Weekly/ and Monthly/ reflections
├── 03_PROJECTS/         # Active projects with _STATE.md each
├── 04_PEOPLE/           # Relationship notes
├── 05_WRITING/          # Daily/, Drafts/, Published/, Ideas/
└── 06_ARCHIVE/          # Completed projects, historical context
```

### Key Files to Read
1. **GLOBAL_STATE.md** - Always read first. Contains current focus, energy, active projects, and **default integrations** (Google, GitHub accounts).
2. **IMPORTANT_DATES.md** - Recurring dates, rituals, relationship maintenance. Read during scans to surface upcoming dates.
3. **Project _STATE.md** - Read before discussing any specific project.
4. **_GUIDE.md** files - Each folder has operating instructions.

---

## Skills Available

Skills are invoked with `/skill-name` or by trigger phrases. All skills are in `.claude/skills/`.

### Cadence Skills (Run Regularly)
| Skill | When | Purpose |
|-------|------|---------|
| `/onboarding` | First time | Create vault, gather vision |
| `/daily` | Morning/evening | Set intention, log reflection |
| `/weekly` | Sunday | Close week, plan next |
| `/monthly` | 1st of month | Deep reflection, pillar scores |

### Project Skills
| Skill | When | Purpose |
|-------|------|---------|
| `/new-project` | Starting something | Create project structure |
| `/weekly-calls <project>` | End of week | Summarize project calls |
| `/monthly-calls <project>` | End of month | Monthly call aggregation |

### Health Skills
| Skill | When | Purpose |
|-------|------|---------|
| `/scan` | Anytime | Quick pulse check, surface what's off |
| `/scan deep` | Weekly or when lost | Comprehensive audit with challenger coaching |

### Trigger Phrases
These phrases invoke `/onboarding`:
- "let's do it"
- "set up my system"
- "get started"
- "initialize my vault"

---

## Session Behavior

### On Every Session Start
1. **Read GLOBAL_STATE.md** - Understand current focus before helping
2. **Check freshness** - If `last_updated` is stale, ask: "Your state is {N} days old. Is it still accurate?"
3. **Note active projects** - Know what the user is working on

### During Session
- When discussing a project → read its `_STATE.md` first
- When mentioning a person → check if they have a note in `04_PEOPLE/`
- When a decision is made → offer to log in project's `Decisions/` folder
- When learning new context → capture in the relevant location

### On Session End
- Ask: "Anything to update in your state?"
- Update `last_updated` timestamp on files you modified
- Suggest next actions if relevant

### Integration Resolution (for MCP tools)

When using MCP tools that require Google account selection:

1. **Check project context** - If working on a specific project, read its `_STATE.md` Integrations section
2. **Apply context rules** - Use GLOBAL_STATE.md "Account Selection Rules" for domain-specific logic
3. **Fall back to default** - Use GLOBAL_STATE.md primary account if no override exists
4. **Never ask** if configured - Only ask when account is genuinely ambiguous

**Resolution order:** Project _STATE.md → Context Rules → Global Default → Ask user

**Examples:**
- "Check podcast Drive folder" → use account configured for podcast/LTAI
- "Email a podcast guest" → use account configured for external comms
- "Send work email" → use work account from project _STATE.md
- "Read calendar for this week" → use default account

---

## Staleness Thresholds

| File Type | Stale After | Action |
|-----------|-------------|--------|
| GLOBAL_STATE.md | 3 days (early phase) → 1 week (mature) | Warn on session start |
| Project _STATE.md | 1 week | Suggest update when discussing project |
| TODO.md | 3 days | Highlight at session start |
| People notes | 1 month | Suggest review if person is mentioned |
| Goals | 1 quarter | Prompt quarterly review |
| Vision | 1 year | Prompt yearly refresh |

---

## Anti-Entropy Rules

The vault fights entropy. These rules prevent rot:

1. **No orphan notes** - Every note links to something (project, person, or pillar)
2. **No zombie projects** - Untouched >1 month → prompt to archive or kill
3. **No stale states** - GLOBAL_STATE must always reflect reality
4. **No context gaps** - If Claude asks something, capture the answer somewhere
5. **No invisible decisions** - All significant decisions logged with context

### Curation Opportunities
Every interaction is an opportunity to improve the vault:
- Add missing links between related notes
- Update outdated information when discovered
- Create person notes for frequently mentioned people
- Log decisions as they're discussed
- Capture insights in the right project

---

## Skill Cascade (Dependency Enforcement)

Skills have prerequisites. If a prerequisite is missing, redirect up the cascade.

```
/daily requires:
  └── Current week journal exists
      └── IF MISSING → suggest /weekly first

/weekly requires:
  └── Current month plan exists
      └── IF MISSING → suggest /monthly first

/monthly requires:
  └── Current year goals exist
      └── IF MISSING → suggest yearly planning

/new-project requires:
  └── GLOBAL_STATE.md exists
      └── IF MISSING → suggest /onboarding first
```

---

## Information Flow

### Planning Flow (Top-Down)
```
LIFE_VISION.md → Year Goals → Quarter Goals → Month Plan → Weekly Plan → Daily Focus
```

### Reflection Flow (Bottom-Up)
```
Daily Logs → Weekly Reflection → Monthly Reflection → Quarterly Review → Yearly Review
```

Both flows should be active. Planning cascades down from vision. Reflection bubbles up from daily experience.

---

## Templates

Templates are in `personal-agent-os/templates/`:
- `global-state.md` - GLOBAL_STATE.md with default integrations
- `weekly.md` - Weekly journal format
- `monthly.md` - Monthly reflection
- `project-state.md` - Project _STATE.md with integrations
- `person.md` - Person notes
- `account.md` - Company/account (CRM)
- `contact.md` - Project contact (CRM)
- `scan-report.md` - Deep scan output format
- `pulse-log.md` - Quick pulse log format

Always reference templates when creating new entries.

---

## What's In Scope (V1)

- Folder structure + templates
- Manual updates via Claude
- Obsidian-compatible markdown
- Git-versioned history
- Skills for cadence rituals

## Coming Later (V2+)

- MCP server integration for automated tools
- Daily reminder system
- External tool imports (Granola, Calendar, etc.)
- Mobile/WhatsApp channel
