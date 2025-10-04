# Complete RAG (Retrieval-Augmented Generation) 

## Introduction

Welcome to the **Complete RAG** repository! This repository contains a comprehensive guide and implementation of **Retrieval-Augmented Generation (RAG)** from scratch. RAG is a powerful framework that combines the strengths of **retrieval-based** and **generation-based** models to improve natural language generation (NLG) tasks by incorporating external knowledge through retrieval mechanisms.

This guide walks you through each stage of building a RAG system, from data collection and preprocessing to training and evaluation. Whether you’re new to RAG or looking to refine your implementation, this repository provides all the tools, concepts, and code necessary.


![Screenshot 2025-03-15 222902](https://github.com/user-attachments/assets/311a81a8-9e76-40ae-9218-ff59a648a5de)


# Retrieval-Augmented Generation (RAG) Process

Retrieval-Augmented Generation (RAG) is a framework that enhances language models by retrieving relevant information from external knowledge bases before generating responses. This improves accuracy, relevance, and contextual understanding. The process involves multiple stages, including query construction, translation, routing, retrieval, indexing, and generation.

---

## [Table of Contents](#table-of-contents)
- [Introduction](https://github.com/Adity-star/CompleteRAG/tree/main/all_rag_techniques/01_Introduction#-module-1-introduction-to-retrieval-augmented-generation-rag)
- [understanding Knowledge Bases](https://github.com/Adity-star/CompleteRAG/tree/main/all_rag_techniques/02_LLMs_knowledge_bases#-module-2-understanding-language-models--knowledge-bases)
- [Query Construction](#query-construction)
- [Query Translation](#query-translation)
- [Routing](#routing)
- [Retrieval](#retrieval)
- [Indexing](#indexing)
- [Generation](#generation)
- [Advanced Rag](#advanced-rag)

---

## Query Construction
The first step in RAG is formulating the query for retrieval. Depending on the type of database, different query construction methods are used:

### 1. Relational Databases (Relational DBs)
- Uses **Text-to-SQL** conversion.
- Converts natural language queries into SQL queries with optional vector-based search using **PGVector**.

### 2. Graph Databases (GraphDBs)
- Uses **Text-to-Cypher** conversion.
- Converts natural language queries into Cypher queries for Graph Databases.

### 3. Vector Databases (VectorDBs)
- Uses **Self-query retriever**.
- Auto-generates metadata filters from the query to refine search results.

Here is a complete code [Notebook](https://github.com/Adity-star/CompleteRAG/blob/main/Rag_query_transformation_1.ipynb) for query construction and translation.  

[Back to table of contents](#table-of-contents)
---

## Query Translation
Before retrieving documents, the input query is refined and transformed into a better-suited format using various techniques:
- **Multi-query**: Reformulates a single question into multiple related queries.
- **RAG-Fusion**: Combines results from multiple queries to enhance retrieval.
- **Decomposition**: Breaks down complex queries into simpler sub-queries.
- **Step-back**: Generalizes the query to retrieve broader relevant information.
- **HyDE (Hypothetical Document Embeddings)**: Generates hypothetical documents to enhance retrieval quality.

Here is a complete code [Notebook](https://github.com/Adity-star/CompleteRAG/blob/main/Rag_query_transformation_1.ipynb) for query construction and translation.

[Back to table of contents](#table-of-contents)
---

## Routing
Routing determines which database should be queried and how.

### 1. Logical Routing
- The **LLM** selects the appropriate database (Relational DB, GraphDB, or VectorDB) based on the query.

### 2. Semantic Routing
- Uses embedding-based similarity matching to route the query to the most relevant prompt.

Here is complete process of RAG Routing through code in this [Notebook](https://github.com/Adity-star/CompleteRAG/blob/main/RAG_routing.ipynb)

[Back to table of contents](#table-of-contents)
---

## Retrieval
Once a query is routed, the system retrieves relevant documents. This step consists of:

### 1. Ranking
- Filters and ranks retrieved documents using methods like **Re-Rank, RankGPT, and RAG-Fusion**.

### 2. Refinement
- **CRAG (Compression-RAG)** further filters and compresses documents to improve relevance.

### 3. Active Retrieval
- If retrieved documents are not relevant, the system **re-retrieves** data from alternative sources (e.g., web search).

Here is complete process of RAG Retrivel through code in this [Notebook](https://github.com/Adity-star/CompleteRAG/blob/main/RAG_Retrivel.ipynb)

[Back to table of contents](#table-of-contents)
---

## Indexing
Indexing optimizes document retrieval by structuring stored data efficiently.

### 1. Chunk Optimization
- **Semantic Splitter**: Splits text into meaningful chunks based on semantic delimiters for better embedding.

### 2. Multi-Representation Indexing
- **Parent Document, Dense X**: Converts documents into compact retrieval units, such as summaries.

### 3. Specialized Embeddings
- Uses advanced embedding models like **Fine-tuning, CoLBERT** for better retrieval.

### 4. Hierarchical Indexing
- **RAPTOR** organizes documents in a tree-like structure with summaries at different abstraction levels.

Here is complete process of RAG  Indexing and Generation through code in this [Notebook](https://github.com/Adity-star/CompleteRAG/blob/main/RAG_Indexing.ipynb)

[Back to table of contents](#table-of-contents)
---

## Generation
The final step is generating responses based on retrieved documents.

### 1. Active Retrieval
- Uses document generation quality to determine whether additional re-retrieval is needed.

### 2. Self-RAG & RRR (Re-Retrieve & Rewrite)
- Enhances response quality by **re-writing** the query or **re-retrieving** better documents.

Here is complete process of RAG  Indexing and Generation through code in this [Notebook](https://github.com/Adity-star/CompleteRAG/blob/main/RAG_Indexing.ipynb)

[Back to table of contents](#table-of-contents)

---
## Advanced Rag

This project implements a sophisticated Retrieval-Augmented Generation (RAG) architecture by combining three complementary modules:

| Notebook | Role / Purpose |
|---|---|
| [`HyDe_Hypothetical_document_embedding.ipynb`](https://github.com/Adity-star/CompleteRAG/blob/main/all_rag_techniques/HyDe_Hypothrtical_document_embedding.ipynb) | Builds dense embeddings for documents using hybrid / hypothetical embedding strategies to maximize retrieval relevance |
| [`contextual_chunk_headers.ipynb`](https://github.com/Adity-star/CompleteRAG/blob/main/all_rag_techniques/contextual_chunk_headers.ipynb) | Splits documents into contextual chunks and associates header-level metadata to each chunk for enhanced retrieval context |
| [`corrective_RAG.ipynb`](https://github.com/Adity-star/CompleteRAG/blob/main/all_rag_techniques/corrective_RAG.ipynb) | Wraps the retrieval + generation loop with corrective feedback to iteratively refine output and reduce hallucinations |

---

## Conclusion
The RAG pipeline efficiently combines retrieval and generation techniques to improve the accuracy of language models. By integrating structured and unstructured data sources, it enhances the quality of generated responses, making it a powerful framework for AI-driven applications.

---


---

### 🚀 Stay Connected
If you found this helpful, feel free to contribute, star the repo ⭐, and follow for updates!


