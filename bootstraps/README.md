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
