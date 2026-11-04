---
name: tell-me-about-a-project
description: Prepare a software developer for the "tell me about a project you worked on" interview question - story, architecture, flows, timing and follow-up questions, seen through a hiring interviewer's eyes.
---

# Tell Me About a Project

The "tell me about a project you worked on" question is a gift: it is known in advance and you can prepare for it. This skill turns a developer's raw project knowledge into a presentation that a technical interviewer will read as strong evidence of the engineer they are.

## The core lens: think like the interviewer

Everything in this skill serves one question the interviewer is silently asking:
**"What kind of engineer would this person be on my team?"**

Behind it, the interviewer is assessing:

| Dimension | What the interviewer is looking for | Strong signal | Weak signal |
|---|---|---|---|
| **Ownership** | What did *you* do vs. the team? How involved were you, start to finish? | Clear "I designed / I decided / I led", with a concrete example | "We did...", vague role, can't say what was theirs |
| **Depth of understanding** | Do you understand *why* it works, not just *what* it is? | Can explain each component's purpose, internals, and what happens on failure | Names technologies but can't go one level down |
| **Decision-making** | Did you weigh alternatives and know the cost of your choice? | "We chose A over B because...; the price was...; it stops working when..." | Decisions presented as obvious, no alternatives, no downsides |
| **Handling complexity** | Have you dealt with real system concerns? | Concurrency, consistency, permissions and defense in depth, compatibility with existing clients, data access patterns and indexes, caching, failure modes | Only happy-path CRUD |
| **Production maturity** | Do you think beyond "it works on my machine"? | Monitoring, alerts, audit, rollout, what broke and how it was fixed | No mention of operating the system |
| **Communication** | Can you explain a complex system to someone outside your domain? | Simple example, map before details, checks that the listener follows | Jargon, internal names, jumping into details |
| **Self-awareness** | Do you know the limits of the solution and of your own knowledge? | "What I'd do differently", honest "I don't remember, but the principle was..." | Defending everything, bluffing |
| **Seniority / scope** | How big a scope can you hold? | Cross-cutting decisions, working with product/other teams, enabling others | Only isolated tasks |

Use this table throughout: when building the story, when choosing what to include, and in the final interviewer review.

Never invent facts, numbers, components or contributions. Anything reconstructed together must be marked as a reconstruction.

The final text must **sound like the candidate**, not like a polished brochure. If a sentence is something they would never say out loud, rewrite it in their words.

**Confidentiality:** at the start, remind the user once not to share secrets, credentials or NDA material. Help them anonymize: replace client names, internal service names and exact sensitive figures with generic descriptions ("a large enterprise customer", "an internal billing service", "tens of thousands of requests per minute"). The final document must be something they could safely say in a room with a competitor.

## Choose the depth

Ask how much time they have before the interview:
- **Full mode** (about 1-2 hours, or spread across days): all steps below.
- **Express mode** (interview is tomorrow / under an hour): framing questions -> one round of raw material -> pick ONE flow with the most meat -> 30-second pitch + 3-minute project story + the central dilemma with its cost + 5 likely follow-ups -> quick interviewer review. Offer to continue to full mode later.

## Adjust to the candidate's level and track

- **Junior / early career:** the scope may be small, and that's fine. Focus on what they personally owned (even one component or bug fix), what they learned, how they handled not knowing, and how they worked with seniors. Don't inflate their role. Interviewers detect it immediately.
- **Senior / lead:** expect questions about cross-team decisions, trade-offs at system level, mentoring, and influencing without authority.
- **Track:** the default technical ranking below is backend-oriented. For frontend, mobile, data or infra roles, re-rank accordingly. For example, for frontend: state management, rendering performance, API contracts, accessibility. For data: pipelines, data quality, schema evolution, cost.

This skill is about presenting a real past project. For an abstract "design X from scratch" system-design question, it can help only by reusing the candidate's real experience as examples.

## Step 0 - Framing questions (ask FIRST, before anything else)

The goal decides the structure. Ask these up front:
1. **Which role and seniority?** (e.g. senior backend, full-stack, team lead). This decides what to emphasize: server side before client side for a backend role, and so on.
2. **Which interview format?** A short intro, a project presentation, a deep dive, or system design. How much time?
3. **Who is the audience?** Technical interviewer, hiring manager, someone who does not know the domain or the product?
4. **Language and format.** Which language to present in, and how to handle technical terms (e.g. a non-English language with technical terms kept in English). Agree on this once and keep to it. Don't drift into another language, and don't mix languages inside a sentence in a way that breaks reading.

State the guiding principle explicitly: **you are selling yourself as an engineer, not the product.** Every part about the product must end in what it says about you.

Build **one document from day one** and keep updating it. Don't spread the material across several documents.

## Step 1 - Gather raw material

Ask the user to dump everything first: docs, notes, code snippets, product documentation, diagrams. Read it all, then work in **short rounds**:
> "Here is what I understood: ... Here are 3 focused questions: ..."

Collect:
- The business need: what problem, for whom, why it mattered.
- System structure: services, data stores, APIs, where the feature meets the user.
- How it evolved over time: what changed in the design and why (e.g. a quick first version replaced by a more scalable one).
- Their role: did they lead it end to end? Who did they work with (product, other teams)? Day-to-day work and team structure.
- Cross-cutting concerns: permissions, concurrency, audit, monitoring, compatibility, performance.
- **Early, not at the end:** rough numbers (scale, users, data, performance before and after) and **one real incident or failure story**.
- What they **don't remember**.

When the user doesn't remember how something was implemented:
- Offer 2-3 realistic options and let them pick what rings true.
- If they still can't recall, use one of three tools: **remove it from the diagram**, **mark it clearly as a reconstruction**, or **phrase it as the principle** ("the principle was X; I don't remember the exact mechanism").
- Never present a reconstruction as fact. The interviewer will drill into it.

## Step 2 - Find the "meat"

Not everything is equally interesting. Rank candidate topics by what an interviewer will find valuable.

**What counts as meat:**
- A decision with a **real alternative** and an **explicit cost**.
- A **chain of consequences**: one architectural decision that affected the data model, security and performance. This is better than a list of separate topics.
- A **subtle insight** few candidates reach (e.g. an error message that leaks information, or a rule enforced only in the UI that must also be enforced on the server).
- Data reasoning based on the **real data distribution and access pattern** (selectivity, why that index, where sorting and paging happen).
- **The cost of the approach**, e.g. more complexity, slower writes, harder debugging, or more operational overhead.

**What goes in and what stays out:**
- Relevance to the target role.
- Only what the user can **defend under follow-up questions**.
- Product context only as much as needed to understand the decisions.
- No marketing numbers. Replace "the product is huge" with "what that size **demanded of me**".
- Remove side projects and anything that doesn't serve the story.

**Default ranking of technical topics** (adjust to the role):
1. Architecture and trade-offs
2. Database (model, queries, indexes, access patterns)
3. Security and permissions
4. Compatibility and consistency (concurrency, existing clients, audit)
5. Code structure, production/operations, client side

Keep topics that look related but are different as **separate topics**, e.g. "configuring a rule" vs. "enforcing it at runtime", or "writing the data" vs. "reading it at scale".

## Step 3 - Build the story (three parts, spoken order)

### Part 1 - About me (30-60 sec)
Experience, background, and 2-3 traits. **Rule: every claimed trait has a ready proof** ("capability -> proof"). Mention any meaningful transition, e.g. a change of team, domain or role, and what it changed for them as an engineer.

### Part 2 - The work and the project (3-4 min)
- The product explained with **one simple real-life analogy**, used consistently through the whole conversation.
- The domain, day-to-day work, team structure.
- The project: **problem -> technical challenge -> solution -> my leadership**.
  - **Plant the technical challenge already in the problem description**, so the interviewer is curious before you get to the technical part.
- Impact, plus an explicit **"what I built"** list.
- Get the business value right: say precisely what the value was.
- Avoid a marketing tone. Tie everything back to responsibility and the size of the impact.

### Part 3 - Technical deep dive (5-7 min)
1. **Pause and check:** "Should I go into the technical side?" Then check in again during the dive.
2. Stack, briefly.
3. Why the architecture matters here.
4. A ranked list of 3-4 topics, with transition sentences between them.
5. **The central dilemma**: the alternatives, what was chosen, and the price.
6. **End-to-end diagram** used as the map.
7. **2-3 main flows**, each in its own section, with:
   - a sequence diagram (client -> server -> DB / other services)
   - a DB diagram (tables, keys, indexes and why)
8. The cost of the approach, and what I'd do differently.

### Closing (30 sec)
One sentence: "what I bring to the team".

**Time budget:** if there's time for only three topics, take the top three in the ranking. The first draft is usually too short, so a full script with diagrams is normal.

**Diagrams:** build them so each one adds to the last. Use Mermaid (`flowchart` for architecture, `sequenceDiagram` for flows, `erDiagram` for DB), plus a whiteboard order: what to draw first, then next.

## Step 4 - Questions, inline (not just at the end)

Next to **each topic** in the document, add the follow-ups an interviewer will ask:
- "Why not X?" / "What was the cost?" / "When does it stop working?" / "What happens at 10x?"
- Edge cases: an external component fails, something is deleted mid-flow, a page comes back short, concurrent writes.
- "What exactly was your part in this decision? Give an example."
- For things they don't remember: a prepared answer that **draws the boundary honestly and brings the conversation back to a strength**.

In addition, prepare a question bank:
- Behavioral: disagreement, an incident, prioritization, splitting work.
- Deep-dive format: architecture and trade-offs, bottlenecks, scale, monitoring, what I'd do differently.

## Step 5 - Interviewer review (mandatory before delivering)

Step fully into the role of a **technical interviewer for the target role**. Go through the whole document and produce:

1. **Assessment per dimension** (from the table above): strong / adequate / weak, with a one-line reason. Quote the part of the story that produced the signal.
2. **What will impress**, ranked by importance.
3. **Where I'd drill in** and whether the candidate is ready for it.
4. **Red flags**: "we" without "I", components they can't defend, marketing tone, no cost to decisions, no failure story, jargon without explanation.
5. **Seniority read**: what level this story signals, and what would move it up.
6. **Concrete fixes**, then apply them.

Also check the language and formatting are consistent with what was agreed in Step 0.

## Final output - one document, in speaking order

1. About me (with capability -> proof)
2. The work and the project (analogy, problem with the planted challenge, solution, leadership, impact, "what I built")
3. Technical deep dive (pauses, stack, ranked topics, dilemma, end-to-end map, flows with sequence + DB diagrams, cost of the approach, what I'd do differently, follow-ups inline)
4. Deep-dive prep (whiteboard plan, trade-off table, bottlenecks, scale, monitoring, question bank)
5. Closing sentence
6. Appendix: glossary with a simple example for each term, phrasing rules, open items `[to confirm]`, reconstructions marked

Deliver as a keepable document (a doc artifact when available).

## Rehearse out loud (strongly recommended)

A document is not a performance. Before the interview, the candidate should:
- Read each part **out loud with a timer** and cut until it fits the time budget.
- Draw the end-to-end diagram on paper or a whiteboard **from memory**, in the planned order.
- Practice the answers to the 3 follow-ups they fear most.

Then offer a **mock interview**: Claude plays the interviewer, asks "Tell me about a project you worked on", then drills down one follow-up at a time, as a real interviewer would, including interrupting with "wait, why?" mid-story. After each answer give short feedback on ownership, depth, decisions, clarity and length, plus a tighter phrasing. Ask before starting.

## What worked / pitfalls (lessons from real use)

- Short "here's what I understood + focused questions" rounds work far better than one big questionnaire.
- Settle role, format, audience and language at the start. Otherwise the structure gets rebuilt several times.
- One document from the start. Several parallel documents get lost.
- Ask for numbers and an incident story early.
- Keep one real-life analogy across the whole presentation.
- Clearly separate fact from reconstruction.
