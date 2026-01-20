# /monthly Skill

Monthly reflection and planning ritual. Run at the start of each month to score your pillars, reflect deeply, and set intentions for the coming month.

## Usage

```
/monthly [month]
```

**Examples:**
- `/monthly` - Current month reflection
- `/monthly 01` - January reflection
- `/monthly 2026-02` - Specific month

---

## Prerequisites

Before running this skill, check:

1. **Year goals exist** - Look for `01_GOALS/{{YYYY}}.md`
   - IF MISSING: "You don't have year goals set. Would you like to do a quick yearly planning session first?"

2. **LIFE_VISION.md exists** - Check `00_SYSTEM/LIFE_VISION.md`
   - IF MISSING: "You haven't defined your life vision yet. Would you like to run /onboarding?"

3. **GLOBAL_STATE.md is fresh**
   - IF STALE: Update before proceeding

---

## Flow Overview

1. Review the month (what happened)
2. Score each pillar 1-10
3. Answer reflection questions
4. Review project portfolio
5. Set month intentions
6. Create month journal
7. Update GLOBAL_STATE.md

---

## Step 1: Gather Context

Read these files:
- `00_SYSTEM/GLOBAL_STATE.md` - Current state
- `00_SYSTEM/LIFE_VISION.md` - Vision and identity word
- `00_SYSTEM/PILLARS.md` - Pillar definitions
- `01_GOALS/{{YYYY}}.md` - Year goals
- `02_JOURNAL/Weekly/` - All weeks from the past month
- `03_PROJECTS/*/_ STATE.md` - All active project states

Summarize what you learn about the past month.

---

## Step 2: Review the Month

**Share with user:**
- Summary of weeks from the past month
- Projects that were active
- Major events or shifts you noticed

**Ask:**
- "What were the highlights of this month?"
- "What were the lowlights or disappointments?"
- "What surprised you?"

---

## Step 3: Score Each Pillar (1-10)

Go through each pillar and ask for a score:

"Let's score how you did on each pillar this month. 1 = neglected, 10 = thriving."

### Body & Energy
**Monthly lens:** "What does your body need right now?"
- How did you treat your body this month?
- Score (1-10):

### Spirit & Meaning
**Monthly lens:** "What makes you feel most alive right now?"
- Did you feel connected to something bigger?
- Score (1-10):

### Mind & Clarity
**Monthly lens:** "What's cluttering your mind?"
- Was your thinking clear or foggy?
- Score (1-10):

### Love & Relationships
**Monthly lens:** "Who needs more of your presence?"
- How did your key relationships fare?
- Score (1-10):

### Self-Time & Joy
**Monthly lens:** "What would feel like pure play?"
- Did you have enough pleasure and joy?
- Score (1-10):

### Creation & Craft
**Monthly lens:** "What are you building right now?"
- What did you create this month?
- Score (1-10):

### Wealth & Leverage
**Monthly lens:** "What's your relationship with money right now?"
- Did you feel financially secure?
- Score (1-10):

### Impact & Service
**Monthly lens:** "Who are you serving?"
- Who did you help this month?
- Score (1-10):

### Media & Personal Brand
**Monthly lens:** "What does your voice want to say?"
- Did you express yourself publicly?
- Score (1-10):

### Exploration & Adventure
**Monthly lens:** "What would expand your world?"
- Did you explore or try new things?
- Score (1-10):

---

## Step 4: Monthly Reflection Questions

Ask these 8 questions (from PILLARS.md):

1. **Identity Calibration:** "Who are you becoming? Does the person you were this month match the person you want to be?"

2. **Energy Audit:** "Where did your energy go? Where did it come from? What drained you? What filled you up?"

3. **Truth Inventory:** "What have you been avoiding? What do you know but haven't admitted? What conversations haven't happened?"

4. **Relationship Scan:** "Who did you invest in? Who invested in you? Who do you miss? Who's drifting away?"

5. **Creation Review:** "What did you ship? What's still in process? What should be killed? What's your next meaningful output?"

6. **Leverage Check:** "Are you building assets or trading time? What would make next month easier than this month?"

7. **Fear & Edge Detection:** "What scared you this month? What edge did you approach? What comfort zone did you challenge?"

8. **Wonder Scan:** "What gave you awe? What restored your sense of possibility? When did time disappear?"

---

## Step 5: Review Project Portfolio

**For each active project:**
- Is it still relevant to your vision and year goals?
- Should it continue, pause, or archive?
- Any new projects that should start?

**Ask:**
- "Any projects that should be archived or killed?"
- "Any new projects emerging that need a home?"

Update project `_STATE.md` files if needed.

---

## Step 6: Set Month Intentions

Connect back to year goals and vision.

**Ask:**
- "What's the theme or keystone focus for next month?"
- "What would make next month a success?"
- "Which 2-3 pillars need the most attention?"
- "Any specific commitments or deadlines?"

---

## Step 7: Create Month Journal

Create the month journal at `02_JOURNAL/Monthly/{{YYYY}}-{{MM}}.md`:

```markdown
# {{Month}} {{Year}}

## Month Theme
{{their keystone focus}}

## Pillar Scores

| Pillar | Score | Notes |
|--------|-------|-------|
| Body & Energy | {{x}}/10 | {{brief note}} |
| Spirit & Meaning | {{x}}/10 | {{brief note}} |
| Mind & Clarity | {{x}}/10 | {{brief note}} |
| Love & Relationships | {{x}}/10 | {{brief note}} |
| Self-Time & Joy | {{x}}/10 | {{brief note}} |
| Creation & Craft | {{x}}/10 | {{brief note}} |
| Wealth & Leverage | {{x}}/10 | {{brief note}} |
| Impact & Service | {{x}}/10 | {{brief note}} |
| Media & Personal Brand | {{x}}/10 | {{brief note}} |
| Exploration & Adventure | {{x}}/10 | {{brief note}} |

**Average:** {{average}}/10

## Highlights
- {{highlight 1}}
- {{highlight 2}}

## Lowlights
- {{lowlight 1}}
- {{lowlight 2}}

## Reflections

### Identity
{{their answer to identity question}}

### Energy
{{their answer}}

### Truth
{{their answer}}

### Relationships
{{their answer}}

### Creation
{{their answer}}

### Leverage
{{their answer}}

### Fear & Edge
{{their answer}}

### Wonder
{{their answer}}

## Next Month Intentions
- {{intention 1}}
- {{intention 2}}
- {{intention 3}}

## Pillar Focus
1. {{pillar needing attention}}
2. {{pillar needing attention}}

---

#monthly #{{year}}-{{month}}
```

---

## Step 8: Update GLOBAL_STATE.md

Update with:
- New focus mode if changed
- Current energy level
- Any project changes
- `last_updated` timestamp

---

## Tips

- This is a longer ritual (60-90 min) - don't rush it
- Pillar scores are subjective - trust your gut
- The reflection questions are the real value - go deep
- Connect everything back to vision and year goals
- If a pillar is consistently low, it needs attention
