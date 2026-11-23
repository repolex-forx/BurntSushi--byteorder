# Repolex Knowledge Graph of BurntSushi/byteorder

RDF knowledge graph data for [BurntSushi/byteorder](https://github.com/BurntSushi/byteorder), parsed by [repolex](https://repolex.ai).

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
rlex download BurntSushi/byteorder
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── ec068eefa042d494475db125c4b034bd8e9e34dd
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── ec068eefa042d494475db125c4b034bd8e9e34dd.nq.gz
│   └── repolex
│       └── ec068eefa042d494475db125c4b034bd8e9e34dd
│           └── chunk-001.nq.gz
├── blob
│   ├── 1aa3c3b5e73b1b2425d50cdefaea519987d5a740.nq.gz
│   ├── 1fec0efb811cee3aba9dfa9dd70f4d32706bec64.nq.gz
│   ├── 3b0a5dc09c1e16357459ddc9182a50f360f3cdba.nq.gz
│   ├── 68a49daad8ff7e35068f2b7a97d643aab440eaec.nq.gz
│   ├── 7c46019e0e0886c4b0087d87d95a25fbb8843cd6.nq.gz
│   ├── 91e6ab1c36f0f72718265d96b6d88279b9ecede1.nq.gz
│   ├── 963251ce56a755b87e5e81a59e4aff252b21653b.nq.gz
│   ├── 9efb7ed29a4597982d10eb2e93f198665b1aab31.nq.gz
│   ├── aa37a218b97e5f6ad37a74a62b50727279a5e460.nq.gz
│   ├── bb9c20a094e41b7632d63bcff20c0b4b95e80777.nq.gz
│   ├── cfd53c3f95c54cd8628c8078a0fc90d334fa9f04.nq.gz
│   └── dfad2ca39e9f619021c316bd885e788fa98a4e41.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── ec068eefa042d494475db125c4b034bd8e9e34dd.nq.gz
├── filetree
│   └── ec068eefa042d494475db125c4b034bd8e9e34dd.nq.gz
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

[BurntSushi/byteorder](https://github.com/BurntSushi/byteorder)

---
*Parsed on 2026-11-23 by [repolex](https://repolex.ai)*
