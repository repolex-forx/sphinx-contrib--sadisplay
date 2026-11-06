# Repolex Knowledge Graph of sphinx-contrib/sadisplay

RDF knowledge graph data for [sphinx-contrib/sadisplay](https://github.com/sphinx-contrib/sadisplay), parsed by [repolex](https://repolex.ai).

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
rlex download sphinx-contrib/sadisplay
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ad93a567f77df680283cb979fe5e0ca3e324c62f
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── ad93a567f77df680283cb979fe5e0ca3e324c62f
│           └── chunk-001.nq.gz
├── blob
│   ├── 25368792f063a78711b03bc922a685d4c377c278.nq.gz
│   ├── 2a23d95fc20b81014bfb36fdc4c707f53e129da1.nq.gz
│   ├── 2d74c58f248790e34e482eb07e20ec6c753c9d2d.nq.gz
│   ├── 5435957533cde93572534b53802a05cbd9f5c0fa.nq.gz
│   ├── 5560e48889084855abe0f1a3518102645687ddf0.nq.gz
│   ├── 7bc3eb6ff7dfe4805ceba0198f03332a2e26e61a.nq.gz
│   ├── 88e8ac0890db9de55155fe5511ee14ad93e35092.nq.gz
│   ├── 98f91438e706f57812c301d06407deeeaa2d2211.nq.gz
│   ├── adf8064a3a104c72b55493d330a5ec3945ae8284.nq.gz
│   ├── c5a67e7ad29aeeadf73350c7677b251a36f7c566.nq.gz
│   ├── ca2948d3ff71bfb5322f7d66f4900eb45fdc9719.nq.gz
│   ├── e0dafce3f89e25966a83fe2822e9a8fad4b4f57b.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   └── ff1d72ad3706d8731d82e5102cc9b24e4bf30397.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── ad93a567f77df680283cb979fe5e0ca3e324c62f.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 22 files
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

[sphinx-contrib/sadisplay](https://github.com/sphinx-contrib/sadisplay)

---
*Parsed on 2026-11-06 by [repolex](https://repolex.ai)*
