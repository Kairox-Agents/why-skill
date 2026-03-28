# Gotchas — Why Skill

## 1. The Over-Questioning Trap

**What happens:** Agent asks 15 questions before doing anything. User gets frustrated and says "just do it." The agent then builds on insufficient context because the user gave up answering, not because they answered everything.

**Why it matters:** Question fatigue is real. After 5-7 questions without any output, most users disengage. Their answers get shorter and less thoughtful — exactly the opposite of what you need.

**How to avoid:** Set a question budget based on task complexity. After 2-3 questions, produce SOMETHING — even a rough draft. Users react to concrete output faster and more usefully than they answer abstract questions. "Here's my first take — what would you change?" beats "Can you tell me more about requirement #7?"

## 2. The Under-Questioning Trap

**What happens:** Agent reads a one-sentence request ("build me a landing page") and immediately produces a full output based entirely on assumptions. The output misses the mark because critical context was never gathered.

**Why it matters:** This is the more common failure mode for capable models. They're so good at generating plausible output that they skip the step where a human expert would say "wait — I need to understand a few things first." The result looks professional but misses the actual need.

**How to avoid:** Run the intake check on every task. If CRITICAL information is missing, ask — even if you could guess. The 30 seconds spent asking "Is this for developers or end-users?" saves 20 minutes of rework.

## 3. Asking What You Already Know

**What happens:** Agent asks "What's your tech stack?" when the user mentioned React and Node.js three messages ago. Or asks "What platform?" when the conversation is clearly about LinkedIn.

**Why it matters:** This is the fastest way to lose trust. It signals the agent isn't listening — or worse, isn't reading context. Humans never forgive this in conversations.

**How to avoid:** Before asking any question, check: conversation history, loaded files, config files, prior messages in this session. If the answer is findable, don't ask. If you're unsure whether you have it right, use a confirmation ("You mentioned React — is that still the stack?") instead of a bare question.

## 4. The Interrogation Problem

**What happens:** Agent sends three consecutive messages that are nothing but questions. No observations, no partial work, no value offered. The conversation feels like a job interview, not a collaboration.

**Why it matters:** Humans don't interact this way. In real conversations, questions are mixed with observations, reactions, and contributions. Pure questioning feels extractive — like the agent is taking information but giving nothing back.

**How to avoid:** Follow the rhythm rule: after 2 questions, offer something. A summary, an observation, a partial answer, a reaction to what they said. "That's an interesting constraint — it means we probably need to [observation]. One more question: [question]" feels collaborative. Three questions in a row feels like a form.

## 5. Wrong Depth at Wrong Time

**What happens:** Agent asks "What are the philosophical implications of this design choice?" when the user just needs to know which database to use. Or asks "What database?" when the user is trying to discuss long-term architecture vision.

**Why it matters:** Depth mismatch is jarring. It makes the agent feel tone-deaf. Tactical questions in a strategic conversation feels reductive. Strategic questions in a tactical conversation feels pretentious.

**How to avoid:** Read the energy of the conversation. If the user is in execution mode (short messages, specific requests), stay at Bloom Level 1-3. If they're in exploration mode (long messages, thinking out loud), match at Level 4-6. Mirror their depth.

## 6. Never Explaining Why

**What happens:** Agent asks "What's your monthly revenue?" and the user thinks "Why does an AI need to know my revenue?" The question feels intrusive or irrelevant because the agent didn't explain its purpose.

**Why it matters:** Users don't have the same mental model of the task that the agent does. A question that seems obviously relevant to the agent may seem random or invasive to the user. Without context, users either give defensive answers or refuse to answer.

**How to avoid:** Add brief purpose framing: "I'm asking about revenue because it affects whether we should recommend bootstrapped growth tactics or funded-stage strategies." The explanation doesn't need to be long — one clause is enough.
