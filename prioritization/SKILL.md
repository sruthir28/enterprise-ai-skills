# PM Prioritization Framework

A comprehensive prioritization skill for product managers to evaluate features, initiatives, and tasks using proven frameworks.

## Overview

This skill helps PMs make data-driven decisions by applying the right framework for their specific context. All outputs are provided in clean, tabular format for easy sharing with stakeholders.

## When to Use This Skill

Use this skill when you need to:
- Prioritize a product roadmap
- Decide which features to build next
- Allocate team resources across initiatives
- Make tradeoff decisions between competing priorities
- Communicate priorities to stakeholders

---

## Frameworks Included

### 1. RICE Scoring

**When to use:** When you have quantitative data and want an objective score

**Best for:** Feature prioritization, roadmap planning with multiple stakeholders

**Requires:** Estimates for reach, impact, confidence, and effort

**Formula:** `(Reach × Impact × Confidence) / Effort`

**Components:**
- **Reach:** How many users/customers affected in a time period
- **Impact:** Effect per person (Minimal=0.25, Low=0.5, Medium=1, High=2, Massive=3)
- **Confidence:** Estimate confidence (50%, 80%, 100%)
- **Effort:** Person-months required

**Output Format:**
```
| Feature | Reach | Impact | Confidence | Effort (PM) | RICE Score | Rank |
|---------|-------|--------|------------|-------------|------------|------|
| Feature A | 5000 | 2.0 | 100% | 3.0 | 3333 | 1 |
| Feature B | 3000 | 1.0 | 80% | 2.0 | 1200 | 2 |
```

---

### 2. Impact/Effort Matrix (2×2)

**When to use:** When you need quick visual prioritization or have limited data

**Best for:** Sprint planning, quick decisions, getting team alignment

**Requires:** Relative assessment of impact and effort (High/Low or Small/Medium/Large)

**Quadrants:**
- **Quick Wins** (High Impact, Low Effort) → Do First
- **Big Bets** (High Impact, High Effort) → Plan & Resource
- **Fill-Ins** (Low Impact, Low Effort) → Do When Available
- **Money Pit** (Low Impact, High Effort) → Avoid/Deprioritize

**Output Format:**
```
| Item | Impact | Effort | Quadrant | Priority | Recommendation |
|------|--------|--------|----------|----------|----------------|
| Feature A | High | Low | Quick Win | 1 | Ship this sprint |
| Feature B | High | High | Big Bet | 2 | Plan for Q2 |
| Feature C | Low | Low | Fill-In | 3 | If time permits |
| Feature D | Low | High | Money Pit | 4 | Defer indefinitely |
```

**Visual Matrix:**
```
           LOW EFFORT          HIGH EFFORT
         ┌─────────────────┬─────────────────┐
HIGH     │  QUICK WINS     │   BIG BETS      │
IMPACT   │  • Feature A    │   • Feature B   │
         │  • Feature C    │                 │
         ├─────────────────┼─────────────────┤
LOW      │  FILL-INS       │  MONEY PIT      │
IMPACT   │  • Feature D    │   • Feature E   │
         │                 │                 │
         └─────────────────┴─────────────────┘
```

---

### 3. Value vs. Complexity

**When to use:** When technical complexity is a key factor

**Best for:** Engineering-heavy decisions, technical debt prioritization

**Requires:** Business value assessment + technical complexity rating

**Considers:**
- **Value:** Business value, user value, strategic alignment
- **Complexity:** Technical complexity, dependencies, risk, maintenance burden

**Output Format:**
```
| Item | Business Value | Technical Complexity | Quadrant | Priority |
|------|----------------|---------------------|----------|----------|
| API Upgrade | High | Low | Quick Win | 1 |
| Platform Migration | High | High | Big Bet | 2 |
| UI Polish | Low | Low | Fill-In | 3 |
| Legacy Refactor | Low | High | Money Pit | 4 |
```

---

### 4. Weighted Scoring

**When to use:** When you have custom criteria important to your context

**Best for:** Strategic initiatives, complex B2B decisions, custom business contexts

**Requires:** Defined criteria and weights (must total 100%)

**Common Criteria Examples:**
- Strategic alignment (30%)
- Customer value (25%)
- Revenue potential (20%)
- Effort (15%)
- Risk (10%)

**Output Format:**
```
| Feature | Strategic (30%) | Customer (25%) | Revenue (20%) | Effort (15%) | Risk (10%) | Total Score | Rank |
|---------|-----------------|----------------|---------------|--------------|------------|-------------|------|
| Feature A | 9 (2.7) | 8 (2.0) | 7 (1.4) | 9 (1.35) | 8 (0.8) | 8.25 | 1 |
| Feature B | 7 (2.1) | 9 (2.25) | 6 (1.2) | 7 (1.05) | 7 (0.7) | 7.30 | 2 |
```
*Note: Numbers in parentheses show weighted contribution*

---

## Framework Selection Guide

| Your Situation | Recommended Framework | Why |
|----------------|----------------------|-----|
| Have quantitative data | RICE | Most objective, data-driven |
| Need quick decision | Impact/Effort Matrix | Visual, fast alignment |
| High technical complexity | Value vs. Complexity | Accounts for engineering reality |
| Custom business criteria | Weighted Scoring | Flexible to your context |
| Early startup, high uncertainty | Impact/Effort Matrix | Works with limited data |
| Enterprise, many stakeholders | RICE or Weighted Scoring | Defensible, systematic |
| Managing technical debt | Value vs. Complexity | Balances business + technical |

---

## How to Use This Skill

### Input Format

Provide Claude with:
1. **List of items to prioritize** (features, initiatives, tasks)
2. **Context** (your product, stage, constraints)
3. **Framework preference** (or ask Claude to recommend)
4. **Available data** (estimates, metrics, constraints)

### When You Don't Have Data

**This is common and okay!** Most PMs lack perfect data. Claude can help in two ways:

**Option 1: Claude asks clarifying questions**
If you say "I don't have reach estimates," Claude will ask:
- How many customers have requested this?
- What % of your user base would use this feature?
- Is this a must-have for a specific segment?

**Option 2: Claude provides baseline estimates**
Based on your product context, Claude can suggest reasonable ranges:
- "For B2B SaaS, SSO typically reaches 60-80% of enterprise customers"
- "Mobile adoption for desk-based products: 20-30%, field-based: 70-90%"
- "Search improvements usually have 'High' impact if search is used daily"

Claude will:
- ✅ Explain reasoning behind estimates
- ✅ Use industry benchmarks and patterns
- ✅ Flag high-uncertainty items for validation
- ✅ Give you ranges (e.g., "1000-2000 users") not false precision
- ✅ Mark estimates clearly so you know what to validate

**Just tell Claude:** "I don't have data for X, can you help estimate?"

### Example Prompts

**For RICE:**
```
Using the prioritization skill, score these 5 features with RICE:

1. User dashboard redesign
2. Mobile app notifications  
3. API rate limiting
4. Advanced search filters
5. Export to CSV

Context: B2B SaaS, 10K users, 3-person eng team
```

**For Impact/Effort:**
```
Help me prioritize these 8 backlog items using Impact/Effort matrix:
[list items]

I need to decide what to tackle in next sprint.
```

**For Framework Recommendation:**
```
I have 12 items to prioritize. Not sure which framework to use.

Context: Early-stage startup, limited data, need to move fast,
high uncertainty. What framework should I use and why?
```

---

## Claude's Output Structure

For every prioritization request, Claude will provide:

1. **Recommended Framework** (with reasoning)
2. **Prioritized Table** (clean, shareable format)
3. **Key Insights** (patterns, trade-offs, gaps)
4. **Recommendation** (what to do next)
5. **Assumptions to Validate** (what Claude assumed, what you should verify)

---

## Output Requirements for Claude

When using this skill, Claude must:

✅ **Always use markdown tables** for prioritization results
✅ **Show calculations** for scoring frameworks (RICE, Weighted)
✅ **Provide visual matrix** for Impact/Effort and Value/Complexity
✅ **Include priority ranking** (1, 2, 3...) in output tables
✅ **List assumptions made** that should be validated
✅ **Give specific next steps** based on the prioritization
✅ **Help estimate missing data** - When the PM lacks estimates, Claude should:
   - Ask 2-3 clarifying questions to gather context, OR
   - Provide reasonable baseline estimates based on product type and industry patterns
   - Explain reasoning (e.g., "Based on typical B2B SaaS, SSO reaches 70% of enterprise customers")
   - Use ranges for uncertain estimates (e.g., "1000-2000 users" not "1500")
   - Clearly mark which numbers are estimates vs. provided data
   - Flag high-uncertainty items that need validation before decisions

❌ **Never use verbose paragraphs** for the main prioritization output
❌ **Never skip the reasoning** for framework selection
❌ **Never provide scores without context** or explaining the methodology
❌ **Never refuse to help due to missing data** - provide estimated ranges instead
❌ **Never give false precision** on estimates (e.g., don't say "exactly 1,247 users")

---

## Tips for Better Results

### Do:
- Provide context about your product and constraints
- Share what data you have available
- Mention upcoming deadlines or strategic goals
- Ask Claude to explain framework selection
- Request specific output format if you have preferences

### Don't:
- Expect perfect precision with limited data
- Skip validating assumptions with your team
- Use complex frameworks when simple ones work
- Forget to communicate the "why" behind priorities
- Treat any framework as the final answer (they're decision aids)

---

## Example: RICE Scoring Output

**Input:**
```
Use RICE to prioritize these 3 features for our project management tool:

1. Gantt chart view
2. Slack integration
3. Custom fields

We have 5K active teams, 4 engineers, targeting enterprise customers.
```

**Claude Output:**

### Framework Recommendation
**RICE Scoring** - You have user base data (5K teams) and can estimate impact. This gives you defensible, quantitative prioritization for stakeholder discussions.

### RICE Analysis

| Feature | Reach | Impact | Confidence | Effort (PM) | RICE Score | Rank |
|---------|-------|--------|------------|-------------|------------|------|
| Slack Integration | 4,000 | 2.0 | 100% | 2.0 | **4,000** | **1** |
| Custom Fields | 3,500 | 1.0 | 80% | 2.8 | **1,000** | **2** |
| Gantt Chart | 1,000 | 1.0 | 80% | 4.0 | **200** | **3** |

### Calculation Details

**Slack Integration:**
- Reach: 4,000 teams (80% would use integrations based on enterprise SaaS benchmarks)
- Impact: High (2.0) - Reduces context switching, major workflow improvement
- Confidence: 100% - Clear demand signal from customer requests
- Effort: 2 person-months (standard OAuth + webhook implementation)
- **Score: (4000 × 2.0 × 1.0) / 2.0 = 4,000**

**Custom Fields:**
- Reach: 3,500 teams (70% of enterprise users need customization)
- Impact: Medium (1.0) - Enables flexibility but doesn't change core workflow
- Confidence: 80% - Some validation needed on field types required
- Effort: 2.8 person-months (schema changes + UI work)
- **Score: (3500 × 1.0 × 0.8) / 2.8 = 1,000**

**Gantt Chart:**
- Reach: 1,000 teams (20% - mainly traditional PM users)
- Impact: Medium (1.0) - Alternative timeline views exist
- Confidence: 80% - Nice-to-have feedback, not urgent requests
- Effort: 4 person-months (complex visualization + interactions)
- **Score: (1000 × 1.0 × 0.8) / 4.0 = 200**

### Key Insights
- **Integrations >> Views:** Your customers value connecting tools over specialized views
- **Effort/Value trade-off:** Gantt chart takes 2× the effort of Slack integration for 1/4 the reach
- **Enterprise focus:** Both top priorities serve enterprise customization needs

### Recommendation
**Ship Slack integration first** (Q1), then custom fields (Q2). Consider pausing Gantt chart until you see demand from a specific high-value segment.

**Alternative to consider:** After Slack, explore general API access - might serve both custom fields AND specialized view needs.

### Assumptions to Validate
- [ ] Slack integration effort estimate - confirm with engineering
- [ ] 80% integration usage rate - check against similar features
- [ ] Custom field requirements - interview 5-10 enterprise customers
- [ ] Whether Gantt is must-have for specific verticals (construction, agencies)

---

## Example: Impact/Effort Matrix Output

**Input:**
```
Quick prioritization for sprint. Impact/Effort matrix:

1. Fix login bug (affects 5% of users)
2. Add dark mode
3. Improve search performance  
4. Build admin analytics dashboard
5. Set up automated testing
6. Add export to PDF
7. Update documentation
8. Refactor payment code

Context: 2-week sprint, 3 developers
```

**Claude Output:**

### Framework Recommendation
**Impact/Effort Matrix** - You need sprint-level decisions with a fixed team. This gives you quick visual prioritization without needing detailed estimates.

### Prioritization Matrix

| Item | Impact | Effort | Quadrant | Priority | Sprint Plan |
|------|--------|--------|----------|----------|-------------|
| Fix login bug | High | Low | 🎯 Quick Win | **1** | Week 1 (2 days) |
| Improve search | High | Medium | 🎯 Quick Win | **2** | Week 1-2 (4 days) |
| Analytics dashboard | High | High | 📋 Big Bet | **3** | Consider for next sprint |
| Automated testing | High | High | 📋 Big Bet | **4** | Consider for next sprint |
| Update docs | Low | Low | ⏰ Fill-In | **5** | Squeeze in if time |
| Export to PDF | Medium | Medium | ⏰ Fill-In | **6** | Backlog |
| Dark mode | Low | Medium | ❌ Money Pit | **7** | Defer |
| Refactor payment | Low | High | ❌ Money Pit | **8** | Defer (unless buggy) |

### Visual Matrix

```
           LOW EFFORT              MEDIUM EFFORT           HIGH EFFORT
         ┌──────────────────┬──────────────────────┬─────────────────────┐
         │                  │                      │                     │
HIGH     │  🎯 QUICK WINS   │  🎯 QUICK WINS       │  📋 BIG BETS        │
IMPACT   │                  │                      │                     │
         │  • Login bug     │  • Search perf       │  • Analytics        │
         │                  │                      │  • Auto testing     │
         │                  │                      │                     │
         ├──────────────────┼──────────────────────┼─────────────────────┤
         │                  │                      │                     │
MEDIUM   │                  │  ⏰ FILL-INS         │                     │
IMPACT   │                  │                      │                     │
         │                  │  • Export PDF        │                     │
         │                  │                      │                     │
         ├──────────────────┼──────────────────────┼─────────────────────┤
         │                  │                      │                     │
LOW      │  ⏰ FILL-INS     │  ❌ MONEY PIT        │  ❌ MONEY PIT       │
IMPACT   │                  │                      │                     │
         │  • Update docs   │  • Dark mode         │  • Refactor payment │
         │                  │                      │                     │
         └──────────────────┴──────────────────────┴─────────────────────┘
```

### Sprint Recommendation

**Week 1:**
- Days 1-2: Fix login bug (Priority 1)
- Days 3-5: Start search performance improvements

**Week 2:**
- Days 1-3: Complete search performance
- Days 4-5: Update documentation (Fill-In)

**Defer to Next Sprint:**
Choose ONE big bet based on strategic priority:
- **Analytics dashboard** if you need revenue/usage insights NOW
- **Automated testing** if you need to improve long-term velocity

### Key Insights
- You have 2 quick wins that fit in one sprint - do both
- Both big bets require full sprint commitment - don't split focus
- Dark mode is tempting but medium effort for low impact
- Payment refactor: only prioritize if it's causing bugs

### Critical Question to Answer
**Login bug affects only 5% of users** - Are these high-value customers? If yes, this jumps to absolute top priority. If no, search performance might be more impactful.

### Assumptions to Validate
- [ ] Login bug: Which customer segment is affected?
- [ ] Search performance: Current load time vs. target
- [ ] Big bets: Can analytics or testing be broken into smaller chunks?
- [ ] Payment refactor: Is there technical debt risk we're missing?

---

## Example: When You Don't Have Data

**Input:**
```
Use RICE but I don't have estimates. Help me prioritize:

1. Add webhooks for integrations
2. Dark mode
3. Team collaboration features
4. Performance improvements

Context: Early-stage B2B productivity tool, 200 customers (mostly small businesses), 
3 engineers, trying to figure out Q1 priorities
```

**Claude Output:**

### Let me help you estimate

I'll provide baseline estimates based on early-stage B2B SaaS patterns. These are **educated guesses** - you should validate the high-impact items with customer conversations.

### RICE Analysis (with estimated ranges)

| Feature | Reach (est.) | Impact | Confidence | Effort (PM) | RICE Score | Rank |
|---------|--------------|--------|------------|-------------|------------|------|
| Webhooks | 60-100 | 2.0 | 60% | 3.0 | **40** | **1** |
| Team features | 80-120 | 2.0 | 70% | 4.0 | **35** | **2** |
| Performance | 150-200 | 1.0 | 80% | 2.0 | **75** | **3** |
| Dark mode | 40-60 | 0.5 | 50% | 1.5 | **13** | **4** |

### How I Estimated (Validate These!)

**Webhooks:**
- **Reach: 60-100 customers (30-50%)** - Early-stage companies building integrations typically see 30-50% of customers using webhook features. Depends heavily on your positioning (API-first vs. UI-first).
- **Impact: High (2.0)** - Enables automation and ecosystem, can be deal-maker for technical buyers
- **Confidence: 60%** - Medium confidence. Check: Are customers asking for specific integrations? That signals real need.
- **Effort: 3 PM** - Webhook infrastructure + documentation + examples

**Team Collaboration:**
- **Reach: 80-120 customers (40-60%)** - Small businesses often start with 1 user, expand to team. Your growth depends on multi-user adoption.
- **Impact: High (2.0)** - Increases stickiness, drives expansion revenue (per-seat pricing?)
- **Confidence: 70%** - Higher confidence. B2B tools need team features to grow ACV.
- **Effort: 4 PM** - Permissions, sharing, team admin, user management

**Performance:**
- **Reach: 150-200 customers (75-100%)** - Everyone experiences performance. Prioritize if currently slow.
- **Impact: Medium (1.0)** - Depends on current state. "Fast enough" vs "frustratingly slow" changes impact.
- **Confidence: 80%** - High confidence on reach, but is performance actually a problem?
- **Effort: 2 PM** - Assuming targeted optimizations, not full rewrite

**Dark Mode:**
- **Reach: 40-60 customers (20-30%)** - Personal preference feature, not everyone uses
- **Impact: Low (0.5)** - Nice-to-have, rarely drives decisions
- **Confidence: 50%** - Low confidence. Check: Are people actually asking for this?
- **Effort: 1.5 PM** - Theme system + testing across all screens

### Key Questions to Answer

Before committing to these priorities, validate:

1. **Webhooks:** 
   - ❓ Are 5+ customers asking for specific integrations?
   - ❓ Would this unlock expansion into technical/engineering buyers?
   - ❓ Do you have 1-2 partners ready to integrate?

2. **Team Features:**
   - ❓ What % of your 200 customers are multi-user teams today?
   - ❓ Are single users asking to bring colleagues?
   - ❓ Do you have per-seat pricing ready?

3. **Performance:**
   - ❓ What's your current load time? (If <2 seconds, maybe not urgent)
   - ❓ Are customers complaining about speed?
   - ❓ Would 50% faster actually change behavior?

4. **Dark Mode:**
   - ❓ How many explicit requests have you received? (If <10, defer)

### Recommendation

**Based on estimated ranges:**

**Ship in Q1:**
1. **Webhooks** (if validation shows integration demand)
2. **Team features** (if multi-user adoption is growing)

**Validate first:**
- Performance: Measure current metrics. Only prioritize if actually slow.
- Dark mode: Defer unless you get 20+ requests

**Data you need:**
- Survey your 200 customers: "What would make you use this 2x more?"
- Check analytics: What % of customers have added a second user?
- Review support tickets: What are top 5 complaints?

### Confidence Levels

🟢 **High confidence (70%+):** Team features - B2B SaaS needs this to scale
🟡 **Medium confidence (50-70%):** Webhooks - depends on your market positioning
🔴 **Low confidence (<50%):** Performance, Dark mode - need data to validate

---

## Version

v1.0 - Four core frameworks (RICE, Impact/Effort, Value/Complexity, Weighted Scoring)

---

## Related Skills

Coming soon:
- Roadmap Planning
- Stakeholder Communication  
- Product Strategy

---

## License

MIT License - Use freely, share widely, build upon it.
