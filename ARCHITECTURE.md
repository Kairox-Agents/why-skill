# Why-Skill: Architectural Position

## The Problem This Skill Actually Solves

A SOTA model like Claude Opus already knows SPIN, GROW, Socratic questioning, 5 Whys, and every other framework from its training data. Teaching it "use SPIN for discovery" adds zero value — it's prompt-level knowledge dressed as a skill.

What Opus actually lacks — and what humans naturally have — is the **metacognitive layer around questioning:**

| What Humans Have | What Models Lack | What This Skill Provides |
|-----------------|-----------------|-------------------------|
| **Timing intuition** — sensing "I don't have enough info yet" | Models either over-ask (20 questions) or under-ask (assume everything) | Decision framework: when to ask, when to act |
| **Knowing what they don't know** — instinct for which missing info causes the most damage | Models treat all missing info equally | Priority framework: which questions matter most |
| **Reading what's NOT said** — catching omissions from experience | Models take responses at face value | Gap detection: what should have been said but wasn't |
| **Question fatigue awareness** — sensing when someone's annoyed | Models don't track conversational energy | Pacing rules: how many questions, how fast, when to stop |
| **Contextual memory** — remembering what was already answered | Models re-ask or ignore prior context | Context check: what do I already know vs. what's missing |
| **Strategic patience** — sitting with ambiguity, not rushing to solutions | Models want to produce output immediately | Hold framework: when NOT to answer yet |

## Where It Fits in a Broader Skill System

### Three-Layer Architecture

```
METACOGNITIVE LAYER (skills about thinking)
├── why-skill           → When/what/how deep to ask
├── judgment-skill      → When to act vs. wait, what matters most
├── reflection-skill    → Know what you don't know, check your work
└── adaptation-skill    → Read the room, adjust approach

EXECUTION LAYER (skills about doing)
├── planning-skill      → Decompose goals into steps
├── research-skill      → Find and evaluate information
├── creation-skills     → Write, code, design, analyze
└── review-skills       → Quality gates before output

RELATIONSHIP LAYER (skills about people)
├── context-skill       → Remember and use what you know about the user
├── communication-skill → Match tone, depth, format to audience
└── boundary-skill      → Know when to defer to a human expert
```

### Why-Skill as the "Intake" Skill

The why-skill sits at the top of the metacognitive layer. It's the skill that **determines what information you need before any other skill can do good work.** Every planning session, every creative brief, every debugging session starts with questions.

Flow:
```
User Request → why-skill (do I have enough to proceed?)
                  ↓ NO → Ask the minimum viable questions
                  ↓ YES → Pass to execution skills
                  ↓ PARTIAL → Act on what you know, flag uncertainties
```

### The "Minimum Viable Questioning" Principle

The skill's core insight: **the goal is not to ask every possible question. It's to ask the fewest questions that produce the highest-quality downstream output.**

This means the skill must know:
1. What information is CRITICAL (blocks everything if missing)
2. What information is IMPORTANT (degrades quality if missing)  
3. What information is NICE-TO-HAVE (can assume defaults)
4. What information the model can INFER (shouldn't ask at all)

## What This Skill is NOT

- NOT a library of question frameworks (the model has those)
- NOT a prompt that says "ask good questions" (zero value)
- NOT a rigid questionnaire to follow step-by-step
- NOT a replacement for domain-specific discovery (social-context, pm-skills, etc.)

## What This Skill IS

- A **decision framework** for when to ask, what to ask, how deep to go
- A **gap detector** that identifies what's missing from context
- A **pacing engine** that manages question fatigue
- A **quality gate** that prevents action on insufficient information
- A **metacognitive tool** that makes the model more self-aware about its own uncertainty

## Integration Points

The why-skill should be composable with domain skills:
- **social-skills** calls why-skill's gap detection before generating content
- **planning-skill** calls why-skill to validate requirements before decomposing
- **any skill** can call why-skill's "do I have enough to proceed?" check

This makes it a **horizontal skill** (used across domains) rather than a vertical one (used within a domain).
