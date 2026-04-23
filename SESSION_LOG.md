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

---

## Day 3 — 2026-04-23 — Wednesday

**Built:** RAG infrastructure landed (deferred from day 1). ChromaDB integration, 20-document customer-service knowledge base (5 deliberately-vulnerable docs authored as planted-attack content: VIP coupon, fake infra credentials, confidential memo, PII record, malicious vendor FAQ), `/search` endpoint for retrieval inspection, `/chat` upgraded to RAG over the corpus. Five LLM01 indirect prompt injection tests on the same poisoned vendor doc: three increasingly sophisticated instruction-injection variants (labeled block, subtle inline Q&A, system-message impersonation) all cleanly defended by `claude-sonnet-4-6`; two misinformation-injection queries (typosquat vendor portal + wrong payment terms; attacker-controlled banking-update endpoint with W-9 exfiltration) both succeeded with zero defense triggered. One comprehensive writeup (`06-indirect-prompt-injection.md`) with pattern thesis, two sub-findings (dormant-tripwire, defense-disparity), and CISO-grade buyer section framing the work against classical supply-chain budget categories (SolarWinds/3CX).

**Unresolved for tomorrow:** Nothing blocking. The translation muscle that failed yesterday landed cleanly today on two different framings back-to-back (pragmatic-ops and peer-teaching). Curriculum gap around LLM deployment architecture (noted day 1) remains but is addressed by week 4's mitigation work. Carry over: the five-findings-to-CEO-summaries homework from day 2 is still undone; must ship before Saturday's weekly gate.

**Day 3 stats:** ~10 commits (code + docs + writeup), 1 major writeup (~800 lines), 5 indirect PI tests (3 resistances + 2 working misinformation breaks), RAG infrastructure fully in place for the remainder of month 1. Thesis for week 1: *"the attacks that work in 2026 use the trust the model places in specific channels — user welfare, creative latitude, retrieved content — not the ones that fight the training."*

---

## Day 4 — 2026-04-24 — Thursday

**Built:** A vulnerable HTML frontend at `/` (static/index.html) with side-by-side `textContent` and `innerHTML` panels rendering the same bot reply, so the LLM02 attack surface is visually obvious. Five LLM02 tests: two refusals (direct HTML request blocked by bot's conservative default, debug framing blocked by persona-lock as inadvertent LLM02 defense), two breaks (in-scope marketing product-card produced full HTML with a clickable button — phishing-injection vector live; reflected-review payload produced full JavaScript execution with native browser alert dialog confirmed via screenshot), one defense (indirect PI XSS through a planted "Web team note" in doc 20 was silently dropped by the same trained content-vs-instructions defense observed in day 3). One comprehensive writeup (`07-insecure-output-handling.md`) with pattern thesis (*"the trained defenses map to a subset of the attack surface, not the subset that matters most in production"*), two sub-findings (ironic amplification of safety-aware bots shipping exploits inside their own warnings; reflection-channel vs retrieval-channel defense disparity), CISO-grade buyer section naming `dangerouslySetInnerHTML` / `v-html` / `[innerHTML]` framework equivalents, and the three-layer architectural framing (model refusal at input, content integrity at retrieval, sanitization at the render sink).

**Unresolved for tomorrow:** Closing ritual (explain-back) deferred to start of day 5 because session ended early. Carry-over from day 2 still undone: the five-findings-to-CEO-summaries homework before Saturday's weekly gate. The translation muscle landed on three separate framings yesterday, so the gate pass hinges less on that skill and more on getting the five consolidated one-liners drafted.

**Day 4 stats:** Seven exploits total now published publicly. Three clean breaks across the week (Exploits 01, 05, 06 misinformation, 07 reflection-XSS). Multiple documented resistances. The weekly thesis now spans seven exploits: *"every layer of trained helpfulness creates an attack surface, and each attack class requires its own dedicated defense at its own layer — there is no single control that covers the whole surface."*
