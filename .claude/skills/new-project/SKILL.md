# /new-project Skill

Create a new project with full structure and state.

## Usage

```
/new-project [name]
```

**Examples:**
- `/new-project` - Interactive flow to create a project
- `/new-project health-app` - Create project with specified name

---

## Prerequisites

Before running this skill, check:

1. **GLOBAL_STATE.md exists** - Check `00_SYSTEM/GLOBAL_STATE.md`
   - IF MISSING: "Your vault isn't set up yet. Would you like to run /onboarding first?"

2. **03_PROJECTS/ folder exists**
   - IF MISSING: Create it

---

## Flow

### Step 1: Gather Project Information

**Ask (if not provided):**
- "What's the project name?" (will be used for folder name)

**Then ask:**
- "What type of project is this?"
  - Personal (hobby, health, learning)
  - Client (external client work)
  - Business (your own business/product)
  - Creative (writing, art, music)
  - Other

- "What phase is it in?"
  - Starting (idea/planning)
  - Building (active development)
  - Scaling (growth/expansion)
  - Maintaining (steady state)
  - Wrapping up (finishing)

- "Brief description - what is this project about?"

- "Who's involved? (names of key people, if any)"

- "Which pillar(s) does this project serve?" (can be multiple)
  - Body & Energy
  - Spirit & Meaning
  - Mind & Clarity
  - Love & Relationships
  - Self-Time & Joy
  - Creation & Craft
  - Wealth & Leverage
  - Impact & Service
  - Media & Personal Brand
  - Exploration & Adventure

- "What's the current focus or main blocker?"

- "What does success look like for this project?"

### Step 2: Confirm Before Creating

Summarize and confirm:

"Here's what I'm going to create:

**Project:** {{name}}
**Type:** {{type}}
**Phase:** {{phase}}
**Description:** {{description}}
**People:** {{people or 'Solo'}}
**Pillars:** {{pillars}}
**Current Focus:** {{focus}}
**Success Definition:** {{success}}

I'll create this at `03_PROJECTS/{{name}}/`

Ready to create?"

### Step 3: Create Project Structure

Create the folder structure:

```
03_PROJECTS/{{project-name}}/
├── _STATE.md           # Project state (populated)
├── _BACKLOG.md         # Task backlog
├── Calls/              # Call notes
├── Decisions/          # Decision logs
└── Notes/              # General notes
```

**For Client/Business projects, also create:**
```
├── People/             # Project-specific contacts
├── Accounts/           # Company accounts (if B2B)
└── Legal/              # Contracts, agreements
```

### Step 4: Populate _STATE.md

Use the `templates/project-state.md` template and populate:

```markdown
# {{Project Name}}

## Overview
{{description}}

## Phase
{{phase}} - {{brief explanation of what this means}}

## Success Definition
{{what success looks like}}

## Current Focus
{{main focus or blocker}}

## Team
{{list of people involved, or "Solo project"}}
- [[People/{{Name}}]] - {{role}}

## Pillars Served
{{which pillars this connects to}}

## Timeline
- Started: {{today's date}}
- Target completion: {{if known, or "Ongoing"}}

## Key Links
- Related projects: {{if any}}
- Key documents: {{if any}}

## Notes
{{any additional context}}

---

Last updated: {{today's date}}

#project #{{type}} #{{phase}}
```

### Step 5: Populate _BACKLOG.md

Create empty backlog:

```markdown
# {{Project Name}} - Backlog

## Next Up
_Tasks ready to work on_

## Soon
_Tasks for this week/sprint_

## Later
_Tasks for future_

## Ideas
_Unprocessed ideas and possibilities_

---

#project #backlog
```

### Step 6: Create/Link Person Notes

For each person mentioned:

1. Check if they already exist in `04_PEOPLE/`
2. If not, offer to create: "{{Name}} doesn't have a person note yet. Create one?"
3. Add a link from the new person note to this project

### Step 7: Update GLOBAL_STATE.md

Add the new project to the active projects list in GLOBAL_STATE.md:

```markdown
## Active Projects
- [[03_PROJECTS/{{new-project}}/_STATE|{{Project Name}}]] - {{phase}}
```

### Step 8: Confirm & Next Steps

"Your project is set up at `03_PROJECTS/{{name}}/`

**Files created:**
- `_STATE.md` - Project state and context
- `_BACKLOG.md` - Task backlog
- `Calls/` - For call notes
- `Decisions/` - For decision logs
- `Notes/` - For general notes

**Next steps:**
1. Add initial tasks to `_BACKLOG.md`
2. Log any existing decisions in `Decisions/`
3. When you have calls, create notes in `Calls/` with format `YYYY-MM-DD-topic.md`

The project is now linked from your GLOBAL_STATE."

---

## Folder Name Convention

Convert project name to folder-friendly format:
- Lowercase
- Replace spaces with hyphens
- Remove special characters
- Keep it short but descriptive

Examples:
- "Health App" → `health-app`
- "Q1 Planning" → `q1-planning`
- "Side Hustle #2" → `side-hustle-2`

---

## Project Types & Default Folders

| Type | Extra Folders | Notes |
|------|---------------|-------|
| Personal | Standard only | Simple structure |
| Client | People/, Accounts/, Legal/ | CRM-style for client management |
| Business | People/, Accounts/, Legal/ | Full business project |
| Creative | Standard only | May add Drafts/, Published/ |

---

## Tips

- Keep project names short but meaningful
- Link to relevant people immediately
- The phase should be updated as project progresses
- Use `_STATE.md` as the source of truth for project context
- Archive projects when done, don't delete
