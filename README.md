# McKinsey Claude Skills

Professional consulting frameworks packaged as Claude Skills. Built by ex-McKinsey consultant for consultants, PMs, and strategists.

## Available Skills

### 🎯 SCPR Framework
Structured problem-solving using Situation-Complication-Problem-Recommendation format.

**Use when:**
- Structuring strategic arguments
- Creating executive summaries
- Developing clear problem statements
- Writing memos or recommendations

**Download:** [scpr-framework.skill](scpr-framework.skill)  
**View Source:** [SKILL.md](scpr-framework/SKILL.md)

**Example Output:**
```
Situation: Series B SaaS startup, $15M ARR, serving creative agencies
Complication: AI tools reducing usage 15%, $500K pipeline paused
Problem: How to return to 25%+ growth within 12 months?
Recommendations:
1. Launch AI-native workflow engine by Q2 2025
2. Shift positioning to "AI-augmented agency ops" by Q1 2025
3. Introduce usage-based AI tier by Q2 2025
```

### 🌳 Issue Tree Builder
Break down complex problems into MECE components using hypothesis-driven approach.

**Use when:**
- Decomposing strategic questions
- Structuring analysis before diving into data
- Creating work plans with prioritization
- Preparing for case interviews

**Download:** [issue-tree-builder.skill](issue-tree-builder.skill)  
**View Source:** [SKILL.md](issue-tree-builder/SKILL.md)

**Example Output:**
```
How to increase revenue 50%?
├─ Average Order Value (Price)
│  ├─ Pricing 15% below market - test if can increase
│  └─ Cart 1.8 items vs 2.5 industry - cross-sell opportunity
├─ Traffic Volume (Quantity)
│  └─ Paid CAC $45 vs LTV $120 - can 2x spend profitably
└─ Conversion Rate
   └─ Checkout abandonment 68% vs 58% - friction exists
```

## How to Use

1. Download the `.skill` file
2. In Claude.ai, go to Settings → Skills
3. Click "Add Skill" and upload the file
4. Start using the framework in your conversations

## Coming Soon

- Executive Summary Generator
- Slide Structure Helper
- Excel Structure Helper

## About

Created with Claude to share consulting best practices. Built publicly to help consultants transition to product and AI roles.

**Connect:** [LinkedIn](https://www.linkedin.com/in/sruthichintakunta/)

---

*Built with Claude | MIT License*
