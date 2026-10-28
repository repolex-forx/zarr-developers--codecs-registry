# Repolex Knowledge Graph of zarr-developers/codecs-registry

RDF knowledge graph data for [zarr-developers/codecs-registry](https://github.com/zarr-developers/codecs-registry), parsed by [repolex](https://repolex.ai).

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
rlex download zarr-developers/codecs-registry
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 419b97c12e8b15230b952ca91ed778c2fabbb8a9
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 419b97c12e8b15230b952ca91ed778c2fabbb8a9
│           └── chunk-001.nq.gz
├── blob
│   ├── 019cc9ea029759678f9491fc14ef54581af715ed.nq.gz
│   ├── 021b240b4a980d548877487c62cf5bb53af9d4a3.nq.gz
│   ├── 171bfdad76e222b32d967d29e39b879b7c2b47fe.nq.gz
│   ├── 1b5fa66a21aeb7ac2b7364116628720bb095253d.nq.gz
│   ├── 3a543ad87c75a057e725cc37443d2060ba65a99e.nq.gz
│   ├── 4ea67f2b77b35016563d801567253b448d5ed941.nq.gz
│   ├── 798552c51c38bfe51aa4bc8b9b6f4079532185e0.nq.gz
│   ├── 7bcd9530ac52e727b5713edae9cbefcb4e578554.nq.gz
│   ├── 8e14308a0b4a4d554be16deefdaf33a2d9ba53bc.nq.gz
│   └── ec220511e2ee0f6e4590823ebbdb42b9cc1cdd09.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 419b97c12e8b15230b952ca91ed778c2fabbb8a9.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

13 directories, 18 files
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

[zarr-developers/codecs-registry](https://github.com/zarr-developers/codecs-registry)

---
*Parsed on 2026-10-28 by [repolex](https://repolex.ai)*
