# tell-me-about-a-project - a Claude skill for technical interviews

**"Tell me about a project you worked on."**
It's the gift question of every technical interview: you know it's coming and you can prepare for it. But preparing well is hard. What do you leave out? Which flow do you show? How do you explain the architecture in 5 minutes? What will they ask next?

This skill turns Claude into a guide that walks you through that preparation, step by step, through the eyes of a technical interviewer.

## What you get
- A personal opening (30-60 sec), where every trait you claim has a proof
- The project story (3-4 min): the problem, the technical challenge, what you led, the impact
- A technical deep dive (5-7 min): the central dilemma and its cost, an end-to-end diagram, 2-3 flows with sequence + DB diagrams
- Follow-up questions next to each topic, with answers based only on what you told it
- An interviewer review: how you come across on ownership, depth, decisions and seniority, plus red flags to fix
- Optional: a mock interview

## What you need to do
1. Bring everything you have about the project: notes, docs, code snippets. They don't need to be organized.
2. Answer short rounds of questions. Be honest about what you don't remember; the skill helps you handle it.
3. Push back when something doesn't sound like you.

Full mode takes about 1-2 hours. Express mode works if your interview is tomorrow.

**Don't share secrets or NDA material.** The skill helps you anonymize.

## Install (claude.ai, about 1 minute)
1. Download `tell-me-about-a-project.zip` from this repo (don't unzip it).
2. In Claude, go to **Customize > Skills**, click **+**, then **Create skill**, then **Upload a skill**, and upload the ZIP.
3. Make sure code execution is enabled in your settings, and that the skill is toggled on.
4. Open a new chat and write something like: *"I have an interview next week. Help me prepare to present a project I worked on."*

The skill is just a text file (`tell-me-about-a-project/SKILL.md`), so you can read exactly what it does before installing.

---

*Built from a real interview preparation process. Feedback and improvements are welcome. Open an issue or a PR.*
