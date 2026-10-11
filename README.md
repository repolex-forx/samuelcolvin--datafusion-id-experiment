# Repolex Knowledge Graph of samuelcolvin/datafusion-id-experiment

RDF knowledge graph data for [samuelcolvin/datafusion-id-experiment](https://github.com/samuelcolvin/datafusion-id-experiment), parsed by [repolex](https://repolex.ai).

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
rlex download samuelcolvin/datafusion-id-experiment
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e31ed01e44f0914cb5642c473a01f87a25366885
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e31ed01e44f0914cb5642c473a01f87a25366885
│           └── chunk-001.nq.gz
├── blob
│   ├── 43a163036a26fba141716d2217b4cf579a261baf.nq.gz
│   ├── 75306517965a54731b94dca8bace640e856af115.nq.gz
│   ├── a56c44a509b4d9b3c6a21d5e846f46204b4d25a8.nq.gz
│   └── c7534e57de859a600f096bd6b9a103fa494e2a80.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e31ed01e44f0914cb5642c473a01f87a25366885.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 10 files
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

[samuelcolvin/datafusion-id-experiment](https://github.com/samuelcolvin/datafusion-id-experiment)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
