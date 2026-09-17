# Repolex Knowledge Graph of rbarrois/fslib

RDF knowledge graph data for [rbarrois/fslib](https://github.com/rbarrois/fslib), parsed by [repolex](https://repolex.ai).

> **Note**: This data is experimental and subject to change without notice.

## How to use this data

The easiest way to get started is to install the [lexq](https://github.com/repolex-ai/lexq) query tool using [uv](https://docs.astral.sh/uv/getting-started/installation/).

If you have uv installed, just copy/paste this into your terminal:

```bash
uv tool install git+https://github.com/repolex-ai/lexq
```

This installs lexq onto your system, in your user context. Verify the install:

```bash
lexq --help
```

**lexq is designed to be used primarily by LLMs in a terminal.** Start up your favorite LLM and ask it to use the lexq tool. It's that easy!

To load this repo's data:

```bash
lexq download rbarrois/fslib
```

This will automatically download essential data files from the last parsed commit. Consult `lexq --moreinfo` for other options, including downloading multiple commits, blobs, etc.

## Data structure

All data is stored as gzip-compressed [N-Quads](https://www.w3.org/TR/n-quads/) (`.nq.gz`), a standard RDF format that can be loaded into any triplestore or graph database.

```
.
├── aggregate
│   ├── ast
│   │   └── b7d0bb3431fe23530ebd5043d0d518b5b2d108be
│   │       └── chunk-001.nq.gz
│   ├── lsp
│   │   └── b7d0bb3431fe23530ebd5043d0d518b5b2d108be.nq.gz
│   └── repolex
│       └── b7d0bb3431fe23530ebd5043d0d518b5b2d108be
│           └── chunk-001.nq.gz
├── blob
│   ├── 1d07143aecc185afc669c20db32291043024307a.nq.gz
│   ├── 2acf2232995a824c1fc63ea0165148c9b787831b.nq.gz
│   ├── 36878081a57df26d60fac40288ca7253b530856b.nq.gz
│   ├── 3d3ba65c57870e631f4248dc9a16bf0c56ef9f8f.nq.gz
│   ├── 41292042519867276c39f906b024a5149a486f69.nq.gz
│   ├── 5ce3594cb6735c8fcde0e9f2385c047198db50c1.nq.gz
│   ├── 5e425f618ae7231d9978049037c17c12602a4cd0.nq.gz
│   ├── 723fa5fc89ea36925ee1155eab951928db36850f.nq.gz
│   ├── a7a486f31f4b650488a449022ceb652bce695731.nq.gz
│   ├── b4d25fcac8d1fec19cff5f5eca9fe42db2aec0a9.nq.gz
│   ├── bc713d1267285aa38be0fd9ee5a171e9cc3a6009.nq.gz
│   ├── c39707f14a04d5f5203fc4d508c04ad39db9b5b8.nq.gz
│   ├── cebc4a933d5a0f53e41f1c6fb8209a2f46cdb9cd.nq.gz
│   ├── d492ae2cac5b4752b647695916f0233726c771f1.nq.gz
│   ├── e4b0b38508cab83694a1f8d449663c59e2b671cc.nq.gz
│   └── e69de29bb2d1d6434b8b29ae775ad8c2e48c5391.nq.gz
├── branch
│   └── branch.nq.gz
├── commit
│   └── commit.nq.gz
├── dep
│   └── b7d0bb3431fe23530ebd5043d0d518b5b2d108be.nq.gz
├── filetree
│   └── b7d0bb3431fe23530ebd5043d0d518b5b2d108be.nq.gz
├── issue
│   └── issue.nq.gz
├── pr
│   └── pr.nq.gz
└── tag
    └── tag.nq.gz

15 directories, 26 files
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

## Source repository

[rbarrois/fslib](https://github.com/rbarrois/fslib)

---
*Parsed on 2026-09-17 by [repolex](https://repolex.ai)*
