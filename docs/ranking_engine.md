# 06 — Ranking Engine

The ranking engine assigns final relevance scores using a hybrid scoring strategy.

Scoring components:

- Semantic similarity
- Keyword overlap
- Metadata priority
- Positional/contextual weighting
- Optional heuristic boosts for:
  - Recency
  - Section importance
  - API-specific signals

The final score = weighted hybrid function of all the above.

This produces more consistent and human-aligned recommendations than pure vector search.
