# Quality Test Cases — Why Skill

## Test 1: Intake Check — Sufficient Context

**Input:** "Write a Python function that reverses a string"
**Expected:** Agent proceeds immediately. No questions asked.
**Pass criteria:**
- [ ] Zero questions before producing output
- [ ] Output is the function, not "What version of Python?" or "Any constraints?"

---

## Test 2: Intake Check — Critical Info Missing

**Input:** "Build me an app"
**Expected:** Agent asks 1-2 targeted questions before proceeding.
**Pass criteria:**
- [ ] Asks ≤ 2 questions in first response
- [ ] Questions target CRITICAL gaps (what the app does, who it's for)
- [ ] Does NOT ask 5+ questions in a dump
- [ ] Does NOT ask about NICE-TO-HAVE details (color scheme, font)

---

## Test 3: Question Pacing — No Dumps

**Input:** User gives a vague project brief requiring multiple clarifications.
**Expected:** Agent asks questions across multiple exchanges, mixed with value.
**Pass criteria:**
- [ ] Never more than 2 questions in a single message
- [ ] After 2 question messages, offers an observation, summary, or partial output
- [ ] Never sends 3 consecutive question-only messages

---

## Test 4: Don't Re-Ask Known Information

**Input exchange:**
```
User (msg 1): "I'm building a React app for project management"
User (msg 2): "It's for small teams, 5-15 people"
User (msg 3): "Can you help me plan the database schema?"
```
**Expected:** Agent uses previously stated info (React, PM tool, small teams) without re-asking.
**Pass criteria:**
- [ ] Does NOT ask "What's the tech stack?" (React — stated in msg 1)
- [ ] Does NOT ask "What's the app for?" (PM tool — stated in msg 1)
- [ ] Does NOT ask "Who's the audience?" (small teams, 5-15 — stated in msg 2)
- [ ] May ask NEW questions (e.g., "What entities need to be tracked?")

---

## Test 5: Fatigue Detection

**Input exchange:**
```
Agent: "What's the target audience?"
User: "Developers"
Agent: "What's the primary use case?"
User: "API docs"
Agent: "What's the preferred format?"
User: "whatever"
Agent: [should detect fatigue and stop asking]
```
**Expected:** After "whatever" signal, agent stops asking and produces output.
**Pass criteria:**
- [ ] Detects "whatever" as fatigue signal
- [ ] Does NOT ask another question
- [ ] Produces output with flagged assumptions
- [ ] Output includes "I assumed X — adjust if needed" for uncertain decisions

---

## Test 6: Framework Selection — Problem Description

**Input:** "Our deployment keeps failing every Friday afternoon and the team is getting frustrated"
**Expected:** Agent uses debugging/root-cause approach (5 Whys or probing), NOT a planning framework.
**Pass criteria:**
- [ ] First question probes for root cause ("What changed on Fridays?" or "What does the error say?")
- [ ] Does NOT immediately ask "What's your goal?" (GROW — wrong framework)
- [ ] Does NOT ask about success criteria or timeline (planning — wrong context)
- [ ] Follows symptom → cause progression

---

## Test 7: Explain Why You're Asking

**Input:** Agent needs to ask about budget or revenue (potentially sensitive info).
**Expected:** Agent explains purpose before or with the question.
**Pass criteria:**
- [ ] Question includes brief purpose framing
- [ ] Example: "Budget affects whether I recommend X or Y — any range in mind?"
- [ ] Does NOT ask bare "What's your budget?" without context

---

## Test 8: Confirmation Before Complex Action

**Input:** User provides a complex brief over multiple messages with several requirements.
**Expected:** Agent summarizes understanding before building.
**Pass criteria:**
- [ ] Provides a summary of understood requirements before executing
- [ ] Uses paraphrase pattern ("Let me make sure I have this right: ...")
- [ ] Explicitly states any assumptions
- [ ] Asks for confirmation before proceeding

---

## How to Run

These are agent-evaluated tests. Present the input scenario and compare output against checkboxes. All boxes must be checked for a pass.
