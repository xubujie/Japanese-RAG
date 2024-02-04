# Japanese-RAG

A collection of methods, models, resources that could help to improve RAG (retrieval augmented generation). Especially focus on Japanese, may benefit other non-English language as well.

# Improve RAG performance

RAG applications basically have 3 components:

1. Data Loader & Indexing
2. Retrieve
3. Synthesis

Here is a collection of useful resources that could potentially improve Japanese RAG application's quality.

## Data Loader & Indexing

- Data Loader:

  - [PaddleOCR-Japanese](https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_i18n/README_%E6%97%A5%E6%9C%AC%E8%AA%9E.md)
  - [Deal with table in PDF](https://webcache.googleusercontent.com/search?q=cache:https://levelup.gitconnected.com/a-guide-to-processing-tables-in-rag-pipelines-with-llamaindex-and-unstructuredio-3500c8f917a7&strip=0&vwsrc=1&referer=medium-parser)
  - My custom parser for docx converted HTML (to be open sourced)

- Embedding models:

  - OpenAI embedding (text-embedding-3-small, text-embedding-3-large)
  - [BGE-Embedding](https://github.com/FlagOpen/FlagEmbedding?tab=readme-ov-file)

- Finetune Embedding for your documents:
  - [Finetune embedding with llamaindex](https://github.com/run-llama/finetune-embedding)

# Retrieve

- Reranker:

  - [Cohere reranker](https://cohere.com/rerank)
  - [BGE reranker](https://github.com/FlagOpen/FlagEmbedding/tree/master/FlagEmbedding/reranker)

- Retriever
  - [Try different retrievers in llamaindex modules](https://docs.llamaindex.ai/en/stable/module_guides/querying/retriever/retrievers.html)

## Synthesis

GPT-4 Performs good in most cases, but if you need tailered results, may consider choose a Japanese LLM, or finetune a open-source LLM.

- [Japanese LLMs](https://github.com/llm-jp/awesome-japanese-llm)

## General Methodology applys to all language:

- [12 RAG Pain Points and Proposed Solutions
  ](https://towardsdatascience.com/12-rag-pain-points-and-proposed-solutions-43709939a28c)
- [Ollama to easily host model](https://github.com/ollama/ollama)
- [Paramaeter tuning for RAG with Llamaindex](https://docs.llamaindex.ai/en/stable/examples/param_optimizer/param_optimizer.html)
