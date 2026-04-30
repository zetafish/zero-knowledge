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
