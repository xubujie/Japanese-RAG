# Japanese RAG

This repo is dedicated to a collection of methodologies, models, and resources aimed at enhancing Retrieval Augmented Generation (RAG), with a particular emphasis on Japanese.

## Enhancing RAG Performance

RAG applications are fundamentally comprised of three key components:

1. **Data Loader & Indexing**
2. **Retrieval**
3. **Synthesis**

Below is a curated list of valuable resources intended to elevate the quality of Japanese RAG applications.

### Data Loader & Indexing

- **Data Loaders:**

  - [PaddleOCR-Japanese](https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_i18n/README_%E6%97%A5%E6%9C%AC%E8%AA%9E.md): An OCR tool for Japanese text extraction.
  - [Processing Tables in PDFs](https://webcache.googleusercontent.com/search?q=cache:https://levelup.gitconnected.com/a-guide-to-processing-tables-in-rag-pipelines-with-llamaindex-and-unstructuredio-3500c8f917a7&strip=0&vwsrc=1&referer=medium-parser): Techniques for handling table data within PDF documents.
  - My custom parser for DOCX-converted HTML (to be open-sourced soon).

- **Embedding Models:**

  - OpenAI Embedding (text-embedding-3-small, text-embedding-3-large).
  - [BGE-Embedding](https://github.com/FlagOpen/FlagEmbedding?tab=readme-ov-file): A specialized embedding model.

- **Fine-tuning Embeddings:**
  - [Fine-tune Embeddings with LlamaIndex](https://github.com/run-llama/finetune-embedding): Tailor embeddings to your specific document sets.

### Retrieval

- **Re-rankers:**

  - [Cohere Re-ranker](https://cohere.com/rerank): Enhance retrieval relevance.
  - [BGE Re-ranker](https://github.com/FlagOpen/FlagEmbedding/tree/master/FlagEmbedding/reranker): A model for improving retrieval accuracy.

- **Retrievers:**
  - [Experiment with Various Retrievers in LlamaIndex Modules](https://docs.llamaindex.ai/en/stable/module_guides/querying/retriever/retrievers.html): Explore different retrieval models.

### Synthesis

While GPT-4 performs well in most scenarios, tailored results might require using a Japanese LLM or fine-tuning an open-source LLM.

- [Japanese LLMs](https://github.com/llm-jp/awesome-japanese-llm): A compilation of Japanese language models.

### General Methodology Applicable to All Languages

- [12 RAG Pain Points and Proposed Solutions](https://towardsdatascience.com/12-rag-pain-points-and-proposed-solutions-43709939a28c): Identifying and addressing common challenges in RAG.
- [Ollama for Easy Model Hosting](https://github.com/ollama/ollama): Simplify the hosting of your models.
- [Parameter Tuning for RAG with LlamaIndex](https://docs.llamaindex.ai/en/stable/examples/param_optimizer/param_optimizer.html): Optimize your RAG parameters for better performance.

## Contribution

Welcome contributions to this repository! Let's help to improve RAG in Japanese together.
