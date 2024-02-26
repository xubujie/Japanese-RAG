[日本語](README.md) | [English](README_en.md)

- [日本語 RAG](#日本語-rag)
  - [RAG パフォーマンスの向上](#rag-パフォーマンスの向上)
    - [データローダー＆インデキシング](#データローダーインデキシング)
    - [Retrieval](#retrieval)
    - [生成](#生成)
    - [すべての言語に適用可能な一般的な方法論](#すべての言語に適用可能な一般的な方法論)
- [貢献](#貢献)

# 日本語 RAG

このリポジトリは、日本語検索拡張生成（RAG）を強化するための方法論、モデル、リソースのコレクションです。

## RAG パフォーマンスの向上

RAG アプリケーションは、基本的に 3 つの主要なコンポーネントで構成されています：

1. **データローダー＆インデキシング**
2. **検索**
3. **生成**

### データローダー＆インデキシング

- **データローダー：**

  - [PaddleOCR-日本語](https://github.com/PaddlePaddle/PaddleOCR/blob/release/2.7/doc/doc_i18n/README_%E6%97%A5%E6%9C%AC%E8%AA%9E.md)：日本語テキスト抽出のための OCR ツール。
  - [PDF 内の表の処理](https://webcache.googleusercontent.com/search?q=cache:https://levelup.gitconnected.com/a-guide-to-processing-tables-in-rag-pipelines-with-llamaindex-and-unstructuredio-3500c8f917a7&strip=0&vwsrc=1&referer=medium-parser)：PDF ドキュメント内の表データを扱う技術。
  - 私のカスタムパーサー（DOCX 変換された HTML 用、近日オープンソース化予定）。

- **日本語 Tokenizer**: for hybrid search

  - [sudachi](https://github.com/WorksApplications/Sudachi)
  - [kuromoji](https://github.com/atilika/kuromoji)
  - [mecab](https://github.com/taku910/mecab)

---

|                              | Sudachi | MeCab     | kuromoji   |
| :--------------------------- | :------ | :-------- | :--------- |
| Multiple Segmentation        | Yes     | No        | Limited ^a |
| Normalization                | Yes     | No        | Limited ^b |
| Joining, Correction          | Yes     | No        | Limited ^b |
| Use multiple user dictionary | Yes     | Yes       | No         |
| Saving Memory                | Good ^c | Poor      | Good       |
| Accuracy                     | Good    | Good      | Good       |
| Speed                        | Good    | Excellent | Good       |

- ^a: approximation with n-best
- ^b: with Lucene filters
- ^c: memory sharing with multiple Java VMs

---

- **Embedding モデル:**

  - OpenAI Embedding (text-embedding-3-small, text-embedding-3-large).
  - [BGE-Embedding](https://github.com/FlagOpen/FlagEmbedding?tab=readme-ov-file): 多言語用高性能 Embedding モデル

- **Fine-tuning Embeddings:**
  - [Fine-tune Embeddings with LlamaIndex](https://github.com/run-llama/finetune-embedding): 日本語専門文書のために Finetuning

### Retrieval

- **Re-rankers:**

  - [BGE Re-ranker](https://github.com/FlagOpen/FlagEmbedding/tree/master/FlagEmbedding/reranker): 多言語対応の Reranker 商用モデル
  - [Cohere Re-ranker](https://cohere.com/rerank):
  - [BGE Re-ranker](https://github.com/FlagOpen/FlagEmbedding/tree/master/FlagEmbedding/reranker): 多言語対応の Reranker オープンソースモデル

- **Retrievers:**
  - [Experiment with Various Retrievers in LlamaIndex Modules](https://docs.llamaindex.ai/en/stable/module_guides/querying/retriever/retrievers.html): 様々な Retriever の集合

### 生成

GPT-4 はほとんどのシナリオで良好に機能しますが、カスタマイズされた結果が必要な場合は、日本語 LLM を使用するか、オープンソースの LLM をファインチューニングすることを検討してください。

- [日本語 LLM](https://github.com/llm-jp/awesome-japanese-llm)：日本語言語モデルのコンパイル。

### すべての言語に適用可能な一般的な方法論

- [12 の RAG の痛点と提案された解決策](https://towardsdatascience.com/12-rag-pain-points-and-proposed-solutions-43709939)
- [Ollama ーモデルホスティング](https://github.com/ollama/ollama)
- [パラメータチューニングー LlamaIndex](https://docs.llamaindex.ai/en/stable/examples/param_optimizer/param_optimizer.html)

# 貢献

このリポジトリへの貢献を歓迎します！リソース、モデル、または方法論の改善についての提案がある場合は、プルリクエストを送信するか、イシューを開いてください。一緒により良い日本語 RAG を作りましょう。
