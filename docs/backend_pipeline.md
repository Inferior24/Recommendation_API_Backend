# 07 — Backend Pipeline

The backend is implemented in FastAPI.

Major routes:

- **/recommend**  
  Takes a natural language query, runs retrieval + ranking, returns top API suggestions.

- **/ask**  
  A question-answering route that uses semantic search to generate responses using retrieved context.

- **/evaluate**  
  A debugging endpoint that exposes:
  - retrieved chunks
  - ranking scores
  - metadata traces

Supporting components include loaders, preprocessing utilities, FAISS wrappers, and logging tools.
