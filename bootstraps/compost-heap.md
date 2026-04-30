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
