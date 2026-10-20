# Repolex Knowledge Graph of simonw/datasette-upload-dbs

RDF knowledge graph data for [simonw/datasette-upload-dbs](https://github.com/simonw/datasette-upload-dbs), parsed by [repolex](https://repolex.ai).

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
rlex download simonw/datasette-upload-dbs
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 563cb7896255690c67f898a604f7d53002a26cfd
│   │       └── chunk-001.nq.gz
│   └── repolex
│       └── 563cb7896255690c67f898a604f7d53002a26cfd
│           └── chunk-001.nq.gz
├── blob
│   ├── 169969c8eccd1dbf5ed8147ec6261ba0953114f4.nq.gz
│   ├── 261eeb9e9f8b2b4b0d119366dda99c6fd7d35c64.nq.gz
│   ├── 36f3270afddeea899d01d3d8456d8ffb1ad7223b.nq.gz
│   ├── 3dfd58b0c56a8c500c7993cf0d0eef7003ab89a9.nq.gz
│   ├── 641c4b55d03cd3ba3f2184b0a448b173766dcd7e.nq.gz
│   ├── b4f56672d39e4839edda141a09507ce69b979aea.nq.gz
│   ├── d1eefb03f4f04d2bb8532ebee42b113aca0f3652.nq.gz
│   ├── d4d62fdf657a7966527f3919c2cdfc5946097560.nq.gz
│   ├── e61ce1d68a38f43ce1ad952ccdb94f9ab7d69670.nq.gz
│   └── f961d9c25afd09d3f72a93aa940c14426478b969.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 563cb7896255690c67f898a604f7d53002a26cfd.nq.gz
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

[simonw/datasette-upload-dbs](https://github.com/simonw/datasette-upload-dbs)

---
*Parsed on 2026-10-20 by [repolex](https://repolex.ai)*
