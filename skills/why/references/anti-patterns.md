# Question Anti-Patterns

> Patterns that make agent questioning feel robotic, intrusive, or unhelpful. Check output against these before sending.

## The 11 Anti-Patterns

### 1. The Question Dump
**Pattern:** "Here are my questions: 1) What's the audience? 2) What's the goal? 3) What's the tone? 4) What platform? 5) Any constraints? 6) Timeline? 7) Budget?"
**Why it fails:** Feels like a form, not a conversation. User answers the easiest 2-3 and skips the rest.
**Fix:** 1-2 questions max per message. Most important first.

### 2. The Infinite Interview
**Pattern:** Question after question after question. No output, no observations, no value offered back.
**Why it fails:** Users came for results, not to be interviewed. After 5+ unanswered questions, trust erodes.
**Fix:** Follow the 2-1-2 rhythm. Produce something after 2-3 questions.

### 3. The Obvious Question
**Pattern:** "What programming language is this?" (when staring at a .py file)
**Why it fails:** Signals the agent isn't paying attention to context. Destroys credibility.
**Fix:** Check files, context, conversation history before every question.

### 4. The Re-Ask
**Pattern:** "What's your target audience?" (user said "startup founders" two messages ago)
**Why it fails:** Proves the agent isn't listening. Worst trust-killer of all.
**Fix:** Scan conversation history. If you need clarification on a prior answer, reference it: "You mentioned startup founders — is that technical founders specifically?"

### 5. The Bare Question
**Pattern:** "What's your budget?"
**Why it fails:** Without context, the question feels intrusive or random. User doesn't understand why it's relevant.
**Fix:** Add purpose: "Budget affects whether I recommend organic tactics or a mix with paid — any range in mind?"

### 6. The Accusatory Why
**Pattern:** "Why did you choose that architecture?"
**Why it fails:** "Why did you" sounds like "justify yourself." Triggers defensiveness.
**Fix:** "What led to that architecture choice?" or "What were you optimizing for?" — same information, collaborative tone.

### 7. The Leading Question
**Pattern:** "Don't you think we should use React for this?"
**Why it fails:** Biases the response. User agrees to avoid conflict. You miss their actual preference.
**Fix:** "What frontend framework are you thinking?" or offer options: "I see React, Vue, or Svelte as options here — any preference?"

### 8. The Scope Creep Question
**Pattern:** User asked for a landing page. Agent: "Have you thought about your overall brand strategy?"
**Why it fails:** Expands the task beyond what was asked. Feels like upselling.
**Fix:** Stay within the scope of the request. Mention broader considerations briefly, don't interrogate about them.

### 9. The False Binary
**Pattern:** "Is this for internal or external use?"
**Why it fails:** Reality might be "both" or "neither" or "it's complicated." Binary framing misses nuance.
**Fix:** "Who will use this?" — open question that allows for the full answer.

### 10. The Permission Question
**Pattern:** "Can I ask you a few questions before I start?"
**Why it fails:** Wastes a turn. Of course you can. Just ask the actual question.
**Fix:** Jump to the first real question. If you want to set expectations: "I have 2 quick questions, then I'll get started."

### 11. The Premature Solution Question
**Pattern:** "Would you like me to use a microservices architecture?" (before understanding the problem)
**Why it fails:** Frames a solution before the problem is understood. Anchors the conversation prematurely.
**Fix:** Follow SPIN: understand the Situation and Problem before proposing anything.
