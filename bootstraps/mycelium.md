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
