---
title: "What's your chunking strategy?"
category: ai
---


`>_TLDR`
Even RAG systems that are powered by LLMs with long context windows require the right chunking strategy for improving retrieval accuracy and response quality.

---

Despite advances in large language models (LLMs) with extended context windows, selecting the right chunking strategy remains crucial to the quality of LLM-generated responses. Chunking refers to the process of dividing documents into smaller, manageable segments known as “chunks” that can be effectively retrieved and interpreted by LLMs.

# RAG (Retrieval Augmented Generation)

RAG is a method that combines an LLM  with an external knowledge retrieval system to produce more accurate, grounded, and up-to-date responses. Enterprises leverage such systems for use cases ranging from enterprise search and document processing to business intelligence to name a few - in other words where specific domain knowledge is required. 

A typical RAG pipeline consists of four key steps:
**1. Parsing documents:** Extracting text from files via file parsers or OCR (Optical Character Recognition) models across different document formats.
**2. Chunking:** Segmenting text into meaningful units that balance retrieval effectiveness with contextual integrity.
**3. Retrieval:** Searching and returning the most relevant chunks using advanced techniques such as vector search.
**4. Generation:** Synthesizing retrieved chunks into a coherent, factually consistent response.

# Chunking Strategies

When LLMs first emerged, they were impressive but limited by short context windows. They could quickly run out of "memory," making them ill-suited for multi-turn conversations or processing large or numerous documents. While modern models now offer extended context windows (some supporting millions of tokens) chunking is still a critical component of an effective RAG system.
In fact, studies have shown that LLMs often struggle to extract information located in the middle of long contexts. A limitation known as the “Lost in the Middle” phenomenon. Even with long context windows, how we chunk information greatly affects performance.

Among the vanilla chunking strategies are:
- **Recursive chunking:** Splits text at high-level semantic boundaries (e.g., paragraphs using double newlines), then progressively breaks it down further as needed.
- **Semantic chunking:** Uses sentence embeddings to detect topic shifts; chunks are created where semantic similarity drops significantly.
- **Markdown-header chunking:** Leverages document structure by splitting at markdown headers helping preserve logical context.

These vanilla approaches can be further improved with the help of LLMs to generate additional metadata or so called LLM-enhanced context-based chunking:
- **Document-level metadata:** A concise summary of the entire document (including key entities and themes) is prepended to every chunk to provide global context.
- **Chunk-level metadata:** Each chunk includes a summary or contextual note derived from the broader document, enriching its standalone meaning and improving retrieval accuracy.

Incorporating LLMs into your chunking strategy to provide richer context for each chunk has shown to lead to even more accurate and relevant retrievals in RAG systems. Despite technological advancements in LLMs, chunking is not going away anytime soon.

---
Sign-up for more!
{% include contact-form.html %}
