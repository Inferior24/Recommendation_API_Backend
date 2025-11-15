# 08 — API Reference

## POST /recommend
Input: 
- query (string)

Output:
- top recommended API functions or modules
- ranking scores
- metadata

## POST /ask
Input:
- user query

Output:
- context-aware answer generated using retrieved chunks
- supporting evidence

## POST /evaluate
Debug endpoint returning:
- embeddings
- FAISS retrieval results
- scoring breakdown
