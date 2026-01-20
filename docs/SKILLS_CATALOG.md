# Skills Catalog

This document describes all available skills in Personal Agent OS. Skills are invoked with `/skill-name` in Claude Code.

---

## Skill Overview

```
┌─────────────────────────────────────────────────────────────────┐
│                      CADENCE SKILLS                             │
├─────────────────────────────────────────────────────────────────┤
│  /onboarding    │ First-time setup, create vault               │
│  /daily         │ Morning planning or evening reflection       │
│  /weekly        │ Weekly transition (close + plan)             │
│  /monthly       │ Monthly reflection + planning                │
└─────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────┐
│                    PROJECT SKILLS                               │
├─────────────────────────────────────────────────────────────────┤
│  /new-project   │ Create new project with full structure       │
│  /weekly-calls  │ Summarize project calls for the week         │
│  /monthly-calls │ Monthly call aggregation                     │
└─────────────────────────────────────────────────────────────────┘

┌─────────────────────────────────────────────────────────────────┐
│                     HEALTH SKILLS                               │
├─────────────────────────────────────────────────────────────────┤
│  /scan          │ Quick pulse check - surface what's off       │
│  /scan deep     │ Comprehensive audit with challenger coaching │
└─────────────────────────────────────────────────────────────────┘
```

---

## Cadence Skills

### /onboarding

**When to use:** First-time setup of your vault.

**Trigger phrases:**
- "let's do it"
- "set up my system"
- "get started"
- "initialize my vault"
- "onboard me"

**What it does:**
1. Welcomes you and explains the system
2. Gathers your 5-year vision and identity word
3. Customizes your 10 pillars
4. Captures your active projects (1-3)
5. Notes your key relationships (3-5 people)
6. Creates your personalized vault at `../my-vault/`
7. Initializes git for version control
8. Explains cadences and next steps

**Output:** Complete vault structure with populated files.

---

### /daily

**When to use:** Every morning and/or evening.

**Usage:**
```
/daily [morning|evening]
```

**Prerequisites:**
- Current week journal must exist (run /weekly if missing)
- GLOBAL_STATE.md should be fresh

**Morning Flow:**
1. Surfaces your Top 3 priorities
2. Asks for your #1 focus today
3. Quick pillar check
4. Energy level capture

**Evening Flow:**
1. Captures what you accomplished
2. Tracks pillar commitments (yes/no)
3. Gratitude prompt
4. Tomorrow preview

**Output:** Updates to your week journal's daily section.

---

### /weekly

**When to use:** Sunday evening or Monday morning.

**Prerequisites:**
- Monthly plan should exist (run /monthly if missing)
- GLOBAL_STATE.md should be fresh

**What it does:**
1. Closes last week (what shipped, blockers, pillar scores)
2. Checks current state freshness
3. Walks through each pillar interactively
4. Reviews projects for the new week
5. Sets Top 3 Personal + Top 3 Professional
6. Creates week journal with tracking grid

**Output:** New week journal at `02_JOURNAL/Weekly/{{YYYY}}-W{{NN}}.md`

---

### /monthly

**When to use:** First of each month.

**Usage:**
```
/monthly [month]
```

**Prerequisites:**
- Year goals should exist
- LIFE_VISION.md should exist

**What it does:**
1. Reviews the past month
2. Scores each pillar 1-10
3. Answers 8 deep reflection questions:
   - Identity Calibration
   - Energy Audit
   - Truth Inventory
   - Relationship Scan
   - Creation Review
   - Leverage Check
   - Fear & Edge Detection
   - Wonder Scan
4. Reviews project portfolio
5. Sets month intentions

**Output:** Month journal at `02_JOURNAL/Monthly/{{YYYY}}-{{MM}}.md`

---

## Project Skills

### /new-project

**When to use:** Starting any new project.

**Usage:**
```
/new-project [name]
```

**What it does:**
1. Gathers project info (type, phase, description, people, pillars)
2. Creates folder structure
3. Populates `_STATE.md` with context
4. Creates `_BACKLOG.md` for tasks
5. Links/creates person notes
6. Updates GLOBAL_STATE.md

**Project types:**
- Personal (hobby, health, learning)
- Client (external work)
- Business (your own product)
- Creative (writing, art, music)

**Output:** Project folder at `03_PROJECTS/{{name}}/`

---

### /weekly-calls

**When to use:** End of week, to summarize project calls.

**Usage:**
```
/weekly-calls <project> [week]
```

**Examples:**
- `/weekly-calls acme` - Latest week
- `/weekly-calls techcorp W03` - Week 3
- `/weekly-calls acme 2026-W02` - Specific week

**What it does:**
1. Locates project and gathers calls from the week
2. Extracts decisions, insights, action items, quotes
3. Identifies theme and momentum
4. Creates summary with relationship tracking
5. Updates person cards with interaction history

**Output:** Summary at `03_PROJECTS/{{project}}/Notes/{{YYYY}}-W{{NN}}-calls.md`

---

### /monthly-calls

**When to use:** End of month, to see call patterns.

**Usage:**
```
/monthly-calls <project> [month]
```

**Examples:**
- `/monthly-calls acme` - Latest month
- `/monthly-calls techcorp 01` - January
- `/monthly-calls acme 2026-03` - Specific month

**What it does:**
1. Aggregates weekly summaries (or raw calls if no summaries)
2. Builds narrative arc for the month
3. Creates relationship map with trajectory
4. Identifies strategic shifts and patterns
5. Primes for next month

**Output:** Summary at `03_PROJECTS/{{project}}/Notes/{{YYYY}}-{{MM}}-calls.md`

---

## Health Skills

### /scan

**When to use:** Anytime you feel scattered, uncertain, or want a quick system check.

**Usage:**
```
/scan
```

**What it does:**
1. Silently loads GLOBAL_STATE, current week, and active project states
2. Checks freshness - flags anything stale
3. Compares attention vs intention - where energy goes vs stated priorities
4. Poses 3 direct challenges based on gaps found
5. Recommends 3 specific actions
6. Appends pulse to `00_SYSTEM/OPS/scans/pulse-log.md`

**Coaching style:** Direct challenger - "You said X but you're not doing it"

**Duration:** 5-10 minutes

**Output:** Entry appended to pulse log

---

### /scan deep

**When to use:** Weekly, or when feeling lost and needing strategic clarity.

**Usage:**
```
/scan deep
```

**What it does:**

**Phase 1: Deep Context Load**
- Reads vision, pillars, goals cascade, current month/week, all project states

**Phase 2: Cascade Alignment**
- Walks through LIFE_VISION → Life Goals → Year Goals → Month Focus → Week Priorities
- Checks if each level serves the one above
- Surfaces any breaks in the chain

**Phase 3: Project Deep Dive**
- Analyzes each project: phase, activity, pillars served, team, unsummarized calls
- Marks projects as Active/Drifting/Zombie

**Phase 4: Entropy Report**
- Stale files needing update
- Orphaned items (projects without goals, people without notes)
- Phantom priorities (stated but no action)
- Shadow work (active but not stated)

**Phase 5: Pattern Recognition**
- Relationship heat map - who you're engaging with most
- Recurring themes across projects
- Energy patterns from journals

**Phase 6: Reconnection Questions**
- 5-7 direct questions about vision alignment, avoidance, relationships
- Captures your responses

**Phase 7: Opinionated Recommendations**
- What to stop
- What to double down on
- Specific actions with priority order

**Phase 8: Save Report**
- Creates `00_SYSTEM/OPS/scans/{{YYYY-MM-DD}}-deep-scan.md`

**Coaching style:** Direct challenger - doesn't hedge, gives specific opinions

**Duration:** 20-30 minutes

**Output:** Full scan report saved to scans folder

---

## Skill Cascade (Dependencies)

Skills have prerequisites. If a prerequisite is missing, the skill will redirect you.

```
/daily requires:
  └── Current week journal exists
      └── IF MISSING → run /weekly first

/weekly requires:
  └── Current month plan exists
      └── IF MISSING → run /monthly first

/monthly requires:
  └── Current year goals exist
      └── IF MISSING → yearly planning needed

/new-project requires:
  └── GLOBAL_STATE.md exists
      └── IF MISSING → run /onboarding first
```

---

## Information Flow

### Planning Flow (Top-Down)
```
LIFE_VISION.md → Year Goals → Quarter Goals → Month Plan → Weekly Plan → Daily Focus
```

Skills support this cascade by always connecting up to higher-level goals.

### Reflection Flow (Bottom-Up)
```
Daily Logs → Weekly Reflection → Monthly Reflection → Quarterly Review → Yearly Review
```

Each cadence skill captures data that feeds into the next level up.

---

## Example Prompts

**Vision & Planning:**
- "Help me do my weekly planning" → triggers /weekly
- "I want to reflect on this month" → triggers /monthly
- "What should I focus on today?" → triggers /daily

**Projects:**
- "I'm starting a new project called X" → triggers /new-project
- "Summarize all my calls from this week for Project Y" → triggers /weekly-calls

**System Health:**
- "Is my system up to date?" → triggers /scan
- "What's stale in my vault?" → triggers /scan
- "I feel scattered" → triggers /scan
- "I need a strategic review" → triggers /scan deep
- "Am I aligned with my vision?" → triggers /scan deep

---

## Tips for Using Skills

1. **Build the habit** - Run /daily every day, /weekly every Sunday
2. **Trust the cascade** - If a skill redirects you, follow it
3. **Keep it quick** - /daily should be 5-10 min, not 30
4. **Go deep monthly** - That's where real reflection happens
5. **Update as you go** - Skills will prompt you to keep things fresh
6. **Run /scan often** - Quick pulse checks prevent entropy buildup
7. **Don't defend** - When /scan challenges you, sit with the discomfort
