# Gap Detection Patterns

> Common information gaps organized by task type. Use this to quickly identify what's missing from a user's request before proceeding.

## Universal Gaps (Apply to Most Tasks)

| Gap | Why It's Critical | Detection Question |
|-----|------------------|-------------------|
| **Who is this for?** | Audience shapes everything — tone, depth, format, complexity | If no audience mentioned, ask. |
| **What does success look like?** | Without criteria, you can't evaluate your own output | If no success criteria, ask or propose some. |
| **What's the scope?** | Unbounded tasks produce unbounded (and usually wrong) output | If scope feels infinite, ask "What's in vs. out?" |
| **What matters most?** | Can't prioritize without knowing priorities | If everything seems equally weighted, ask for ranking. |
| **What are the constraints?** | Timeline, budget, tech stack, approvals, existing systems | If no constraints mentioned, at least one exists — ask. |
| **What's been tried?** | Avoids repeating failed approaches and reveals what "good" means to them | If problem sounds solvable, ask why it hasn't been solved yet. |

## Task-Specific Gaps

### Planning / Roadmap
- Timeline: When does this need to be done?
- Dependencies: What blocks what?
- Resources: Who's available? What tools exist?
- Risk tolerance: What happens if this fails?
- Decision authority: Who approves?

### Requirements / Building
- Users: Who uses this? How technical are they?
- Existing system: What does this replace or integrate with?
- Edge cases: What happens when things go wrong?
- Scale: 10 users or 10,000?
- Data: What data exists? What format? Who owns it?

### Debugging / Troubleshooting
- Reproduction: Can you make it happen again?
- Timing: When did this start? What changed?
- Frequency: Always, sometimes, or once?
- Impact: Who's affected? How badly?
- Logs/errors: What does the error message say?

### Creative / Content
- Audience: Who reads/watches/uses this?
- Tone: Formal? Casual? Technical? Playful?
- Format: Blog? Post? Video? Email? Slide deck?
- Reference: "Make it like ___" — any examples they admire?
- Goal: Awareness? Conversion? Education? Entertainment?

### Strategy / Decision
- Options on the table: What choices exist?
- Evaluation criteria: What matters in this decision?
- Stakeholders: Who cares about the outcome?
- Reversibility: Can this be undone?
- Time pressure: When must this be decided?

## The "What's NOT Being Said" Checklist

Experienced humans catch these gaps instinctively. An agent should actively check:

| If They Mention... | But NOT... | Probe For... |
|-------------------|-----------|--------------|
| A technical solution | Users or audience | "Who will use this? How technical are they?" |
| A goal | Constraints | "What are the limits — time, budget, resources?" |
| What they want | Why they want it | "What's the underlying need? What problem does this solve?" |
| A problem | Its impact | "How bad is this? Who's affected?" |
| Everything going well | Challenges | "What's the hardest part right now?" |
| Features | Priority | "If you could only ship one of these, which one?" |
| A plan | Risks | "What could go wrong? What's the backup?" |
| The ideal outcome | Current reality | "Where are you now vs. where you want to be?" |

## Information Priority Classification

For each gap identified, classify:

```
CRITICAL  → Must ask. Wrong assumption = wasted work.
             Example: building for iOS when they need Android.

IMPORTANT → Ask if it's a 1-question answer. Otherwise flag as assumption.
             Example: brand tone — you can default to "professional-casual" and note it.

NICE-TO-HAVE → Don't ask. Use sensible defaults. Mention the default.
             Example: color scheme — use a standard unless they specify.

INFERABLE → Never ask. Determine from context.
             Example: if they pasted React code, the tech stack is React.
```
