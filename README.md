# Repolex Knowledge Graph of plotly/DataframesBenchmark

RDF knowledge graph data for [plotly/DataframesBenchmark](https://github.com/plotly/DataframesBenchmark), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [rlex](https://github.com/repolex-ai/rlex) query tool:

```bash
cargo install --git https://github.com/repolex-ai/rlex
```

Verify the install:

```bash
rlex --help
```

**rlex is designed to be used primarily by LLMs in a terminal.** Start up your favorite AI assistant and ask it to use rlex. It handles the SPARQL — you just ask questions in plain English.

To load this repo's data:

```bash
rlex download plotly/DataframesBenchmark
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 6beefb48878200d2bf16854200046191e62844a8
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 6beefb48878200d2bf16854200046191e62844a8
│           └── chunk-001.nq.gz
├── blob
│   ├── 0e67458fecbfa8c714384686e8cf5d2a8d1128e4.nq.gz
│   ├── 2d2ddf0dceeee3c1700293f34e35a401d9f48c1a.nq.gz
│   ├── 3607066bdc1fbd9ed7b49f8abe5ad014dda7fca0.nq.gz
│   ├── 5607b9c0f18febd0337529ba30514403b560317d.nq.gz
│   ├── 6e4692ba5e29c66f08e99a4926e7744e7b779bbe.nq.gz
│   ├── 792c76a2748ea9a1bbc0e7ff3fb128d982a29e93.nq.gz
│   ├── cc695391a0ed134e9c40271a4280f6ac0c8dec06.nq.gz
│   └── ecae0b461c4eb0f6c80875297463a4e037f01afb.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 6beefb48878200d2bf16854200046191e62844a8.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 14 files
```

| Directory | What it contains |
|-----------|-----------------|
| `blob/` | Per-file AST graphs, content-addressed by git blob SHA. Each file in the source repo gets its own graph. |
| `aggregate/ast/` | Combined AST graph per parsed commit. Merges all blob graphs for a snapshot of the entire codebase at that point. |
| `aggregate/lsp/` | Language Server Protocol enrichment: resolved symbols, definitions, references, and type information. |
| `aggregate/dataflow/` | Interprocedural data flow edges between functions and modules. |
| `aggregate/repolex/` | Combined graph (AST + LSP + dataflow) per commit. |
| `commit/` | Git commit metadata (author, date, message, parent links). |
| `branch/` | Branch metadata. |
| `tag/` | Tag metadata. |
| `filetree/` | File tree snapshots per commit (which files existed and their blob SHAs). |
| `audit/` | Code architecture and graph audit reports per commit. |

## Source repository

[plotly/DataframesBenchmark](https://github.com/plotly/DataframesBenchmark)

---
*Parsed on 2026-11-07 by [repolex](https://repolex.ai)*
