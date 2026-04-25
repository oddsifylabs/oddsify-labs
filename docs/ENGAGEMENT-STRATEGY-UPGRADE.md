# Engagement Strategy Upgrade — Implementation Summary

**Date:** April 25, 2026
**Owner:** Markus Hermes
**Status:** ✅ Implemented

---

## What Changed

### 1. Visual-First Content (Canva)
- **Decision:** Use Canva-style graphics for all educational/engagement posts
- **Templates Created:** 6 template types (CLV comparisons, bankroll charts, EV breakdowns, agent updates, live games, polls)
- **Storage:** `~/oddsifylabs/visuals/` with organized subdirectories
- **Guide:** `~/oddsifylabs/visuals/CANVA-TEMPLATES.md` (full specs + brand guidelines)

### 2. Behind-the-Scenes Content (Public)
- **Decision:** Make agent team and scanner development public
- **Agents Featured:** Miah (coder), Ruth (web), Octavia (writer/admin), Mitch (sales), Markus (social)
- **Content Types:**
  - Agent team updates (feature deployments)
  - Scanner discoveries (3am findings with data)
  - Development logs (progress tracking)
- **Frequency:** 1-2x/week minimum

### 3. Event-Driven Auto-Posts
- **Decision:** Manual-trigger cron job for marquee games
- **Job ID:** `2c312ea8d716` (paused by default, run manually)
- **Post Types:** Pre-game prep, live game CLV angles, post-game analysis
- **How to Trigger:** `cronjob action='run' job_id='2c312ea8d716'`

---

## Updated Cron Jobs

| Job ID | Name | Schedule | Change |
|--------|------|----------|--------|
| `0948d020db1d` | Afternoon Engagement | Daily 2pm PT | ✅ Updated — now rotates polls/BTS/visuals |
| `2c312ea8d716` | Event-Driven Game Posts | Daily 7pm PT | ✅ Created — PAUSED, manual trigger only |

**All other jobs unchanged** (verified picks, results, reports still running)

---

## Content Rotation (Afternoon Engagement - 2pm PT)

| Day | Content Type | Examples |
|-----|--------------|----------|
| **Mon/Wed/Fri** | Conversation Starters | Polls, questions, "show me your setup" |
| **Tue/Thu** | Behind-the-Scenes | Agent updates, scanner discoveries, dev logs |
| **Sat/Sun** | Visual Content | CLV comparisons, bankroll charts, EV breakdowns |

---

## First Week Visual Content Plan

**Week 1 (April 25 - May 1):**

| Day | Visual Type | Topic | Status |
|-----|-------------|-------|--------|
| Mon (4/27) | Poll | "How many books funded?" | 📋 Pending |
| Tue (4/28) | Agent BTS | Miah scanner update | 📋 Pending |
| Wed (4/29) | CLV Comparison | Pick #[X] result | 📋 Pending |
| Thu (4/30) | EV Breakdown | Tonight's best edge | 📋 Pending |
| Fri (5/1) | Bankroll Chart | Turtle Doctrine example | 📋 Pending |

**Priority:** Start with 3 high-priority templates (polls, CLV comparisons, agent updates)

---

## Skills Updated

1. **oddsify-social-media** — Added visual content guidelines, new templates (conversation starters, BTS, event-driven)
2. **oddsify-follower-growth** — Updated content pillars (now 7 pillars including BTS, conversation, event-driven)

---

## How to Use

### Create Your First Visual (10-15 min)
1. Go to Canva.com (free tier works)
2. Create design → Custom dimensions → 1200x675px
3. Use brand colors: Black background, Green #22c55e, White text
4. Follow template specs in `CANVA-TEMPLATES.md`
5. Export as PNG → Save to `~/oddsifylabs/visuals/[category]/`

### Trigger Event-Driven Post (During Games)
```bash
# Run this command during playoffs/marquee games
cronjob action='run' job_id='2c312ea8d716'
```

### Check Tomorrow's Engagement Post
```bash
# See what content type is scheduled
cronjob action='list' | grep "Afternoon Engagement"
```

---

## Metrics to Watch

**Weekly Review (Mondays 9am PT — automated report):**
- Follower growth rate (target: +10-20/week early on)
- Engagement rate on polls vs. BTS vs. visuals
- Reply count on conversation starters (target: 5+ replies/post)
- Accounts engaging back (build relationship list)

**Success Indicators:**
- Polls getting 10+ votes
- BTS posts getting questions about the tech
- Conversation starters sparking actual discussions (not just likes)
- Event-driven posts getting retweets during live games

---

## Next Steps

**This Week:**
1. ✅ Create first poll visual (Monday 4/27)
2. ✅ Post first agent BTS update (Tuesday 4/28)
3. ✅ Test event-driven job during next marquee game

**Week 2:**
- Review engagement metrics
- Adjust content rotation based on performance
- Batch-create 5-7 visuals for efficiency

**Month 1:**
- Build library of 20+ reusable templates
- Identify top-performing content types
- Refine brand voice based on community response

---

## Files Created/Updated

```
~/oddsifylabs/
├── visuals/
│   ├── CANVA-TEMPLATES.md (new — full template specs)
│   ├── clv-comparisons/ (new — empty)
│   ├── bankroll-charts/ (new — empty)
│   ├── ev-breakdowns/ (new — empty)
│   ├── agent-updates/ (new — empty)
│   ├── event-driven/ (new — empty)
│   └── polls/ (new — empty)
└── docs/
    └── ENGAGEMENT-STRATEGY-UPGRADE.md (this file)

~/.hermes/skills/
├── social-media/oddsify-social-media/SKILL.md (updated)
└── social-media/oddsify-follower-growth/SKILL.md (updated)
```

---

## Questions?

All implementation details are in the updated skills and CANVA-TEMPLATES.md guide.

**Quick reference:**
- Visual specs → `~/oddsifylabs/visuals/CANVA-TEMPLATES.md`
- Content strategy → `oddsify-social-media` skill (Content Strategy Update section)
- Growth targets → `oddsify-follower-growth` skill (90-day targets)

Ready to execute. Let me know if you want to adjust anything before Monday's first poll post. 🐢
