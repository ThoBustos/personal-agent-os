# /weekly Skill

Interactive weekly planning ritual. Run this at the start of each week (typically Sunday) to close the previous week and set up the new one.

---

## Prerequisites

Before running this skill, check:

1. **Current month plan exists** - Look for `02_JOURNAL/Monthly/{{YYYY}}-{{MM}}.md`
   - IF MISSING: Inform user: "You don't have a monthly plan yet. Would you like to run /monthly first to set your month intentions?"

2. **GLOBAL_STATE.md is fresh** - Check `last_updated` in `00_SYSTEM/GLOBAL_STATE.md`
   - IF STALE (>1 week): Ask "Your state is {N} days old. Is it still accurate?"

3. **At least one active project** - Check GLOBAL_STATE for active_projects
   - IF EMPTY: Ask "You don't have any active projects listed. What are you working on?"

---

## Flow Overview

1. Close last week (per project)
2. Check current state
3. Walk through each pillar (interactive)
4. Review projects for new week
5. Set Top 3s
6. Create week journal + sync

---

## Step 1: Close Last Week Per Project

Read the previous week's journal file and review what happened.

**For each active project, ask:**
- "What shipped last week for [project]?"
- "What didn't ship? Any blockers?"

**Then ask for pillar scores:**
- "Score each pillar 1-10 for last week: Body, Spirit, Mind, Relationships, Joy, Creation, Wealth, Impact, Media, Exploration"

**Finally:**
- "What went well last week?"
- "What didn't go well?"
- "What changes should you make this week?"

Update the previous week's reflection section with answers.

---

## Step 2: Check Current State

Read these files:
- `my-vault/00_SYSTEM/GLOBAL_STATE.md`
- `my-vault/03_PROJECTS/[project]/_STATE.md` for each active project

Surface anything that seems stale or outdated.

**Ask:**
- "Any new inputs since last week? (new priorities, changes, things that came up)"
- "Is your GLOBAL_STATE still accurate?"

---

## Step 3: Walk Through Each Pillar (Interactive)

For each of the 10 pillars, do this interactively:

### Body & Energy
Share recent context from GLOBAL_STATE (e.g., "You mentioned wanting 3 sun exposures, 2 workouts")

**Monthly lens:** "What does your body need right now?"

**Ask:** "What specific commitment will you make this week for Body? (e.g., 3x gym, daily walk, 8h sleep)"

### Spirit & Meaning
Share context.

**Monthly lens:** "What makes you feel most alive right now?"

**Ask:** "What specific commitment for Spirit? (e.g., 7x meds, 2x boredom sessions)"

### Mind & Clarity
Share context.

**Monthly lens:** "What's cluttering your mind?"

**Ask:** "What specific commitment for Mind? (e.g., read 4 days, write 4 days)"

### Love & Relationships
Share context (partner, family, etc.)

**Monthly lens:** "Who needs more of your presence?"

**Ask:** "What specific commitment for Relationships? (e.g., 2x dinner dates, 1x family call)"

### Self-Time & Joy
Share context.

**Monthly lens:** "What would feel like pure play?"

**Ask:** "What specific commitment for Joy? (e.g., 1x puzzle, 1x adventure)"

### Creation & Craft
Share context.

**Monthly lens:** "What are you building right now?"

**Ask:** "What specific commitment for Creation? (covered in projects, but any personal creation?)"

### Wealth & Leverage
Share context.

**Monthly lens:** "What's your relationship with money right now?"

**Ask:** "Any specific Wealth commitment this week? (e.g., review finances, invoice clients)"

### Impact & Service
Share context.

**Monthly lens:** "Who are you serving?"

**Ask:** "Any specific Impact commitment this week?"

### Media & Personal Brand
Share context.

**Monthly lens:** "What does your voice want to say?"

**Ask:** "What's your Media commitment?"

### Exploration & Adventure
Share context.

**Monthly lens:** "What would expand your world?"

**Ask:** "Any Exploration commitment this week? (e.g., try new restaurant, explore new area)"

---

## Step 4: Review Projects for New Week

For each active project:

**Ask:**
- "What are the specific deliverables for [project] this week?"

**Check for:**
- Any new projects or priorities that came in
- Anything that should be deprioritized

**Create project buckets** with the gathered tasks.

---

## Step 5: Set Top 3s

After reviewing everything, ask:

**Top 3 Personal:**
"What are your top 3 personal priorities this week?"
(Usually includes AM protocol, pillar commitments, relationships)

**Top 3 Professional:**
"What are your top 3 professional priorities this week?"
(Most important deliverables across projects)

---

## Step 6: Create Week Journal + Sync

Create the new week's journal file with:
- Top 3 Personal
- Top 3 Professional
- Pillar Commitments tracking grid (with specific commitments filled in)
- Project Buckets with all gathered tasks
- Daily log sections ready

**Sync:**
- Update `TODO.md` "This Week" section to match project buckets
- Update `GLOBAL_STATE.md` if anything changed
- Update project `_STATE.md` files if needed

---

## Output Template

The week journal should follow this structure:

```markdown
# Week XX - 2026

*Sun Mon DD - Sat Mon DD*

---

## Top 3 Personal

1. [ ] [first personal priority]
2. [ ] [second personal priority]
3. [ ] [third personal priority]

## Top 3 Professional

1. [ ] [first professional priority]
2. [ ] [second professional priority]
3. [ ] [third professional priority]

---

## Pillar Commitments (Tracked)

| Pillar | Commitment | Mon | Tue | Wed | Thu | Fri | Sat | Sun |
|--------|------------|-----|-----|-----|-----|-----|-----|-----|
| Body | [specific commitment] | | | | | | | |
| Spirit | [specific commitment] | | | | | | | |
| Mind | [specific commitment] | | | | | | | |
| Relationships | [specific commitment] | | | | | | | |
| Joy | [specific commitment] | | | | | | | |

---

## Project Buckets

### #[project1]
- [ ] Task 1
- [ ] Task 2

### #[project2]
- [ ] Task 1
- [ ] Task 2

---

## Daily Log

[daily sections for each day]

---

## Weekly Reflection

[filled in at end of week]
```

---

## Tips

- Keep commitments **specific and measurable** (not "exercise more" but "3x gym")
- The tracking grid lets you check off each day you hit the commitment
- Top 3s should be achievable but meaningful
- Project buckets should match TODO.md exactly
- Run this every week to build the habit
