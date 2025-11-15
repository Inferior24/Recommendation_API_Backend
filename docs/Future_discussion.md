# 11 — Learnings and Future Work

This section outlines the key insights gained during development and provides a roadmap for long-term improvements.

---

## Key Learnings (Detailed)

### 1. Data Quality Drives Everything  
Better data → smoother chunking → more meaningful embeddings → higher retrieval accuracy.  
Even small inconsistencies degrade semantic performance.

### 2. Chunk Granularity Impacts Recall and Precision  
- Smaller chunks increase recall but dilute context  
- Larger chunks improve context but reduce precision  
A balanced, dynamic chunking strategy is essential.

### 3. Hybrid Scoring Outperforms Pure Cosine Similarity  
Pure vector similarity fails in cases where:
- metadata matters,
- structure matters,
- section relevance matters.
Hybrid scoring provides more stable and interpretable outcomes.

### 4. Metadata is a Hidden Superpower  
Adding metadata significantly improves:
- ranking accuracy,
- retrieval filtering,
- debugging clarity,
- domain specificity.

### 5. FastAPI Enables Clean Architecture  
The modular layout of FastAPI simplifies:
- routing logic,
- request validation,
- documentation,
- extension for future models.

---

## Future Work (Expanded)

### **RAG Chatbot Integration**
- multi-turn conversation memory  
- dynamic context building  
- citation-based responses  
- generator model integration  

### **UI Dashboard Development**
- interactive query tools  
- real-time scoring visualizations  
- dataset explorer  
- performance analytics  

### **Better Chunking Heuristics**
- semantic boundary detection  
- code-block aware segmentation  
- adaptive windowing based on content density  

### **Multi-Model Embedding Ensemble**
- combine multiple embedding models  
- weighted ensemble strategies  
- fallback mechanisms for out-of-distribution queries  

### **Scalable Indexing Improvements**
- HNSW for fast approximate search  
- IVF + PQ for large datasets  
- multi-shard vector indexes  

### **API Analytics Dashboard**
Track and visualize:
- user behavior  
- most queried topics  
- ranking stability  
- retrieval drift  
- performance bottlenecks
