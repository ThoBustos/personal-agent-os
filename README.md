# Personal Agent OS

A **Life Operating System** for humans who want to live intentionally, build at the edge, and compound their growth over time.

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

## Philosophy

> Structure before automation. Clarity before tools.

Most productivity systems fail because they focus on tools before thinking. Personal Agent OS inverts this:

1. **Define your identity** (who are you becoming?)
2. **Establish your pillars** (what must never be neglected?)
3. **Create reflection loops** (how will you course-correct?)
4. **Add structure** (where does information live?)
5. **Then automate** (only after the foundation is solid)

See [docs/PHILOSOPHY.md](docs/PHILOSOPHY.md) for the full framework.

## Core Principles

From the [swyx framework](https://www.swyx.io/):

- **Systems > Goals** - Build processes that make success inevitable
- **Principles > Tactics** - Understand the why, invent the how
- **Writing > Reading** - Processing creates value, consumption doesn't
- **Questions > Answers** - Stay curious longer than comfortable
- **People > Projects** - Projects end, relationships compound

## Quick Start

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

## Structure Overview

```
00_SYSTEM/          # Your operating system - vision, pillars, principles
01_GOALS/           # Life goals cascading from decades to quarters
02_JOURNAL/         # Weekly docs (with daily entries) and monthly reflections
03_PROJECTS/        # Active projects with state, backlog, calls, decisions
04_PEOPLE/          # Relationship notes
05_WRITING/         # Reflections, drafts, published work, ideas
06_ARCHIVE/         # Completed projects and historical contexts
```

See [docs/VAULT_STRUCTURE.md](docs/VAULT_STRUCTURE.md) for details.

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

## Reflection Cadences

### Daily Compass
- Did I move my body?
- Did I create something?
- Did I tell the truth?
- Did I connect with someone?
- Did I feel awe or gratitude?

### Weekly Planning
- Keystone focus (if one thing worked, what matters?)
- Pillar intentions
- One brave act
- One joy anchor
- One system upgrade

### Monthly Reflection
- Identity calibration
- Energy audit
- Truth inventory
- Relationship scan
- Creation review
- Leverage check
- Fear & edge detection
- Wonder scan

See [playbooks/](playbooks/) for detailed guides.

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

## For AI Assistants

This structure is designed to give AI assistants rich context:

1. **Start with `00_SYSTEM/GLOBAL_STATE.md`** - Current focus and energy
2. **Check `PILLARS.md`** - Life balance context
3. **Read project `_STATE.md`** - Project-specific context
4. **Reference `_GUIDE.md`** in each folder - Operating instructions

## Contributing

This is a personal framework, but ideas are welcome. Open an issue to discuss improvements.

## License

MIT - Use it, fork it, make it yours.

---

*Built with intention. Lived with consistency.*
