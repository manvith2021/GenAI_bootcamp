# RAG Folder Overview

This folder contains notes and guidance for Retrieval-Augmented Generation (RAG) from classes 29 to 33.

## Class 29: Introduction to RAG

- RAG combines retrieval and generation.
- Instead of generating responses from the model alone, RAG retrieves relevant context from a knowledge source first.
- Workflow:
  1. User query arrives.
  2. Query is converted into an embedding.
  3. The vector index is searched for relevant documents.
  4. Retrieved context is passed to the generative model.
  5. Model generates a response grounded in retrieved data.
- Benefits:
  - Reduces hallucinations.
  - Enables up-to-date or domain-specific knowledge without retraining the model.
  - Allows large language models to answer from a curated dataset.

## Class 30: Embeddings and Data Preparation

- Embeddings convert text or documents into dense numeric vectors.
- Good embeddings capture semantic meaning, so similar text maps to nearby vectors.
- Key steps:
  - Choose an embedding model.
  - Normalize text (cleaning, splitting, tokenization).
  - Create embeddings for each document chunk or data item.
- Metadata management:
  - Store document IDs, source names, chunk text, and other fields with each vector.
  - Metadata enables downstream retrieval to show useful context.
- Tools:
  - Embedding APIs from OpenAI, Hugging Face, or other providers.
  - Local embedding models when offline or for privacy.

## Class 31: Vector Index Fundamentals

- A vector index stores embeddings for efficient similarity search.
- Main idea:
  - Embed documents once.
  - Store vectors in an index.
  - Query by embedding and return nearest neighbors.
- Similarity metrics:
  - Cosine similarity
  - Euclidean distance
  - Dot product
- Index types:
  - Flat / brute-force: exact but slow at scale.
  - Approximate indexes: faster for large datasets.
- Role in RAG:
  - The index matches query intent to relevant documents.
  - It is the retrieval layer before generation.

## Class 32: Common Vector Index Types

- Flat Index:
  - Simple.
  - Compares each query to all vectors.
  - Accurate, but not scalable beyond moderate datasets.
- IVF (Inverted File):
  - Clusters vectors.
  - Searches only a subset of clusters.
  - Good tradeoff of speed and accuracy.
- HNSW (Hierarchical Navigable Small World):
  - Graph-based approximate nearest neighbor search.
  - Very fast and scalable.
  - Good for high-dimensional embedding spaces.
- PQ / Quantization:
  - Compresses vectors.
  - Saves memory.
  - Useful when index size is large.

## Class 33: Building and Using a Vector Index

- Index lifecycle:
  1. Data ingestion
  2. Embedding generation
  3. Index creation
  4. Query embedding
  5. Search and retrieval
- Practical considerations:
  - Ensure consistent embedding dimensions.
  - Use the same embedding model for both documents and queries.
  - Keep metadata to interpret retrieval results.
- Retrieval output:
  - Return top-k relevant items.
  - Rank by similarity score.
  - Attach source text and document identifiers.
- RAG integration:
  - Combine retrieved passages with prompt templates.
  - Build prompts that include context and user query.
  - Send the augmented prompt to the generative model.

## Summary

From class 29 through 33, the focus is on:
- understanding RAG as a combination of retrieval and generation,
- preparing data and embeddings,
- building vector indexes,
- choosing the right index type,
- and using retrieval results to ground model output.

This README captures the core concepts and workflow needed to implement a Retrieval-Augmented Generation pipeline.// filepath: c:\Madhu_GenAI\GenAI_bootcamp\rag\README.md