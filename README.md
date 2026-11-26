> **Moved.** This project now lives in [d3dcrypted/llmops](https://github.com/d3dcrypted/llmops), in the [`rag-pipeline/`](https://github.com/d3dcrypted/llmops/tree/main/rag-pipeline) directory, together with the rest of the stack. This repository is archived and stays readable.

# LLMOps RAG Pipeline

A small, transparent retrieval-augmented generation reference implementation. The first milestone covers deterministic ingestion, chunking, retrieval and citations behind testable interfaces; no framework abstraction yet.

## Roadmap

- [x] deterministic text chunking
- [x] source metadata and citation objects
- [x] dependency-free baseline retriever
- [ ] embedding-backed retrieval
- [ ] generation adapter
- [ ] faithfulness and context-precision evaluation
- [ ] REST API and container deployment

## Security baseline

`ingest_file()` reads one explicitly selected UTF-8 file below an operator-provided root. Traversal, symlink targets, non-files, and oversized inputs are rejected. `retrieve_with_citations()` returns the source, chunk index, and exact retrieved text so citations can be verified without trusting generated prose.

## Run

```bash
python3 -m unittest discover -s tests -v
```

The examples are synthetic. Do not place confidential documents, credentials, or production data in this repository.

## Authorship

Human thought, machine hand. The author set the direction, took the decisions and reviewed the result; an AI assistant produced the drafting, the code and the prose in this file. Mistakes are the author's.

## License

MIT
