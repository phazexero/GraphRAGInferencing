# Graph RAG

The main purpose of this repo is to demostrate how to build a RAG mechanism with the use of Knowledge graph. The main purpose of this is to branch of from the concept of vector RAG mechanisms and use it for cases where vector RAGs are inefficient and don't give enough context. Microsoft is the company which started with this first and now has released the open source documentation for GraphRAG. In their on terms:

"GraphRAG is a structured, hierarchical approach to Retrieval Augmented Generation (RAG), as opposed to naive semantic-search approaches using plain text snippets. The GraphRAG process involves extracting a knowledge graph out of raw text, building a community hierarchy, generating summaries for these communities, and then leveraging these structures when perform RAG-based tasks."

Which is effectively short for "we have built a library which can perform RAG for graph databases".

### GraphRAG vs Baseline RAG 🔍
To approach the answer to this we first need to define what RAG is, so Retrieval-Augmented Generation (RAG) is a technique to improve LLM outputs using real-world information. This technique is an important part of most LLM-based tools and the majority of RAG approaches use vector similarity as the search technique, which can be called Baseline RAG. 

GraphRAG uses knowledge graphs to provide substantial improvements in question-and-answer performance when reasoning about complex information. RAG techniques have shown promise in helping LLMs to reason about private datasets - data that the LLM is not trained on and has never seen before, such as an enterprise’s proprietary research, business documents, or communications. Baseline RAG was created to help solve this problem, but we observe situations where baseline RAG performs very poorly. For example:

1. Baseline RAG struggles to connect the dots. This happens when answering a question requires traversing disparate pieces of information through their shared attributes in order to provide new synthesized insights.
2. Baseline RAG performs poorly when being asked to holistically understand summarized semantic concepts over large data collections or even singular large documents.