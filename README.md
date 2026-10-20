# Repolex Knowledge Graph of klen/starlette-plugins

RDF knowledge graph data for [klen/starlette-plugins](https://github.com/klen/starlette-plugins), parsed by [repolex](https://repolex.ai).

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
rlex download klen/starlette-plugins
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 5ca24ddc1ade331e30e83272fe5e5703d2fd35fb
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 5ca24ddc1ade331e30e83272fe5e5703d2fd35fb
│           └── chunk-001.nq.gz
├── blob
│   ├── 0eb6dcacd67ac20c461b23cec6743044f32fbd45.nq.gz
│   ├── 178e66ffe768300cd50ddddd190ecc5e14c4e241.nq.gz
│   ├── 20c850c6a393ec7d20a769f5602ead5f785d716d.nq.gz
│   ├── 2247d5f95a7193c7221b9464debe167763b4fae3.nq.gz
│   ├── 349fa04ce5d3d61d60fc670a83062858d2e79266.nq.gz
│   ├── a4ee3bcb17de74d867b34df6246d80b9da2a6176.nq.gz
│   ├── d937a870d97cd05918d2ab949a13e0e3d83b2c90.nq.gz
│   ├── ddaa579057e4b4f469cf2e5886a5ee0ee2ae8a54.nq.gz
│   ├── ed76978d02b3b8bf9e69d89920410c1a3cbd7957.nq.gz
│   └── f586e87f8a4d343e8b9c7e78bdee2d7a0b36183c.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 5ca24ddc1ade331e30e83272fe5e5703d2fd35fb.nq.gz
└── tag
    └── tag.nq.gz

11 directories, 16 files
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

[klen/starlette-plugins](https://github.com/klen/starlette-plugins)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
