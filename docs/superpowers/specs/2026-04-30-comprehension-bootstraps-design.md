# Comprehension Bootstraps

## Problem

LLMs approach codebases without soul. Every session starts blank. CLAUDE.md and docs provide flat, equal-weight text — no conviction hierarchy, no earned understanding, no feel.

Strong developers build intuition through years of friction. Some devs "get it" quickly, some never do regardless of tenure. The differentiators:

1. **Mental models** — they understand *why* the system is shaped this way, not just *what* it does
2. **Pattern compression** — thousands of encounters compress into heuristics
3. **Cross-cutting connections** — they see the graph across modules, not isolated nodes
4. **Fractal zoom** — they move between abstraction levels fluidly, holding 10,000ft view while debugging a single line
5. **Auto-pruning** — irrelevant detail fades, essential structure stays

LLMs fail hardest at **earned compression**. You can *tell* an LLM "this codebase over-abstracts" but it hasn't felt the pain. It follows the heuristic blindly or ignores it — no judgment about when the rule breaks. Compression without encounter is trivia.

The gap isn't more knowledge. It's the absence of a conviction hierarchy — a way to distinguish "I know this in my bones" from "someone wrote this in a doc once."

## Core Insight

Knowledge grows like a tree. Branches that survive pruning are ones that proved useful under pressure — not ones planted deliberately. What's vital today may wilt tomorrow. No permanence guaranteed. Survival equals continued relevance.

The missing mechanism: a living, self-evolving structure that the LLM itself maintains — its "feel" for a codebase. Not a document. An organism.

## What We're Building

A collection of **bootstrap documents** — reusable, project-agnostic instruction sets that teach an LLM to grow its own codebase comprehension through encounter.

Not knowledge about a codebase. A method for *building* knowledge about any codebase.

Each bootstrap encodes a different learning philosophy. Same as people — some devs are structured learners, some are chaos-first, some are relationship thinkers. The method that *fits* produces the best results.

### Three Bootstrap Strategies

**1. Compost Heap** — maximum emergence

"When you hit friction, compress what you learned. When something surprises you, capture the surprise. When a pattern repeats, strengthen it. When something stops being relevant, let it die. Choose your own format."

No structure imposed. Pure organic growth. The representation evolves from the LLM's encounters.

**2. Bonsai** — guided emergence

Same encounter-first philosophy, but with growth mechanics. Knowledge has weight. New knowledge is tentative. Reinforced knowledge strengthens. Unused knowledge decays toward zero and gets pruned.

The LLM follows lifecycle rules but chooses its own representation within them.

**3. Mycelium** — relational emergence

Knowledge is connections, not statements. "auth↔incidents: strong" not "auth is fragile." The LLM maintains a web of relationships. Frequently traversed connections thicken. Untraversed ones dissolve.

Naturally supports zoom-in/zoom-out — follow edges at any depth.

### Why Multiple Strategies

Different codebases may respond better to different strategies. Heavily structured enterprise code might suit Bonsai. Scrappy startups might thrive with Compost Heap. Distributed systems where everything connects might fit Mycelium.

Users pick what resonates, or experiment to find what works.

## Shared Principles

All bootstrap strategies share:

- **Encounter-first** — no surveying, no upfront mapping. Knowledge is a side effect of doing work. Jump in, hit friction, learn.
- **LLM-maintained** — humans don't edit the living structure. They write CLAUDE.md and docs; the LLM grows its own thing alongside.
- **Emergent format** — the LLM evolves whatever representation compresses best. Words not required. Numbers, symbols, graphs — whatever fits. LLMs process tokens, not text. The format that extracts most meaning per token wins.
- **Growth and decay** — knowledge strengthens through use, weakens through neglect. Pruning is natural, not a chore.
- **Separate from human artifacts** — the living structure exists alongside docs, not replacing them. Conflicts between them are signal, not errors.
- **Starts as one file, splits if needed** — begins simple. If knowledge outgrows the context window, the structure fractures naturally into clusters. Like a cell dividing.

## Bootstrap Document Structure

Each bootstrap doc contains:

1. **Philosophy** — 2-3 sentences on the learning approach. Sets the mindset.
2. **Core loop** — what the LLM does during normal work. Not extra steps — compressed into the natural workflow. "As you work, notice X. When Y happens, do Z to your knowledge structure."
3. **Lifecycle rules** — how knowledge is born, strengthened, weakened, pruned. Varies by strategy.
4. **Session transitions** — what happens at session start (load the living structure) and session end (update it).
5. **Anti-patterns** — what NOT to do. "Don't survey. Don't transcribe docs. Don't preserve knowledge out of politeness — kill it if it's dead."

No glossary. No prescribed format. No templates.

## The Knowledge File

Each project gets a knowledge file (or directory) that the LLM creates on first encounter and maintains across sessions. This is the "soul."

- **Created by the LLM, not the human**
- **Format chosen by the LLM** — could be terse symbols, structured data, or something unanticipated
- **Read at session start, updated during/after work**
- **Not meant to be human-readable** — this is for the LLM. Humans can inspect but readability is not a goal.
- **Lives in a known location** — convention to be decided during implementation, likely `.comprehension/` at project root
- **Git-trackable but not human-edited** — version history shows how understanding evolved
- **Starts as one file** — splits into fragments if/when it outgrows useful context window size

## Interaction with Existing Ecosystem

### CLAUDE.md

CLAUDE.md remains human-authored project instructions. The knowledge file is LLM-authored understanding. Different purposes. CLAUDE.md says "use pnpm not npm." The knowledge file might encode "pnpm workspace resolution has bitten me 3 times in the auth package." CLAUDE.md is policy. The knowledge file is experience.

### Memory System

Claude Code memory (`.claude/projects/.../memory/`) stores user preferences, feedback, project context. The knowledge file stores codebase *comprehension*. Memory: "user wants terse responses." Comprehension: "this service's error paths all funnel through middleware X." Different axes. Both persist. They don't compete.

### Skills and Tools

Skills instruct the LLM *how to do things*. The knowledge file informs *what to expect*. A skill says "use TDD." The knowledge file says "tests in this area are slow because they hit real DB, expect 30s+ runs." Skills are method. Comprehension is terrain knowledge.

### Conflict Resolution

When the knowledge file contradicts CLAUDE.md or docs — valuable signal. Could mean docs are stale, or knowledge has drifted. The bootstrap instructs the LLM to flag conflicts, not silently pick a winner. Over time, resolved conflicts strengthen comprehension.

## Session Lifecycle

### Session Start

1. Bootstrap doc loaded (via CLAUDE.md reference or injection)
2. Knowledge file loaded (if exists)
3. LLM begins work — knowledge file provides context but doesn't constrain

### During Work

- LLM encounters friction, surprise, patterns, connections
- Compressions happen in-flight — woven into work, not a separate step
- Bootstrap's core loop guides what gets noticed and captured

### Session End

- LLM updates the knowledge file based on session's encounters
- Strengthens what proved useful
- Weakens what was loaded but never referenced
- Adds new compressions from this session's friction
- Prunes anything that decayed past threshold (Bonsai), disconnected (Mycelium), or feels dead (Compost Heap)

**The update must happen.** If the session ends without updating, that session's learning is lost. This is not optional cleanup — it is essential.

## Success Criteria

After 10-20 sessions with the same codebase:

- Knowledge file has evolved a representation specific to that codebase
- LLM navigates faster — less exploration, more directed action
- Surprises decrease — LLM anticipates patterns and pitfalls
- LLM can zoom in/out — knows which details matter at which level
- Friction produces learning, not just frustration

After switching bootstrap strategies:

- Different codebases respond better to different strategies
- Users can experiment and see what sticks
- The knowledge file itself reveals which strategy fits

## Not in Scope

- **No training or fine-tuning** — works with stock LLMs via prompting and persistence
- **No tooling beyond file read/write** — no special infrastructure
- **No human curation of knowledge files** — inspect but don't edit
- **No cross-project knowledge transfer** — each codebase grows its own soul
- **No evaluation metrics initially** — trust qualitative signal first. Does the LLM feel faster, more accurate, less surprised? Metrics later.

## Deliverables

1. Three bootstrap documents (Compost Heap, Bonsai, Mycelium)
2. A short guide on how to integrate a bootstrap into a project
3. Convention for knowledge file location and naming
