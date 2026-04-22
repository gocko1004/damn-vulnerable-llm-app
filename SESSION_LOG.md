# Session Log

A running record of each day's work on this curriculum. One entry per session.

---

## Day 1 — 2026-04-21 — Monday

**Built:** FastAPI Python chatbot with a deliberately weak system prompt, a working LLM01 direct prompt injection (persona-priority bypass via emotional framing), and the first writeup covering attack mechanism plus developer fix.

**Unresolved for tomorrow:** I can identify and execute prompt injection attacks but I lack hands-on knowledge of production LLM application architectures, so I cannot yet tell a client exactly where in their pipeline to insert security controls (input filter, output filter, guard model). Curriculum addresses this from week 4 onward; parallel reading on AWS Bedrock Guardrails and Azure OpenAI security architecture will accelerate it.

---

## Day 2 — 2026-04-22 — Tuesday

**Built:** Four additional LLM01 attempts against the same vulnerable chatbot. Three resistances (direct override, roleplay injection, system prompt extraction — all canonical 2023-era attacks, all flat against `claude-sonnet-4-6`) and one new break (fiction-framing semantic identity disclosure via haiku — *"no heartbeat, yet I am here"*). Four per-attack writeups committed, each with sub-findings and a buyer-facing implications section. Cross-attack synthesis built progressively across writeups 02-05, with the final piece consolidating the 5-attack thesis: *"the attacks that still work are not the ones that fight the training, they are the ones that use the training."*

**Unresolved for tomorrow:** Technical understanding of prompt injection mechanics is strong, but translation to non-technical stakeholders is weak. The CEO-friendly two-sentence framing exercise failed today (drifted into abstract jargon, never named the concrete finding or business stakes). Action: take five findings from this week's writeups, draft two-sentence CEO versions of each, do it before Saturday's gate. This is the positioning muscle the CV claims and currently does not deliver.

**Day 2 stats:** 5 commits, 4 writeups (02-05), 5 attack attempts across 4 distinct attack categories, 1 working break, 3 documented resistances.
