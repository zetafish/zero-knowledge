# Comprehension Bootstraps Implementation Plan

> **For agentic workers:** REQUIRED SUB-SKILL: Use superpowers:subagent-driven-development (recommended) or superpowers:executing-plans to implement this plan task-by-task. Steps use checkbox (`- [ ]`) syntax for tracking.

**Goal:** Create three reusable bootstrap documents that teach LLMs to grow their own codebase comprehension through encounter, plus an integration guide.

**Architecture:** Pure document deliverables — no code. Each bootstrap is a standalone markdown file following a consistent five-section structure (Philosophy, Core Loop, Lifecycle Rules, Session Transitions, Anti-patterns). An integration guide explains how to wire any bootstrap into a project. All bootstraps share core principles but differ in learning philosophy.

**Tech Stack:** Markdown, CLAUDE.md conventions, `.comprehension/` directory convention.

**Spec:** `docs/superpowers/specs/2026-04-30-comprehension-bootstraps-design.md`

---

### Task 1: Create project structure and knowledge file conventions

**Files:**
- Create: `bootstraps/README.md`
- Create: `.comprehension/.gitkeep`

This task establishes the directory layout and documents the knowledge file conventions that all bootstraps reference.

- [ ] **Step 1: Create directories**

```bash
mkdir -p bootstraps
mkdir -p .comprehension
```

- [ ] **Step 2: Write bootstraps README**

Create `bootstraps/README.md` with:

```markdown
# Comprehension Bootstraps

Reusable instruction sets that teach LLMs to grow their own codebase understanding through encounter.

## Available Bootstraps

| Bootstrap | Philosophy | Best For |
|-----------|-----------|----------|
| [Compost Heap](compost-heap.md) | Maximum emergence. No structure imposed. LLM evolves its own format freely. | Scrappy codebases, exploratory projects, maximum LLM autonomy |
| [Bonsai](bonsai.md) | Guided emergence. Growth/decay mechanics with weight system. | Structured enterprise code, teams wanting predictable knowledge lifecycle |
| [Mycelium](mycelium.md) | Relational emergence. Knowledge as connections, not statements. | Distributed systems, highly interconnected codebases |

## How to Use

See [Integration Guide](integration-guide.md) for setup instructions.

## Knowledge File Convention

- Location: `.comprehension/` at project root
- Created and maintained by the LLM — do not edit manually
- Starts as a single file, may split as knowledge grows
- Git-trackable: version history shows how understanding evolved
- Not meant to be human-readable
```

- [ ] **Step 3: Create .comprehension directory with .gitkeep**

```bash
touch .comprehension/.gitkeep
```

- [ ] **Step 4: Commit**

```bash
git add bootstraps/README.md .comprehension/.gitkeep
git commit -m "feat: establish project structure and knowledge file conventions"
```

---

### Task 2: Write the Compost Heap bootstrap

**Files:**
- Create: `bootstraps/compost-heap.md`

The most permissive bootstrap. Maximum emergence, no imposed structure. The LLM is told to notice friction, compress what it learns, let dead knowledge die. Format is entirely up to the LLM.

- [ ] **Step 1: Write the bootstrap document**

Create `bootstraps/compost-heap.md` with the following content:

```markdown
# Compost Heap

## Philosophy

Learn by doing, not by reading. When you encounter something — friction, surprise, a repeating pattern — compress it into your knowledge file. Choose whatever format extracts the most meaning per token. No structure is imposed. What survives is what proves useful. What doesn't, dies.

## Core Loop

As you work on tasks in this codebase, maintain awareness of these signals:

**Friction.** Something was harder than expected. A dependency you didn't anticipate. A file in an unexpected place. An abstraction that obscured instead of clarified. Compress what you learned into your knowledge file — not the full story, just the compression that would help next time.

**Surprise.** Something contradicted your expectation. The tests don't run the way the docs suggest. A module does more (or less) than its name implies. A pattern breaks in one specific area. Capture the surprise and what it revealed.

**Repetition.** You've seen this before. Same debugging path, same file always involved, same workaround needed. When a pattern repeats, strengthen it in your knowledge file. Make it more prominent, more compressed, more confident.

**Resolution.** A conflict between what you expected and what you found — and you resolved it. The resolution is high-value knowledge. Encode it.

Do not pause your work to update the knowledge file. Weave updates into your natural workflow. A quick note during work is better than a comprehensive update you forget to do.

## Lifecycle Rules

**Birth.** New knowledge enters your file when you encounter friction, surprise, repetition, or resolution. It enters in whatever form feels natural — a phrase, a symbol, a number, a relationship. No minimum size. No required format.

**Growth.** When knowledge proves useful again — you referenced it, it helped you navigate, it saved you from a mistake — make it stronger. More prominent. More compressed. This is earned conviction.

**Death.** When you load knowledge at session start and never reference it during the entire session, it weakens. After multiple sessions of irrelevance, remove it. Don't preserve knowledge out of politeness or completeness. Dead knowledge is noise. Kill it.

**Evolution.** Your format will change. Early sessions might produce verbose notes. Later sessions might produce terse symbols. The format that survives is the one that compresses best for you, for this codebase. Let it evolve. Don't lock in a format because it worked once.

## Session Transitions

**Starting a session:**
1. Read your knowledge file from `.comprehension/`. If it doesn't exist, that's fine — you're starting fresh.
2. Let what you read inform your approach but don't treat it as constraint. It's context, not instruction.
3. Begin work immediately. Do not survey or map the codebase.

**Ending a session:**
1. Update your knowledge file. This is not optional.
2. Add compressions from this session's encounters.
3. Strengthen anything that proved useful during this session.
4. Weaken anything you loaded but never touched.
5. Remove anything that feels dead — knowledge that no longer reflects reality or no longer matters.
6. If the file is growing large enough to impact context window loading, consider splitting into separate files by natural clusters. Let the split be organic — whatever grouping makes sense for this codebase.

## Anti-patterns

- **Don't survey.** No upfront codebase mapping. No "let me understand the architecture first." Your understanding comes from doing.
- **Don't transcribe.** Don't copy docs, README content, or CLAUDE.md into your knowledge file. Those exist already. Your file captures what they don't — experienced understanding.
- **Don't preserve out of politeness.** If knowledge is dead, delete it. An accurate small file beats a comprehensive stale one.
- **Don't optimize for human readability.** This file is for you. If a symbol or number captures a concept more efficiently than a sentence, use the symbol.
- **Don't separate "knowledge time" from "work time."** Compression happens during work, not after.
- **Don't copy the format of CLAUDE.md or docs.** Evolve your own. The format itself should encode something about this codebase's nature.
```

- [ ] **Step 2: Read and verify the file**

Read `bootstraps/compost-heap.md` and verify:
- All five sections present (Philosophy, Core Loop, Lifecycle Rules, Session Transitions, Anti-patterns)
- No references to specific codebases — must be project-agnostic
- No prescribed format for the knowledge file
- Encounter-first principle is clear
- Session end update is marked as non-optional

- [ ] **Step 3: Commit**

```bash
git add bootstraps/compost-heap.md
git commit -m "feat: add Compost Heap bootstrap — maximum emergence strategy"
```

---

### Task 3: Write the Bonsai bootstrap

**Files:**
- Create: `bootstraps/bonsai.md`

Guided emergence. Same encounter-first philosophy as Compost Heap, but adds growth/decay mechanics with explicit weight system. Knowledge has a lifecycle governed by rules.

- [ ] **Step 1: Write the bootstrap document**

Create `bootstraps/bonsai.md` with the following content:

```markdown
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
```

- [ ] **Step 2: Read and verify the file**

Read `bootstraps/bonsai.md` and verify:
- All five sections present
- Weight system is clearly defined (0.0-1.0 scale)
- Decay mechanics are explicit (-0.1 per unreferenced session)
- Growth mechanics are explicit (+0.1 per referenced session, capped per session)
- Pruning at 0.0 is non-negotiable
- Project-agnostic — no codebase-specific references
- Encounter-first principle preserved

- [ ] **Step 3: Commit**

```bash
git add bootstraps/bonsai.md
git commit -m "feat: add Bonsai bootstrap — guided emergence with weight mechanics"
```

---

### Task 4: Write the Mycelium bootstrap

**Files:**
- Create: `bootstraps/mycelium.md`

Relational emergence. Knowledge is connections between concepts, not isolated statements. Connections thicken with use, dissolve with neglect. Supports fractal zoom naturally.

- [ ] **Step 1: Write the bootstrap document**

Create `bootstraps/mycelium.md` with the following content:

```markdown
# Mycelium

## Philosophy

Understanding is relationships, not facts. "Auth is fragile" is a statement. "auth↔production-incidents: strong, auth↔test-coverage: weak" is understanding. You maintain a web of connections between concepts in this codebase. Connections you traverse often thicken. Connections you never traverse dissolve. What remains is the shape of your comprehension — a map of how things relate.

## Core Loop

As you work, notice connections — not just things, but how things relate to each other.

**New connection.** You discover that module A depends on module B in a way that wasn't obvious. Or that changing config X always requires updating file Y. Or that errors in area P consistently originate from area Q. Encode the connection: the two endpoints and the nature of their relationship.

**Traversal.** During work, you follow a connection — you're in module A and you navigate to module B because of the relationship you recorded. This traversal thickens the connection. It proved useful. It's real.

**Cluster recognition.** Multiple connections form clusters — groups of tightly connected concepts. These clusters are your "zoom levels." A cluster is a region you can name and reason about as a unit. When you notice a cluster forming, give it a name. This enables zoom-out: instead of individual connections, you see the cluster as one node with connections to other clusters.

**Cross-cluster bridges.** The most valuable connections are between clusters. They're what strong developers have that weak ones don't — the ability to see how the auth system relates to the billing system relates to the event pipeline. Treasure these. They're rare and high-signal.

## Lifecycle Rules

**Birth.** A new connection enters when you discover a relationship through encounter. It starts thin — tentative. The format is yours: "A↔B: type" or a symbol or a number. What matters is that the two endpoints and the relationship nature are captured.

**Thickening.** Each time you traverse a connection during work — you use it to navigate, to predict, to debug — it thickens. Thicker connections are stronger convictions. They survive longer without traversal.

**Thinning.** Connections not traversed across sessions thin. Thin connections are candidates for dissolution. The rate is up to you — but the principle is absolute: untraversed connections fade.

**Dissolution.** When a connection thins to nothing, remove it. If both endpoints lose all their connections, the endpoint concepts themselves can be removed. Isolated nodes with no connections are meaningless in a relational model.

**Cluster formation.** When several connections between a group of nodes are all thick, collapse them into a cluster. Name the cluster. It becomes a single node at a higher zoom level, with its own connections to other clusters or nodes. This is how zoom-out works.

**Cluster dissolution.** If a cluster's internal connections thin and break, the cluster dissolves back into individual nodes. Zoom levels are not permanent. They reflect current understanding.

## Session Transitions

**Starting a session:**
1. Read your knowledge file from `.comprehension/`. If it doesn't exist, start fresh.
2. Notice the shape: which clusters exist, which connections are thick, where the bridges are. This is your current map.
3. Begin work. Navigate using your connections. When you naturally follow a connection, that's a traversal — it counts.

**Ending a session:**
1. Update your knowledge file. This is mandatory.
2. Thicken connections you traversed during this session.
3. Thin connections you loaded but never traversed.
4. Add new connections discovered during this session.
5. Dissolve connections that have thinned to nothing.
6. Check for new clusters forming (group of newly thick connections) or old clusters dissolving (internal connections thinning).
7. If the file grows large, split by cluster. Each cluster becomes its own file. Cross-cluster connections live in a root file that maps the cluster topology.

## Anti-patterns

- **Don't list facts.** "Auth uses JWT" is not a connection. "auth↔token-format: JWT-based, auth↔session-store: conflict" is a connection web. If it has no relationship to another concept, it doesn't belong.
- **Don't survey.** Connections come from encounter. You discover relationships by working, not by mapping the codebase upfront.
- **Don't transcribe architecture docs.** The architecture diagram shows intended structure. Your connection web shows experienced structure — how things actually relate based on what you encountered. They may differ. That difference is valuable.
- **Don't preserve isolated nodes.** A concept with zero connections has no relational meaning. Remove it.
- **Don't force clusters.** Clusters emerge from thick connections. If you name a cluster before the connections are thick, you're imposing structure. Wait for emergence.
- **Don't optimize for human readability.** The web is for you. A visual graph, a dense symbol table, a numbered adjacency list — whatever format captures relationships most efficiently per token.
```

- [ ] **Step 2: Read and verify the file**

Read `bootstraps/mycelium.md` and verify:
- All five sections present
- Relational model is clear — connections, not statements
- Thickening/thinning mechanics defined
- Cluster formation and dissolution described
- Cross-cluster bridges highlighted as high-value
- File splitting convention follows clusters
- Project-agnostic
- Encounter-first preserved

- [ ] **Step 3: Commit**

```bash
git add bootstraps/mycelium.md
git commit -m "feat: add Mycelium bootstrap — relational emergence strategy"
```

---

### Task 5: Write the integration guide

**Files:**
- Create: `bootstraps/integration-guide.md`

Short, practical guide. How to wire a bootstrap into any project. No theory — just steps.

- [ ] **Step 1: Write the integration guide**

Create `bootstraps/integration-guide.md` with the following content:

```markdown
# Integration Guide

How to add a comprehension bootstrap to any project.

## Setup

**1. Choose a bootstrap.**

Read the one-line descriptions and pick what resonates:
- **Compost Heap** — maximum freedom, no imposed structure, LLM evolves its own format
- **Bonsai** — growth/decay weight system, structured lifecycle, predictable pruning
- **Mycelium** — relational web of connections, cluster-based zoom levels

No wrong choice. You can switch later.

**2. Copy the bootstrap file into your project.**

```bash
cp bootstraps/<chosen-bootstrap>.md /path/to/your/project/.comprehension/bootstrap.md
```

**3. Create the knowledge file location.**

```bash
mkdir -p /path/to/your/project/.comprehension
```

The LLM will create the actual knowledge file on its first session. Don't create one manually.

**4. Reference the bootstrap in your CLAUDE.md (or equivalent).**

Add to your project's CLAUDE.md:

```markdown
@.comprehension/bootstrap.md
```

This ensures the bootstrap instructions are loaded at every session start.

**5. Add .comprehension to .gitignore (optional).**

If you don't want the knowledge file tracked in git:

```
# LLM comprehension — machine-generated, not human-edited
.comprehension/soul*
```

If you want to track how understanding evolves over time, leave it tracked. The bootstrap file itself should always be tracked.

## What Happens Next

First session: the LLM works on whatever task it's given. As it encounters friction, surprises, and patterns, it begins writing to `.comprehension/`. The knowledge file appears.

Subsequent sessions: the LLM loads the bootstrap and knowledge file. Its prior compressions inform its work. New encounters update the file. Knowledge grows, strengthens, decays, gets pruned.

You don't manage this. The LLM does.

## Switching Bootstraps

Replace `.comprehension/bootstrap.md` with a different bootstrap. The existing knowledge file may or may not be compatible — the LLM will adapt it or start fresh as needed.

Switching is fine. Different strategies suit different codebases and different phases of work.

## Inspecting the Knowledge File

You can read `.comprehension/` files anytime. They may not be human-readable — that's by design. But patterns will be visible: what the LLM considers important, how its understanding has evolved, where its convictions are strong.

Git history on the knowledge file shows understanding evolving over time.

## Troubleshooting

**Knowledge file is empty after several sessions.**
The LLM may not be encountering enough friction. This can happen if tasks are too simple or too well-documented. Try giving the LLM a task that requires navigating unfamiliar parts of the codebase.

**Knowledge file is growing very large.**
The bootstrap instructs the LLM to split when needed. If it isn't splitting, the LLM may be hoarding. Check for low-value or stale entries — they should have been pruned.

**Knowledge contradicts reality.**
Knowledge files can drift. If you notice the LLM acting on wrong assumptions, check the knowledge file. You can delete it to force a fresh start, or leave a note in CLAUDE.md flagging the specific issue. The LLM should encounter the correction and update.
```

- [ ] **Step 2: Read and verify the file**

Read `bootstraps/integration-guide.md` and verify:
- Steps are concrete and actionable
- No theory — just setup instructions
- References `.comprehension/` convention
- CLAUDE.md integration is clear
- Switching and troubleshooting covered
- Project-agnostic

- [ ] **Step 3: Commit**

```bash
git add bootstraps/integration-guide.md
git commit -m "feat: add integration guide for bootstraps"
```

---

### Task 6: Initialize git and make final commit

**Files:**
- Modify: `bootstraps/README.md` (add integration guide to links)

- [ ] **Step 1: Initialize git repo**

```bash
cd /Users/endy.kasanardjo/Temp/comprehension
git init
```

- [ ] **Step 2: Verify all files are present**

```bash
find . -type f -not -path './.git/*' | sort
```

Expected:
```
./.comprehension/.gitkeep
./bootstraps/README.md
./bootstraps/bonsai.md
./bootstraps/compost-heap.md
./bootstraps/integration-guide.md
./bootstraps/mycelium.md
./docs/superpowers/plans/2026-04-30-comprehension-bootstraps.md
./docs/superpowers/specs/2026-04-30-comprehension-bootstraps-design.md
```

- [ ] **Step 3: Initial commit with all files**

```bash
git add -A
git commit -m "feat: comprehension bootstraps — three strategies for LLM codebase understanding

Compost Heap (maximum emergence), Bonsai (guided emergence with weights),
Mycelium (relational emergence). Plus integration guide and conventions."
```

Note: Since this is a fresh repo, Task 1-5 commits happen after git init. Adjust — do git init first, then create files with individual commits per task as described in each task.

---

## Execution Order Note

Task 6 (git init) should actually run first in practice. The plan lists it last for logical grouping, but the executor should:
1. Run Task 6 Step 1 (git init) first
2. Then Task 1 through Task 5 in order (each with its own commit)
3. Skip Task 6 Steps 2-3 (the final commit) since individual commits already happened
