# Repolex Knowledge Graph of augmentcode/augment.vim

RDF knowledge graph data for [augmentcode/augment.vim](https://github.com/augmentcode/augment.vim), parsed by [repolex](https://repolex.ai).

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
rlex download augmentcode/augment.vim
```

Consult `rlex --help` for other options, including SPARQL queries, HTTP server, and interactive visualization.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── 71f49befb94d3ddcf42220d640e892bd025dda5d
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── 71f49befb94d3ddcf42220d640e892bd025dda5d.nq.gz
│   └── repolex
│       └── 71f49befb94d3ddcf42220d640e892bd025dda5d
│           └── chunk-001.nq.gz
├── blob
│   ├── 0300e649779d641edc0189de35ee286ea3f8b267.nq.gz
│   ├── 07b9d806bd0ed34fb42f7c99fea5651d98181afd.nq.gz
│   ├── 254ed9c0c105af3e4df99991bec98a4c830bd6aa.nq.gz
│   ├── 2e65f401caa685c0e9dc73cab6d1b6de504f2799.nq.gz
│   ├── 34e63ba8d410297d8d1dced7238148a712614849.nq.gz
│   ├── 4eccf2a1d36b17cc16ca7b7f19e21bcd17218ad9.nq.gz
│   ├── 549f584fb00a8f54647c6644a56f558f4e0eb281.nq.gz
│   ├── 5f1c221bded62c41225e3b84cd8be9597db9d969.nq.gz
│   ├── a6afeea760c9658cbb62d712eabaf3681a53aee8.nq.gz
│   ├── c69a7f8f5479a66acfbe4d96bf0798fe71a5c172.nq.gz
│   ├── d52f0421de227148e83eeaf4921c8c1cd09cfc22.nq.gz
│   ├── fbb74690d4498e7148f039cc2cd1fbfc9afc1919.nq.gz
│   └── fcf067b60fe97fb36595a06468ae4475b5ff5c2d.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── filetree
│   └── 71f49befb94d3ddcf42220d640e892bd025dda5d.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

14 directories, 22 files
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

[augmentcode/augment.vim](https://github.com/augmentcode/augment.vim)

---
*Parsed on 2026-10-01 by [repolex](https://repolex.ai)*
