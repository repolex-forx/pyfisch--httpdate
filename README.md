# Repolex Knowledge Graph of pyfisch/httpdate

RDF knowledge graph data for [pyfisch/httpdate](https://github.com/pyfisch/httpdate), parsed by [repolex](https://repolex.ai).

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
rlex download pyfisch/httpdate
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 638da761065df8b67282b0a1d139c0a7e4a02429
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 638da761065df8b67282b0a1d139c0a7e4a02429.nq.gz
│   └── repolex
│       └── 638da761065df8b67282b0a1d139c0a7e4a02429
│           └── chunk-001.nq.gz
├── blob
│   ├── 4f82467bdb3809cec51e74895b510aabd36127ff.nq.gz
│   ├── 572e03bdf321b6cc3a99488183436905cefd086d.nq.gz
│   ├── 8819964156340c2b1873d521b5b4d8e9a3d08206.nq.gz
│   ├── 88b9f696fe678eba9ccfc8c2c0cbe6098320b3cc.nq.gz
│   ├── 88cb6fa75175d9c5929f1508af0ade935771c04a.nq.gz
│   ├── 8a9dfcc7de00ac47ba24ed7448f6b8204831932c.nq.gz
│   ├── 8bc0a3b33bb9ca8ac3c3204e10fcea5810a762ec.nq.gz
│   ├── a9d37c560c6ab8d4afbf47eda643e8c42e857716.nq.gz
│   ├── cb1951cc32831e939647406f87b14aa65c543b50.nq.gz
│   ├── cd482d89761c2eb60d1fc8c72c1708b7f47b8c82.nq.gz
│   ├── dd436e86e0f97d0dd5b00b36ccdb0acccb5c8380.nq.gz
│   └── ddc17f10991084ad4dea8695b444a5ed6c1293d7.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── 638da761065df8b67282b0a1d139c0a7e4a02429.nq.gz
├── filetree
│   └── 638da761065df8b67282b0a1d139c0a7e4a02429.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 22 files
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

[pyfisch/httpdate](https://github.com/pyfisch/httpdate)

---
*Parsed on 2026-11-22 by [repolex](https://repolex.ai)*
