# /daily Skill

Morning planning or evening reflection ritual. Run daily to stay aligned with your weekly intentions.

## Usage

```
/daily [morning|evening]
```

**Examples:**
- `/daily` - Auto-detect based on time (before 2pm = morning, after = evening)
- `/daily morning` - Morning planning flow
- `/daily evening` - Evening reflection flow

---

## Prerequisites

Before running this skill, check:

1. **Current week journal exists** - Look for `02_JOURNAL/Weekly/{{YYYY}}-W{{NN}}.md`
   - IF MISSING: "You don't have a week journal yet. Would you like to run /weekly first to set up your week?"

2. **GLOBAL_STATE.md is fresh** - Check `last_updated` in `00_SYSTEM/GLOBAL_STATE.md`
   - IF STALE (>3 days): Ask "Your state is {N} days old. Is it still accurate?"

---

## Morning Flow

### Step 1: Read Context

Read these files:
- `00_SYSTEM/GLOBAL_STATE.md` - Current focus and energy
- `02_JOURNAL/Weekly/{{current-week}}.md` - This week's Top 3s and pillar commitments

### Step 2: Surface Today's Focus

Share with the user:
- Their Top 3 Personal priorities for the week
- Their Top 3 Professional priorities for the week
- Any pillar commitments they haven't tracked yet this week

### Step 3: Set Daily Intention

**Ask:**
- "What's your #1 focus for today?"
- "Any new inputs since yesterday that affect your plan?"
- "What would make today a success?"

### Step 4: Quick Pillar Check

**Ask:**
- "Any pillar that needs specific attention today?" (Body, Spirit, Mind, Relationships, Joy)

### Step 5: Energy Check

**Ask:**
- "What's your energy level right now (1-10)?"
- "Any obstacles you anticipate today?"

### Step 6: Capture

Add a morning entry to today's section in the week journal:

```markdown
### {{Day}} - {{Date}}

**Morning**
- Energy: {{level}}/10
- #1 Focus: {{their focus}}
- Pillar attention: {{if any}}
```

---

## Evening Flow

### Step 1: Read Context

Read these files:
- `00_SYSTEM/GLOBAL_STATE.md` - Current focus
- `02_JOURNAL/Weekly/{{current-week}}.md` - Today's morning entry

### Step 2: Capture What Happened

**Ask:**
- "What did you accomplish today?"
- "What didn't get done that you planned?"
- "Any wins worth celebrating?"

### Step 3: Pillar Tracking

Review the week's pillar commitments and ask:
- "Did you hit your pillar commitments today? Let me mark them off."
  - Body: {{their commitment}} - Yes/No?
  - Spirit: {{their commitment}} - Yes/No?
  - Mind: {{their commitment}} - Yes/No?
  - etc.

Update the tracking grid in the week journal.

### Step 4: Gratitude & Energy

**Ask:**
- "What's one thing you're grateful for today?"
- "Energy level now (1-10)?"
- "Anything weighing on your mind?"

### Step 5: Tomorrow Preview

**Ask:**
- "What's the most important thing for tomorrow?"
- "Any inputs for tomorrow you need to capture?"

### Step 6: Capture

Complete today's section in the week journal:

```markdown
### {{Day}} - {{Date}}

**Morning**
- Energy: {{level}}/10
- #1 Focus: {{their focus}}

**Evening**
- Energy: {{level}}/10
- Accomplished: {{what they did}}
- Gratitude: {{their answer}}
- Tomorrow: {{preview}}
```

### Step 7: Update State (If Needed)

If anything significant changed:
- Update `GLOBAL_STATE.md` with new focus or energy
- Note any new information learned

---

## Daily Compass Questions

Use these sparingly to deepen reflection:

- Did I move my body?
- Did I create something?
- Did I tell the truth?
- Did I connect with someone?
- Did I feel awe or gratitude?

---

## Tips

- Morning should be quick (5 min max) - focus on intention
- Evening should capture the day (10 min max) - focus on reflection
- Don't overthink pillar tracking - a quick yes/no is fine
- The goal is consistency, not perfection
- If they miss a day, don't guilt - just pick up where they are
