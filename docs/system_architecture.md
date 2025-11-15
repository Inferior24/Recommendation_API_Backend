# 02 — System Architecture

The architecture is composed of five major layers:

1. **Data Pipeline**
   - Raw data cleanup
   - Normalization
   - Chunking logic
   - Metadata enhancement

2. **Embedding Engine**
   - Transformer-based embeddings
   - Vector generation
   - Index compatibility checks

3. **FAISS Indexing Layer**
   - L2 normalized vectors
   - Flat or HNSW indexing (depending on scale)
   - Persistent storage

4. **Semantic Retrieval Layer**
   - Query embedding
   - Vector similarity search
   - Metadata filtering

5. **Ranking & API Layer**
   - Hybrid scoring
   - Output formatting
   - FastAPI routes for recommendations and Q&A

A RAG chatbot and UI dashboard sit as planned extensions on top of this architecture.
# Architecture Diagram (Textual Representation)

                 ┌──────────────────────────┐
                 │      User Query          │
                 └─────────────┬────────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │     Data Pipeline        │
                 │──────────────────────────│
                 │ • Raw data cleanup       │
                 │ • Normalization          │
                 │ • Chunking logic         │
                 │ • Metadata enhancement   │
                 └─────────────┬────────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │    Embedding Engine      │
                 │──────────────────────────│
                 │ • Transformer model       │
                 │ • Vector generation       │
                 │ • L2 normalization        │
                 │ • Dimensionality checks   │
                 └─────────────┬────────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │    FAISS Index Layer     │
                 │──────────────────────────│
                 │ • Vector storage          │
                 │ • Flat / HNSW index       │
                 │ • Fast similarity search  │
                 └─────────────┬────────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │  Semantic Retrieval      │
                 │──────────────────────────│
                 │ • Embed user query        │
                 │ • Vector similarity search│
                 │ • Metadata filtering      │
                 └─────────────┬────────────┘
                               │
                               ▼
                 ┌──────────────────────────┐
                 │ Ranking & API Layer      │
                 │──────────────────────────│
                 │ • Hybrid scoring          │
                 │ • Response formatting     │
                 │ • FastAPI routes          │
                 │     /recommend            │
                 │     /ask                  │
                 │     /evaluate             │
                 └─────────────┬────────────┘
                               │
                               ▼
       ┌───────────────────────────────────────────────────┐
       │            Planned Extensions (Future)            │
       │───────────────────────────────────────────────────│
       │ • Multi-turn RAG Chatbot                          │
       │ • Visual Dashboard / UI                           │
       └───────────────────────────────────────────────────┘
