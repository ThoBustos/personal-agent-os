# Personal Agent OS

A **Life Operating System** for humans who want to live intentionally, build at the edge, and compound their growth over time.

---

## Quick Start with Claude Code

### Prerequisites

- **Git** - For version control
- **Claude Code** - Anthropic's CLI (`npm install -g @anthropic-ai/claude-code`)
- **Obsidian** (recommended) - For viewing/editing your vault
- **GitHub account** - For forking the repo
- **Google account** (optional) - For Gmail, Calendar, Drive integration

### Setup

1. **Fork this repo** on GitHub (click "Fork" button top-right)

2. **Clone your fork**
   ```bash
   git clone https://github.com/YOUR_USERNAME/personal-agent-os.git
   cd personal-agent-os
   ```

3. **Run Claude Code**
   ```bash
   claude
   ```

4. **Say the magic words**
   > "Let's do it"

   Claude guides you through ~15 minute onboarding:
   - Asks about your vision, pillars, and projects
   - Creates your vault at `../my-vault/` (sibling folder)
   - Offers to set up Google integration

5. **Open your vault** in Obsidian

### Google Integration (Recommended)

Connect Gmail, Calendar, and Drive to Claude for full functionality:

1. Create your own Google Cloud OAuth app ([10-min guide](docs/mcp/google-workspace.md#quick-setup-checklist))
2. Add the MCP server to Claude Code
3. Authenticate your Google account(s)

**Note:** You create your *own* OAuth app - no access to anyone else's app needed. Your credentials stay on your machine.

See [Google Workspace Setup](docs/mcp/google-workspace.md) for detailed instructions.

---

## Architecture

This repo (`personal-agent-os/`) is the **framework** - templates, skills, docs.

Your vault (`my-vault/`) is created as a **sibling folder** during onboarding:

```
your-projects/
├── personal-agent-os/   # Framework (this repo, public)
│   ├── .claude/skills/  # Skill definitions
│   ├── templates/       # Markdown templates
│   └── docs/            # Documentation
└── my-vault/            # YOUR vault (private, created during onboarding)
    ├── 00_SYSTEM/       # Vision, pillars, state
    ├── 02_JOURNAL/      # Weekly/monthly reflections
    └── 03_PROJECTS/     # Your active projects
```

**Benefits:**
- Pull framework updates without affecting your vault
- Your vault is a separate Git repo (push to private repo)
- Keep personal data separate from public code

---

## What Is This?

Personal Agent OS is a structured framework for:
- **Organizing your life** around meaningful pillars, not chaotic to-do lists
- **Reflecting systematically** at daily, weekly, and monthly cadences
- **Managing projects** with rich context your future self (and AI assistants) can understand
- **Tracking relationships** and ensuring no one important drifts away
- **Building systems** that make success inevitable, not just goals that expire

It's designed to work with:
- **Obsidian** as the knowledge base
- **Git** for version control and history
- **AI assistants** (Claude, etc.) that can read your vault and help you stay aligned

---

## Philosophy

> Structure before automation. Clarity before tools.

Most productivity systems fail because they focus on tools before thinking. Personal Agent OS inverts this:

1. **Define your identity** (who are you becoming?)
2. **Establish your pillars** (what must never be neglected?)
3. **Create reflection loops** (how will you course-correct?)
4. **Add structure** (where does information live?)
5. **Then automate** (only after the foundation is solid)

See [docs/PHILOSOPHY.md](docs/PHILOSOPHY.md) for the full framework.

---

## Skills (What You Can Do)

Personal Agent OS uses **skills** - predefined workflows that help you maintain your system. Run them with `/skill-name` in Claude Code.

### Cadence Skills (Run Regularly)
| Skill | When | What It Does |
|-------|------|--------------|
| `/onboarding` | First time | Create your vault, gather vision |
| `/daily` | Morning/evening | Set intention, log reflection |
| `/weekly` | Sunday | Close week, plan next week |
| `/monthly` | 1st of month | Deep reflection, pillar scores |

### Project Skills
| Skill | When | What It Does |
|-------|------|--------------|
| `/new-project` | Starting something | Create project structure |
| `/weekly-calls <project>` | End of week | Summarize project calls |
| `/monthly-calls <project>` | End of month | Monthly call patterns |

**[See full Skills Catalog](docs/SKILLS_CATALOG.md)**

---

## Structure Overview

```
my-vault/
├── 00_SYSTEM/          # Your operating system - vision, pillars, principles
│   ├── GLOBAL_STATE.md # Current focus, energy, active projects
│   ├── LIFE_VISION.md  # 5-year vision, identity word
│   └── PILLARS.md      # 10 life pillars
├── 01_GOALS/           # Life goals cascading from decades to quarters
├── 02_JOURNAL/         # Weekly docs (with daily entries) and monthly reflections
├── 03_PROJECTS/        # Active projects with _STATE.md each
├── 04_PEOPLE/          # Relationship notes
├── 05_WRITING/         # Reflections, drafts, published work, ideas
└── 06_ARCHIVE/         # Completed projects and historical contexts
```

See [docs/VAULT_STRUCTURE.md](docs/VAULT_STRUCTURE.md) for details.

---

## The 10 Pillars

Personal Agent OS organizes life around 10 pillars:

| Pillar | Question |
|--------|----------|
| **Body & Energy** | Is my body becoming more powerful, resilient, expressive? |
| **Spirit & Meaning** | Do I feel connected to existence, or just executing tasks? |
| **Mind & Clarity** | Is my thinking getting clearer, simpler, more strategic? |
| **Love & Relationships** | Are my relationships deepening, or just continuing? |
| **Self-Time & Joy** | When did I last feel childlike, curious, enchanted? |
| **Creation & Craft** | What am I building that didn't exist before me? |
| **Wealth & Leverage** | Is my life becoming more free, or more fragile? |
| **Impact & Service** | If I disappeared, what would be missing? |
| **Media & Personal Brand** | Is my worldview being expressed, or trapped? |
| **Exploration & Adventure** | When did I last feel small—in a good way? |

---

## Information Flow

### Planning (Top-Down)
```
LIFE_VISION.md → Year Goals → Quarter Goals → Month Plan → Weekly Plan → Daily Focus
```

### Reflection (Bottom-Up)
```
Daily Logs → Weekly Reflection → Monthly Reflection → Quarterly Review → Yearly Review
```

Skills enforce this cascade. If you try to run `/daily` without a weekly plan, it will redirect you to `/weekly` first.

---

## Reflection Cadences

### Daily Compass (5-10 min)
- Morning: Set intention, energy check
- Evening: Capture accomplishments, gratitude

### Weekly Planning (30-45 min)
- Close last week with pillar scores
- Set Top 3 Personal + Professional
- Plan pillar commitments

### Monthly Reflection (60-90 min)
- Score all pillars 1-10
- Answer 8 reflection questions
- Review project portfolio

See [docs/CADENCES.md](docs/CADENCES.md) for the complete breakdown.

---

## Anti-Entropy Rules

The system fights rot with these rules:

1. **No orphan notes** - Every note links to something
2. **No zombie projects** - Untouched >1 month → archive or kill
3. **No stale states** - GLOBAL_STATE.md must always be current
4. **No context gaps** - Capture answers when Claude asks
5. **No invisible decisions** - Log decisions with context

---

## Manual Setup (Alternative)

If you prefer to set up manually without Claude Code:

<details>
<summary>Click to expand manual setup instructions</summary>

### 1. Fork this repo

```bash
git clone https://github.com/yourusername/personal-agent-os.git my-vault
cd my-vault
```

### 2. Copy the example vault

```bash
cp -r example-vault/* .
rm -rf example-vault  # Remove the example folder after copying
```

### 3. Open in Obsidian

Open the folder in Obsidian. You'll see the full structure ready to use.

### 4. Start with the essentials

1. Edit `00_SYSTEM/LIFE_VISION.md` - Who are you becoming?
2. Edit `00_SYSTEM/PILLARS.md` - What are your life pillars?
3. Edit `00_SYSTEM/GLOBAL_STATE.md` - What's your current focus?
4. Create your first weekly doc in `02_JOURNAL/Weekly/`

### 5. Live in it

Use the playbooks in [playbooks/](playbooks/) to guide your daily, weekly, and monthly rituals.

</details>

---

## Core Principles

From the [swyx framework](https://www.swyx.io/):

- **Systems > Goals** - Build processes that make success inevitable
- **Principles > Tactics** - Understand the why, invent the how
- **Writing > Reading** - Processing creates value, consumption doesn't
- **Questions > Answers** - Stay curious longer than comfortable
- **People > Projects** - Projects end, relationships compound

---

## Tags

Tags create relations across all content:

```
# Entity types
#person, #project, #decision, #idea, #memory, #gratitude

# Pillars
#pillar/body, #pillar/spirit, #pillar/mind, #pillar/relationships
#pillar/joy, #pillar/creation, #pillar/wealth, #pillar/impact
#pillar/media, #pillar/exploration

# Status
#active, #someday, #archived
```

See [docs/TAGGING.md](docs/TAGGING.md) for the full system.

---

## For AI Assistants

This structure is designed to give AI assistants rich context:

1. **Start with `00_SYSTEM/GLOBAL_STATE.md`** - Current focus and energy
2. **Check `PILLARS.md`** - Life balance context
3. **Read project `_STATE.md`** - Project-specific context
4. **Reference `_GUIDE.md`** in each folder - Operating instructions

---

## Documentation

| Guide | Description |
|-------|-------------|
| [docs/SKILLS_CATALOG.md](docs/SKILLS_CATALOG.md) | All available skills and when to use them |
| [docs/GETTING_STARTED.md](docs/GETTING_STARTED.md) | Your first week, day by day |
| [docs/CADENCES.md](docs/CADENCES.md) | Daily, weekly, monthly rituals |
| [docs/PHILOSOPHY.md](docs/PHILOSOPHY.md) | Why this structure works |
| [docs/VAULT_STRUCTURE.md](docs/VAULT_STRUCTURE.md) | Folder structure explained |
| [docs/TAGGING.md](docs/TAGGING.md) | Tag system for patterns |
| [docs/FAQ.md](docs/FAQ.md) | Common questions |

---

## Contributing

This is a personal framework, but ideas are welcome. Open an issue to discuss improvements.

## License

MIT - Use it, fork it, make it yours.

---

*Built with intention. Lived with consistency.*
