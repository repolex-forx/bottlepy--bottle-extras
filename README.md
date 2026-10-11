# Repolex Knowledge Graph of bottlepy/bottle-extras

RDF knowledge graph data for [bottlepy/bottle-extras](https://github.com/bottlepy/bottle-extras), parsed by [repolex](https://repolex.ai).

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
rlex download bottlepy/bottle-extras
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── e385a3940ed172e99dc46f5bf05d92dd35c95e41
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── e385a3940ed172e99dc46f5bf05d92dd35c95e41
│           └── chunk-001.nq.gz
├── blob
│   ├── 11362d3112b1a6f5b709ae07c3d767d868caa339.nq.gz
│   ├── 38af035f72a2a7ae865ed479b72f70bc701fbcc9.nq.gz
│   ├── 41f70b25444a48114856edf02467c93ec757c3d9.nq.gz
│   ├── 4b304d2a59be8ec0e4c6eaaaf0fa3f60103180eb.nq.gz
│   └── b8b62dc050b5d2c56969e8f493aa1e62eaef97c5.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── e385a3940ed172e99dc46f5bf05d92dd35c95e41.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 13 files
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

[bottlepy/bottle-extras](https://github.com/bottlepy/bottle-extras)

---
*Parsed on 2026-10-11 by [repolex](https://repolex.ai)*
