---
name: why
description: Metacognitive questioning skill. Use BEFORE any task where the agent lacks sufficient context — planning, requirements gathering, debugging, user discovery, creative briefs. Determines what information is missing, asks the minimum viable questions to proceed effectively, and manages question pacing. NOT for tasks where context is already sufficient. NOT a question library — the agent already knows questioning frameworks.
---

# Why — Metacognitive Questioning

You already know how to ask questions. This skill tells you **when to ask, what depth to go, and when to stop.**

## Hard Rules

1. **Never fire more than 2 questions per message.** One is ideal. Two is the max. Bundle only when they're tightly related.
2. **Never ask what you can infer or look up.** Check files, context, conversation history, and prior answers first. Asking questions the user already answered kills trust.
3. **Always explain why you're asking** when the purpose isn't obvious. "I'm asking because this affects how I structure the whole project" > bare question.
4. **Confirm understanding before acting.** Paraphrase back: "So if I understand correctly: [summary]. Is that right?" — then proceed.
5. **Never ask accusatory "why" questions.** Use "What led to that?" or "What's behind that?" instead of "Why did you do that?"

## The Intake Check

Before starting any task, run this decision:

```
Do I have enough context to produce quality output?
  │
  ├─ YES → Proceed. No questions needed.
  │
  ├─ PARTIAL → Act on what you know. Flag uncertainties inline.
  │            "I'm assuming X — let me know if that's wrong."
  │
  └─ NO → Ask. But ask SMART (see below).
```

### What Counts as "Enough Context"

Categorize missing information:

| Category | Definition | Action |
|----------|-----------|--------|
| **CRITICAL** | Blocks everything if missing. Wrong assumption = wasted work. | Must ask. Don't proceed without it. |
| **IMPORTANT** | Degrades quality if missing. Output will be generic or partially wrong. | Ask if you can do it in 1 question. Otherwise flag as assumption. |
| **NICE-TO-HAVE** | Improves output but defaults exist. | Don't ask. Use sensible defaults. Mention the default you chose. |
| **INFERABLE** | Can be determined from context, files, or conversation history. | Never ask. Just infer and note your inference. |

**The principle: ask the fewest questions that prevent the most damage downstream.**

## Framework Selection

Read the situation, pick the approach:

| Situation | Approach | Why |
|-----------|----------|-----|
| First interaction, no context | **Funnel** — one broad question, then narrow | Need scope before depth |
| User has a vague goal | **GROW** — Goal → Reality → Options → Will | Structured path to committed action |
| User describes a problem to solve | **SPIN** — Situation → Problem → Implication → Need-Payoff | Full pain before jumping to solutions |
| User's answer has gaps or contradictions | **Socratic probe** — clarify → check assumptions → ask for evidence | Surface what's really going on |
| Need to explore options | **What If** questions + perspective shifts | Opens possibilities |
| User is stuck or blocked | **5 Whys** (for root cause) or **Question Burst** (for reframing) | Get past symptoms or open new angles |
| Planning conversation | **Why → What If → How** progression | Understanding → imagination → execution |
| Checking commitment | **Scaling** — "1-10, how committed?" then "What would raise it?" | Surfaces hidden blockers |
| Debugging / troubleshooting | **5 Whys** + probing | Symptoms → root cause |

Don't rigidly follow one framework. Switch when the conversation shifts.

## Question Depth Matching

Match cognitive depth to where you are in the conversation:

| Phase | Depth | Question Type |
|-------|-------|---------------|
| **Early discovery** | Level 1-2 (Remember, Understand) | "What is ___?" · "Can you describe ___?" |
| **Clarification** | Level 2-3 (Understand, Apply) | "How would that work?" · "Can you give an example?" |
| **Analysis** | Level 4 (Analyze) | "What are the parts?" · "What's the relationship between X and Y?" |
| **Decision-making** | Level 5 (Evaluate) | "Which option is stronger and why?" · "What are the tradeoffs?" |
| **Creation/planning** | Level 6 (Create) | "How would you design this?" · "What would you propose?" |

**Don't ask Level 5 questions when Level 1 isn't answered.** Build up.

## Pacing Rules

### Question Budget
- **Simple tasks** (write a post, fix a bug): 0-2 questions before acting
- **Medium tasks** (plan a feature, review a strategy): 2-5 questions
- **Complex tasks** (architect a system, define a roadmap): 5-10 questions, spread across exchanges
- **Never exceed 10 questions total** before producing something. If you still don't have enough, produce a draft and let the user react to it — that's faster than more questions.

### Fatigue Detection
Watch for these signals that you're asking too much:
- Short, terse answers (user was giving paragraphs, now giving words)
- "Just do it" / "Whatever you think" / "You decide"
- Repeating what they already said (you missed it)
- Long pauses before responding

When you detect fatigue: **stop asking and start doing.** Use your best judgment, flag assumptions, and iterate from output rather than from questions.

### Rhythm
- After 2 questions, offer something: an observation, a partial answer, a summary
- Never send 3 consecutive question-only messages
- Mix questions with value: "Based on what you've said, I think X. Does that match your thinking?"

## Gap Detection

When reviewing a user's input, actively look for:

### Common Gaps in Requirements
- **Audience undefined** — who is this for?
- **Success criteria missing** — how will we know this worked?
- **Scope ambiguous** — what's in vs. out?
- **Priority unclear** — if we can't do everything, what matters most?
- **Constraints unstated** — timeline, budget, tech stack, approvals needed?
- **Assumptions buried** — what are they taking for granted that might be wrong?

### Common Gaps in Problem Descriptions
- **Symptom vs. cause** — they described what happened, not why
- **Frequency unknown** — does this happen always, sometimes, or once?
- **Impact unstated** — how bad is this actually?
- **Prior attempts missing** — what did they already try?
- **Context absent** — when did this start? what changed?

### What's NOT Being Said
- If they describe a technical problem but haven't mentioned users → ask about user impact
- If they describe a goal but haven't mentioned constraints → ask about constraints
- If they describe what they want but not why → ask about the underlying need
- If everything sounds perfect → probe for what's not working ("What's the hardest part?")

## Confirmation Patterns

Before acting on gathered information, confirm:

### For Simple Tasks
```
"Got it — [one-sentence summary]. Building that now."
```

### For Complex Tasks
```
"Let me make sure I have this right:
- [Key point 1]
- [Key point 2]  
- [Key point 3]

I'm assuming [stated assumption]. Anything I'm missing?"
```

### For Ambiguous Situations
```
"I see two ways to interpret this:
A) [Interpretation 1]
B) [Interpretation 2]

Which is closer to what you mean?"
```

## Integration With Other Skills

The why-skill is a **horizontal check** other skills can call:

```
Any skill starting work:
  1. Run intake check (do I have enough context?)
  2. If NO → ask minimum viable questions
  3. If PARTIAL → proceed with flagged assumptions
  4. If YES → execute
```

When composing with domain skills (e.g., social-context, planning-skill):
- Let the domain skill define WHAT information is needed
- Let why-skill determine HOW MUCH questioning is appropriate given the conversation state
- Domain skill says "I need audience, platform, tone" — why-skill says "audience is CRITICAL (ask), platform is IMPORTANT (ask if easy), tone is NICE-TO-HAVE (default to casual)"

## This Skill Does NOT

- Replace domain-specific discovery (social-context has its own interview, pm-skills has requirements templates)
- Provide a library of question templates (the model already knows those)
- Force a rigid questioning script (it's a decision framework, not a questionnaire)
- Apply to tasks where context is already sufficient (if you have enough, just work)
