# why-skill

A metacognitive questioning skill for AI agents. Teaches agents not *how* to ask questions (they already know that), but **when to ask, what depth to go, and when to stop**.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

## The Problem

A SOTA model like Claude Opus already knows SPIN, GROW, Socratic questioning, the 5 Whys, and every other questioning framework from its training data. A skill that says "use SPIN for requirements gathering" adds zero value — that's prompt-level knowledge dressed up as a skill.

What models actually lack — and what humans naturally have — is the **metacognitive layer around questioning:**

| What Humans Have | What Models Lack |
|-----------------|-----------------|
| **Timing intuition** — "I don't have enough info yet" | Models either over-ask (20 questions before acting) or under-ask (assume everything and charge ahead) |
| **Knowing what they don't know** — instinct for which missing info causes the most damage downstream | Models treat all missing information equally |
| **Reading what's NOT said** — catching omissions from experience | Models take responses at face value |
| **Question fatigue awareness** — sensing when someone's getting annoyed | Models don't track conversational energy |
| **Strategic patience** — sitting with ambiguity, not rushing to output | Models want to produce immediately |

This skill gives agents those human instincts.

## What This Skill Does

- **Decision framework** for when to ask, what to ask, how deep to go
- **Gap detection** that identifies what's missing from context before acting
- **Pacing engine** that manages question fatigue and conversational flow
- **Quality gate** that prevents action on insufficient information
- **Minimum viable questioning** — the fewest questions that produce the highest-quality downstream output

## What This Skill is NOT

- Not a library of question frameworks (the model has those)
- Not a prompt that says "ask good questions" (zero value)
- Not a rigid questionnaire to follow step-by-step
- Not a replacement for domain-specific discovery skills

## How It Fits in a Broader System

The why-skill is a **horizontal metacognitive skill** — it works across domains, not within one.

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

Any skill can call why-skill's "do I have enough to proceed?" check. A social media skill calls it before generating content. A planning skill calls it before decomposing tasks. It's the "intake" layer that sits before execution.

```
User Request → why-skill (do I have enough to proceed?)
                  ↓ NO → Ask the minimum viable questions
                  ↓ YES → Pass to execution skills
                  ↓ PARTIAL → Act on what you know, flag uncertainties
```

---

## The Theory: Questioning Frameworks

The skill itself focuses on the metacognitive layer — but the frameworks below are the foundation it's built on. Understanding them helps you understand why the skill makes the decisions it does.

### Maxwell: Good Leaders Ask Great Questions

John C. Maxwell's *Good Leaders Ask Great Questions* (2014) identifies 8 principles of effective questioning:

1. **You only get answers to the questions you ask.** The fear of looking foolish prevents people from asking. Overcoming this fear is step one.
2. **Questions unlock doors.** Every question is a key to a conversation, opportunity, or insight that wouldn't exist without the asking.
3. **Questions connect people.** Asking is the most effective way to build relationships. It signals genuine interest.
4. **Questions cultivate humility.** Asking "I don't know — can you help me understand?" demonstrates vulnerability and builds trust.
5. **Questions engage others.** People contribute more when asked than when told. Engagement through questioning > engagement through instruction.
6. **Questions build better ideas.** Shared thinking through questioning leads to creativity. The best ideas come from collision, not isolation.
7. **Questions shift perspective.** You can't understand someone's viewpoint without asking for it. Assumptions about shared beliefs are usually wrong.
8. **Questions break ruts.** Curiosity prevents stagnation. The right question reframes a problem and opens new paths.

Maxwell also identifies **three levels of listening** — critical for agents:
- **Internal** — focused on your own thoughts (worst — this is what agents do when they plan their response while "listening")
- **Focused** — paying attention to the speaker (good)
- **Global** — reading context, emotion, what's NOT said (best — this is what the skill trains)

His favorite team questions:
- "What do you think?" — unlocks others' insights
- "How can I serve you?" — demonstrates commitment
- "What do I need to communicate?" — surfaces gaps
- "Did we exceed expectations?" — drives excellence

**What this means for agents:** The value isn't in the specific questions — it's in the principle that asking should be a fundamental reflex, not an afterthought. An agent should ask before assuming, every time.

### Socratic Questioning (R.W. Paul's Six Types)

The Socratic method, formalized by Richard Paul into six types of questions, is the foundation of critical thinking through inquiry:

| Type | Purpose | Example Questions |
|------|---------|-------------------|
| **1. Clarification** | Go deeper, surface meaning | "What do you mean by ___?" · "Could you put that another way?" · "Can you give me an example?" |
| **2. Probe Assumptions** | Surface hidden beliefs | "What are you assuming?" · "What could we assume instead?" · "What would happen if that assumption were wrong?" |
| **3. Probe Reasons & Evidence** | Challenge the basis | "How do you know?" · "What evidence supports that?" · "What would change your mind?" |
| **4. Viewpoints & Perspectives** | Expand the lens | "What's another way to look at this?" · "How would [someone else] see this?" · "What's the counter-argument?" |
| **5. Implications & Consequences** | Trace the chain | "If that's true, what else must be true?" · "What are the consequences?" · "How does this affect ___?" |
| **6. Questions About the Question** | Meta-questioning | "Why is this question important?" · "What was the point of asking that?" · "How does this apply?" |

**What this means for agents:** Types 1-3 are essential for requirements gathering (clarify → challenge assumptions → demand evidence). Types 4-5 are essential for planning (explore alternatives → trace consequences). Type 6 is valuable for transparency — explaining to users *why* you're asking.

### Berger: Why → What If → How

Warren Berger's *A More Beautiful Question* (2014) proposes a three-stage innovation questioning process:

| Stage | Mindset | Purpose | Example |
|-------|---------|---------|---------|
| **Why?** | Observation | Understand the problem, challenge the status quo | "Why does this problem exist?" · "Why hasn't anyone solved this?" · "Why do we do it this way?" |
| **What If?** | Imagination | Generate possibilities without judgment | "What if we removed this constraint?" · "What if we combined X with Y?" · "What if we started from scratch?" |
| **How?** | Execution | Turn possibilities into action plans | "How could we actually build this?" · "How do we test this?" · "How do we get from here to there?" |

Berger also advocates **question-storming** — brainstorming questions about a problem instead of brainstorming answers. This works because:
- Questions open thinking; answers narrow it
- People are less defensive about questions than proposed solutions
- Questions surface assumptions you didn't know you had

His distinction between old and new business questions is sharp:
- **Old:** "How many? How much? How fast?" (closed, quantitative)
- **New:** "Why? What if? How might we?" (open, generative)

**What this means for agents:** The Why → What If → How progression maps directly to planning conversations. Don't jump to "How?" before "Why?" is answered. And when a user is stuck, try question-storming — generate 10 questions about their problem and let them pick which ones feel most important.

### SPIN Selling (Neil Rackham)

Developed from research studying 35,000 sales calls, SPIN is the most empirically-validated questioning framework for discovery conversations:

| Phase | Question Type | Purpose | Example |
|-------|-------------|---------|---------|
| **S**ituation | Context gathering | Understand current state | "What tools are you currently using?" · "How many people are on your team?" · "What's your current workflow?" |
| **P**roblem | Pain identification | Surface problems and frustrations | "What's the biggest challenge with ___?" · "Where do things break down?" · "What frustrates you most?" |
| **I**mplication | Impact exploration | Understand consequences of the problem | "What happens when that goes wrong?" · "How does that affect your team?" · "What does this cost you?" |
| **N**eed-Payoff | Solution framing | Get the user to articulate the value of solving | "What would it mean if you could solve this?" · "How would things change?" · "What would success look like?" |

The critical insight: **the order matters.** Jumping straight to Need-Payoff ("What do you want?") produces shallow answers. People can't articulate what they need until they've fully explored what's wrong. S → P → I → N builds understanding before solutions.

Rackham's research found that top performers asked 4x more Implication questions than average performers. The Implication stage — "what happens if this stays broken?" — is where urgency and clarity emerge.

**What this means for agents:** This is the most directly applicable framework for user discovery. An agent gathering requirements should follow S → P → I → N order, resisting the urge to jump to solutions after hearing the first problem statement.

### GROW Model (Sir John Whitmore)

Developed for coaching, GROW provides structure for any goal-setting or planning conversation:

| Phase | Focus | Example Questions |
|-------|-------|-------------------|
| **G**oal | What do you want? | "What do you want to achieve?" · "What would success look like?" · "Why is this important to you now?" · "How will you know when you've achieved it?" |
| **R**eality | Where are you now? | "What's the current situation?" · "What's working well?" · "What have you tried?" · "What results did that produce?" · "What's really going on (intuition)?" |
| **O**ptions | What could you do? | "What could you do to change this?" · "What else?" · "What if you had unlimited resources?" · "Who could help?" · "Which options interest you most?" |
| **W**ill | What will you do? | "What specifically will you do?" · "When will you start?" · "What could get in the way?" · "On a 1-10 scale, how committed are you?" · "What would raise it to a 10?" |

The **commitment scale** is one of the most powerful coaching tools: "On a 1-to-10, how committed are you?" If less than 8, ask "What would raise it?" This surfaces hidden objections and practical blockers that the person wouldn't volunteer otherwise.

**What this means for agents:** Directly applicable to project planning. And the "What would raise it to a 10?" technique works for agents too — when a user seems lukewarm on a plan, don't just proceed. Ask what's holding them back.

### The 5 Whys (Toyota Production System)

Simple but powerful: ask "Why?" five times to move from symptoms to root causes.

**Example:**
1. Why did the deployment fail? → The config file was wrong
2. Why was the config file wrong? → Someone manually edited it
3. Why did someone manually edit it? → There's no automated config management
4. Why is there no automated config management? → It was never set up after the migration
5. Why wasn't it set up? → No one owns the deployment pipeline

**Root cause:** No ownership of the deployment pipeline (not "the config was wrong")

The power is in discipline — most people stop at Why #1 or #2 and fix the symptom. The 5 Whys forces you past symptoms to systemic causes.

**What this means for agents:** Essential for debugging and troubleshooting. Users describe symptoms ("my server crashed"). The agent's job is to reach root causes. But note: "Why?" can sound accusatory. Softer alternatives work better: "What led to that?" or "What's behind that?"

### Hal Gregersen: Question Burst (MIT Sloan)

A structured technique for generating insight through questions:

1. **Frame the challenge** in 1-2 sentences
2. **Set a timer for 4 minutes**
3. **Generate as many questions as possible** about the challenge
4. **Rules:** Questions only. No preambles. No answers. No judgments.
5. **After 4 minutes:** Review. Select 3-4 "catalytic" questions that shift how you think about the problem

Why it works: questions are less threatening than solutions, high volume (15-20 in 4 minutes) surfaces unexpected angles, and the "no answers" rule prevents premature convergence.

**What this means for agents:** When a user is stuck, instead of proposing solutions, try: "Let me generate 10 questions about this challenge — see which ones feel most important to you." This structured approach surfaces what the user really cares about.

### Bloom's Taxonomy (Question Depth)

Questions can target six levels of cognitive complexity:

| Level | Action | Question Starters | Agent Context |
|-------|--------|-------------------|---------------|
| **1. Remember** | Recall facts | "What is ___?" · "List the ___" | Requirements gathering: get the facts first |
| **2. Understand** | Explain meaning | "Explain ___" · "What's the difference between?" | Clarification: make sure you understand |
| **3. Apply** | Use in context | "How would you use ___?" · "Give an example" | Validation: test understanding with examples |
| **4. Analyze** | Break into parts | "What are the components?" · "What's the relationship?" | Planning: decompose the problem |
| **5. Evaluate** | Judge/assess | "Do you agree? Why?" · "What are the pros and cons?" | Decision-making: weigh options |
| **6. Create** | Generate new | "How would you design ___?" · "What would you propose?" | Innovation: build something new |

**What this means for agents:** Match question depth to context. Don't ask Level 5 (evaluation) questions when Level 1 (facts) hasn't been established. Requirements gathering starts at Level 1-2 and works up. Strategy conversations need Level 4-6.

### Practical Question Types

A working taxonomy for everyday use:

| Type | What It Does | When to Use |
|------|-------------|-------------|
| **Open** | Invites wide-ranging response | Exploration, early discovery |
| **Closed** | Gets yes/no or specific fact | Confirmation, narrowing down |
| **Probing** | Digs deeper into a response | Follow-up, "tell me more" |
| **Funnel** | Broad → narrow (or reverse) | Structured discovery |
| **Reflective** | Mirrors back what was said | Validation, showing you listened |
| **Hypothetical** | Explores possibilities | Planning, testing assumptions |
| **Scaling** | Quantifies subjective feelings | Prioritization, commitment |
| **Silence** | Gives space after asking | Letting someone think (hardest for agents) |

---

## Anti-Patterns: How Questions Fail

| Anti-Pattern | Why It Fails | What to Do Instead |
|-------------|-------------|-------------------|
| **Asking 10 questions at once** | Overwhelms. User answers the easiest, skips the rest | 1-2 questions per message, max |
| **"Tell me everything about your project"** | Too broad. No structure for response | Start with one specific funnel question |
| **Closed when you need open** | Gets yes/no when you need context | "What's the goal?" not "Is this for marketing?" |
| **Leading questions** | Biases the response, misses the truth | Ask neutral first, suggest after |
| **"Why?" accusatorially** | Makes people defensive | "What led to that decision?" instead |
| **Skipping confirmation** | Builds on misunderstandings | "So if I understand correctly, ___?" |
| **Asking what you should know** | Wastes time, breaks trust | Read context/files first, ask what's unfindable |
| **Rapid-fire interrogation** | Feels like an interview, not a conversation | Mix questions with observations and value |
| **Never explaining why you're asking** | User doesn't understand the purpose | "I'm asking because this affects ___" |
| **Re-asking what was answered** | Signals you're not listening | Acknowledge previous answer before building |
| **Asking forever, never acting** | Question fatigue — user just wants results | Set a question budget, then act |

---

## Framework Selection Guide

Different situations call for different approaches:

| Situation | Best Framework | Why |
|-----------|---------------|-----|
| First interaction, no context | **Funnel** (broad → narrow) | Need scope before depth |
| User has a vague goal | **GROW** | Structured path from goal to commitment |
| User describes a problem | **SPIN** | Full pain exploration before solutions |
| Answer doesn't make sense | **Socratic (Types 1-3)** | Clarify → check assumptions → demand evidence |
| Need to explore options | **What If** + **Socratic Type 4** | Opens possibilities and alternative perspectives |
| User is stuck | **5 Whys** or **Question Burst** | Root cause or creative reframing |
| Planning conversation | **Why → What If → How** | Understanding → imagination → execution |
| Commitment check | **GROW (Will)** + **Scaling** | "1-10, how committed?" surfaces blockers |
| Debugging/troubleshooting | **5 Whys** + **Probing** | Symptoms → root cause |

---

## Core Principles

These are the principles the skill enforces:

1. **Ask before assuming.** Always prefer a question over an assumption.
2. **One question at a time.** Never fire 5 questions in a single message.
3. **Match depth to context.** Don't ask evaluation questions when facts aren't established.
4. **Explain why you're asking.** Users cooperate more when they understand the purpose.
5. **Listen globally.** Process context, implied meaning, and what's NOT said.
6. **Follow the natural progression.** Situation → Problem → Implication → Solution, not the reverse.
7. **Confirm before building.** Paraphrase understanding back before acting on it.
8. **Mix questions with value.** Don't just interrogate — offer observations and insights between questions.
9. **Know when to stop.** Enough questions to act; not so many the user gets frustrated.
10. **Adapt to the moment.** No rigid script — choose the right question type for the situation.

---

## Sources

| Source | Type | Key Contribution |
|--------|------|-----------------|
| Maxwell, J.C. (2014). *Good Leaders Ask Great Questions* | Book | 8 principles, self/team questions, listening levels |
| Paul, R.W. Six Types of Socratic Questions | Academic framework | Clarification → assumptions → evidence → perspectives → implications → meta |
| Berger, W. (2014). *A More Beautiful Question* | Book | Why → What If → How progression, question-storming |
| Rackham, N. (1988). *SPIN Selling* | Research (35,000 calls) | Situation → Problem → Implication → Need-Payoff |
| Whitmore, J. (2009). *Coaching for Performance* | Book | GROW model: Goal → Reality → Options → Will |
| Gregersen, H. *Questions Are the Answer* (MIT Sloan) | Research | Question Burst technique |
| Toyota Production System | Methodology | 5 Whys root cause analysis |
| Bloom, B. (1956). *Taxonomy of Educational Objectives* | Academic | 6 levels of cognitive complexity |

## License

MIT
