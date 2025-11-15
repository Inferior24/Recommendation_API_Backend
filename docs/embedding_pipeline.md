# 04 — Embedding Pipeline

The embedding layer transforms each chunk into a vector representation.

Components:

- Model loader (Sentence Transformers / Instructor models)
- Batch encoding for efficiency
- L2 normalization for FAISS compatibility
- Dimensionality checks
- Persistent storage in JSON/Parquet alongside metadata

The pipeline outputs:
- chunk_id
- chunk_text
- embedding vector
- metadata object

# Embedding Pipeline Diagram (Textual Representation)

                ┌──────────────────────────┐
                │    Input Chunks          │
                │ (Cleaned + Metadata)     │
                └─────────────┬────────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │     Model Loader         │
                │──────────────────────────│
                │ • Sentence Transformers   │
                │ • Instructor Models       │
                │ • Device allocation       │
                └─────────────┬────────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │     Batch Encoder        │
                │──────────────────────────│
                │ • Batch text embedding    │
                │ • Tokenization optimiza.  │
                │ • Parallel processing     │
                └─────────────┬────────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │   L2 Normalization       │
                │──────────────────────────│
                │ • Normalize vectors        │
                │ • Ensure FAISS readiness   │
                └─────────────┬────────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │ Dimensionality Checks    │
                │──────────────────────────│
                │ • Validate vector size     │
                │ • Ensure model consistency │
                └─────────────┬────────────┘
                              │
                              ▼
                ┌──────────────────────────┐
                │ Persistent Storage        │
                │──────────────────────────│
                │ • JSON / Parquet output   │
                │ • Store metadata          │
                │ • Save chunk embeddings   │
                └─────────────┬────────────┘
                              │
                              ▼
         ┌───────────────────────────────────────────┐
         │            Pipeline Output Objects        │
         │───────────────────────────────────────────│
         │ • chunk_id                                │
         │ • chunk_text                              │
         │ • embedding vector                        │
         │ • metadata object                         │
         └───────────────────────────────────────────┘
