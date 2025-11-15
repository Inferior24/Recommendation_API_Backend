# 05 — Semantic Retrieval

Semantic retrieval is powered by FAISS.

Process:

1. User query is cleaned and embedded
2. Embedding is passed through FAISS index
3. Top-k vectors are returned based on cosine distance
4. Metadata is attached to each retrieved result
5. Results are passed to the ranking engine for scoring

This layer ensures speed and accuracy for large-scale vector operations.
