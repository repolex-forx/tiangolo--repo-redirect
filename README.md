# Repolex Knowledge Graph of tiangolo/repo-redirect

RDF knowledge graph data for [tiangolo/repo-redirect](https://github.com/tiangolo/repo-redirect), parsed by [repolex](https://repolex.ai).

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
rlex download tiangolo/repo-redirect
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 1e4e8677a6232a7dfe44c6789bd469340430d192
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 1e4e8677a6232a7dfe44c6789bd469340430d192
│           └── chunk-001.nq.gz
├── blob
│   ├── 06ca6b3d8106b03fe250d383daa469187da51164.nq.gz
│   ├── 12a7aeb2846d4a17e87008fb3bb8ca253e07bf47.nq.gz
│   ├── 1d5d61c15d9b2f6dcbf646c1c8c4e82695d1d503.nq.gz
│   ├── 22dd1c1d26417bb3f592875c3abc1b3b1cf9f39e.nq.gz
│   ├── 505a3b1ca2716907d5b292ab90c36df043c42bb6.nq.gz
│   ├── 6324d401a069f4020efcf0ff07442724b52f47c2.nq.gz
│   ├── 8dc006060a91211097221b51302dfa60d1fee337.nq.gz
│   ├── afba912bad53d4a798457ab69816029aeee3649b.nq.gz
│   ├── e46ed426558f8b414419c55d1a2c855cbd8296a2.nq.gz
│   ├── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
│   ├── e940a46aee5b7acdc5a87ad63655eff72234c68f.nq.gz
│   ├── edde5cd6ef4eaa9db2ffde0ea428756b91930831.nq.gz
│   └── f1bb8f6e9b3505f792f34cefec38beb9c5ebfad6.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 1e4e8677a6232a7dfe44c6789bd469340430d192.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

12 directories, 20 files
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

[tiangolo/repo-redirect](https://github.com/tiangolo/repo-redirect)

---
*Parsed on 2026-10-10 by [repolex](https://repolex.ai)*
