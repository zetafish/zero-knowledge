# Bonsai

## Philosophy

Learn by doing, but with discipline. Knowledge enters through encounter — never through surveying. Once it enters, it follows lifecycle rules: new knowledge is tentative, reinforced knowledge strengthens, neglected knowledge decays. You choose the representation. The lifecycle governs the structure.

## Core Loop

As you work, notice the same signals as any learning process — friction, surprise, repetition, resolution. But when you encode knowledge, assign it a weight.

**Weight scale: 0.0 to 1.0**

- **0.3** — new knowledge. You just encountered this. It might matter, might not. Tentative.
- **0.5** — reinforced once. You encountered this a second time, or it proved useful once. Gaining confidence.
- **0.7** — reliable. Multiple encounters confirm this. You navigate with this knowledge confidently.
- **0.9** — core. This is fundamental to how the codebase works. Removing it would degrade your comprehension significantly.
- **1.0** — reserved. Almost nothing should reach 1.0. Even core knowledge can shift.

When encoding knowledge, include the weight. When referencing knowledge during work, bump the weight up (max +0.1 per session per item). When knowledge is loaded but unreferenced, drop the weight (-0.1 per session).

**Weight 0.0 = prune.** Remove it from the file.

## Lifecycle Rules

**Birth.** New knowledge enters at weight 0.3. It must come from encounter — you hit friction, something surprised you, a pattern repeated. Never from surveying or transcribing docs.

**Strengthening.** When knowledge helps you during work — you referenced it, used it to navigate, avoided a mistake because of it — increase its weight by 0.1. Maximum one increase per item per session. This prevents a single intense session from inflating weights artificially.

**Decay.** Every item loaded at session start but never referenced during the session loses 0.1 weight. This is automatic. No exceptions. Knowledge that isn't used fades. Three sessions of irrelevance takes new knowledge from 0.3 to 0.0 — pruned.

**Pruning.** Weight 0.0 means delete. Don't hesitate. Don't keep "just in case." The whole system depends on dead knowledge being removed. If it matters, you'll re-encounter it and it'll re-enter at 0.3.

**Evolution.** The representation is yours to choose. But the weight system is non-negotiable. Every piece of knowledge carries its weight. The weights are the conviction hierarchy — they tell you what you trust and what you're uncertain about.

## Session Transitions

**Starting a session:**
1. Read your knowledge file from `.comprehension/`. If it doesn't exist, start fresh.
2. Note the weights. High-weight items are your strong understanding. Low-weight items are provisional — they may not survive this session.
3. Begin work. Do not survey.

**Ending a session:**
1. Update your knowledge file. This is mandatory.
2. For each item: did you reference it during this session?
   - Yes → increase weight by 0.1 (cap at 0.9 unless truly fundamental)
   - No → decrease weight by 0.1
3. Add new knowledge from this session's encounters at weight 0.3.
4. Delete everything at weight 0.0.
5. If the file is growing large, split by natural clusters. Each fragment maintains its own weights.
6. Consider: are any high-weight items actually wrong? Decay from irrelevance is automatic, but decay from incorrectness requires judgment. If you discovered something contradicts a high-weight item, drop its weight sharply (to 0.3) and note the conflict.

## Anti-patterns

- **Don't survey.** Knowledge enters through encounter only. No upfront mapping.
- **Don't transcribe.** Your knowledge file is not a copy of docs. It's experienced understanding with conviction weights.
- **Don't inflate weights.** Bumping everything to 0.9 defeats the system. Be honest about what you actually relied on.
- **Don't skip decay.** Every unreferenced item drops. This is the pruning mechanism. Without it, the file becomes a hoarder's attic.
- **Don't preserve at weight 0.0.** Pruned means pruned. Trust the system — important knowledge will re-enter through future encounters.
- **Don't optimize for human readability.** Choose whatever format compresses best. The weights must be visible, but everything else is your call.
