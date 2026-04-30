# Comprehension Bootstraps

LLMs start every session from scratch. CLAUDE.md and docs help, but they're flat text — no conviction hierarchy, no earned understanding, no feel. Strong developers build intuition through years of friction. This project gives LLMs a mechanism to do the same.

## The Problem

In a 100K-line codebase, some developers quickly build deep understanding. Others never do, regardless of tenure. The difference isn't knowledge — it's **earned compression**: heuristics built through repeated encounter with the code, where the struggle itself is load-bearing.

LLMs can be *told* heuristics, but telling isn't earning. A heuristic without encounter behind it is trivia — the LLM can't judge when it applies and when it breaks.

## The Solution

A **bootstrap document** teaches an LLM to grow its own codebase comprehension through encounter. Not knowledge about a codebase — a method for *building* knowledge about any codebase.

The LLM maintains a **knowledge file** (`.comprehension/`) that evolves across sessions. Knowledge enters through friction, strengthens through use, and dies through neglect. The format is chosen by the LLM — not prescribed by humans. What survives is what proves useful.

## Three Strategies

Different learning philosophies for different codebases and preferences:

| Bootstrap | Philosophy | Best For |
|-----------|-----------|----------|
| [Compost Heap](bootstraps/compost-heap.md) | Maximum emergence. No structure imposed. | Exploratory projects, maximum LLM autonomy |
| [Bonsai](bootstraps/bonsai.md) | Guided emergence. Weight-based growth/decay. | Structured codebases, predictable lifecycle |
| [Mycelium](bootstraps/mycelium.md) | Relational emergence. Knowledge as connections. | Distributed systems, interconnected codebases |

## Getting Started

See the [Integration Guide](bootstraps/integration-guide.md) for setup, switching strategies, and troubleshooting.

## Principles

- **Encounter-first** — no surveying. Knowledge is a side effect of doing work.
- **LLM-maintained** — humans don't edit the knowledge file. It's for the LLM.
- **Emergent format** — the LLM evolves whatever representation compresses best.
- **Growth and decay** — used knowledge strengthens, unused knowledge fades.
- **Living structure** — what grows today can shrink tomorrow. That's the point.
